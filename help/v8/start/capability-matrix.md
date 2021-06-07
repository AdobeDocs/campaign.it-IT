---
product: Adobe Campaign
title: Matrice di funzionalità Campaign Classic v7 e Campaign v8
description: Comprendere le differenze tra Campaign Classic v7 e Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 93b690d815f73d11de7de90b92ae188082a3e9e4
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 43%

---

# [!DNL Campaign Classic] v7 - Funzionalità  [!DNL Campaign] v8{#gs-matrix}

In qualità di utente [!DNL Campaign Classic] v7 esistente, non devi aspettarti grandi interruzioni nel modo in cui solitamente interagisci con [!DNL Adobe Campaign]. La maggior parte delle modifiche nella versione 8 non sono visibili, tranne che per le piccole modifiche visualizzate nell’interfaccia utente e nei passaggi di configurazione.

Modifiche principali:

* Creazione di segmenti fino a 200 volte più velocemente
* Aumento della velocità di consegna
* Rapporti in tempo reale con cubetti

In qualità di utente [!DNL Campaign Classic], tieni presente che la maggior parte delle funzioni [!DNL Campaign Classic] v7 sono disponibili con [!DNL Campaign] v8, ad eccezione di un piccolo insieme di esse, elencate in [questa sezione](#gs-removed). Altre funzioni saranno disponibili nelle prossime versioni. [Ulteriori informazioni in questa sezione](#gs-unavailable-features)

[!DNL :bulb:] Ulteriori informazioni sull&#39;architettura  [!DNL Campaign] v8 in  [questa pagina](../dev/architecture.md).

## Modifiche alla configurazione del prodotto

### [!DNL Campaign] e  [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 funziona con due database: un database locale per la messaggistica in tempo reale e le query unitarie dell’interfaccia utente e la scrittura tramite API e un database Cloud per l’esecuzione di una campagna, le query batch e l’esecuzione di un flusso di lavoro.

Questo è un cambiamento fondamentale nell’architettura del software. Adesso i dati sono remoti e Campaign unisce tutti i dati, inclusi i profili. [!DNL Campaign]I processi di ora vengono scalati in modalità end-to-end, dal targeting all’esecuzione dei messaggi: in genere l’acquisizione dei dati, la segmentazione, il targeting, le query e le consegne vengono eseguite in pochi minuti. Questa nuova versione risolve l’intera sfida della scalabilità mantenendo lo stesso livello di flessibilità ed estensibilità. Il numero di profili è quasi illimitato e la conservazione dei dati può essere estesa.

L&#39;archiviazione cloud viene eseguita in **[!DNL Snowflake]**: un nuovo account **esterno** integrato garantisce la connettività con il database cloud. È configurato da Adobe e non deve essere modificato. [Ulteriori informazioni](../config/external-accounts.md)

Qualsiasi schema/tabella integrata che deve essere spostata o replicata in Cloud Database viene fornita con un’estensione integrata dello schema nello spazio dei nomi **xxl** . Tali estensioni contengono eventuali modifiche necessarie per spostare gli schemi incorporati dal database locale [!DNL Campaign] al database [!DNL Snowflake] Cloud e per adattare di conseguenza la loro struttura: nuovo UUID, collegamenti aggiornati, ecc.

>[!CAUTION]
>
> I dati del cliente non vengono memorizzati nel database locale [!DNL Campaign]. Di conseguenza, qualsiasi tabella personalizzata deve essere creata nel database Cloud.


Sono disponibili API specifiche per gestire i dati tra il database locale e quello cloud. Scopri come funzionano queste nuove API e come utilizzarle in [questa pagina](../dev/new-apis.md).

### Replica dei dati

Un flusso di lavoro tecnico specifico gestisce la replica delle tabelle che devono essere presenti su entrambi i lati (database Cloud e database locale di Campaign). Questo flusso di lavoro viene attivato ogni ora e si basa su una nuova libreria JavaScript integrata.

>[!NOTE]
>
> Sono stati creati diversi criteri di replica in base alle dimensioni della tabella (XS, XL, eccetera).
> Alcune tabelle vengono replicate in tempo reale, altre vengono replicate su base oraria. Alcune tabelle avranno aggiornamenti incrementali, altre avranno un aggiornamento completo.


[Ulteriori informazioni sulla replica dei dati](../config/replication.md)

### Gestione ID

Ora gli oggetti di Campaign v8 utilizzano un **ID universalmente univoco (UUID)**, che consente l’identificazione dei dati tramite valori univoci illimitati.

Tieni presente che questo ID è basato su stringhe e non sequenziale. La chiave primaria non è un valore numerico in Campaign v8 e devi utilizzare gli attributi **autouuid** e **autopk** negli schemi.

Nelle versioni Campaign Classic v7 e precedenti, l’unicità di una chiave all’interno di uno schema (ovvero una tabella) viene gestita a livello di motore del database. Più in generale, i motori di database classici come PostgreSQL, Oracle o SQL Server includono un meccanismo nativo per impedire l&#39;inserimento di righe duplicate basate su una colonna o su un set di colonne tramite chiavi primarie e/o indici univoci. L&#39;ID duplicato non esiste in queste versioni quando l&#39;indice e le chiavi primarie sono impostati correttamente a livello di database.

Adobe campaign v8 viene fornito con Snowflake come database di base. Poiché aumenta notevolmente la scala delle query, l&#39;architettura distribuita del database di Snowflake non fornisce tali meccanismi per gestire e quindi applicare l&#39;unicità di una chiave all&#39;interno di una tabella. Di conseguenza, con Adobe Campaign v8, nulla impedisce l’inserimento di chiavi duplicate in una tabella. Gli utenti finali sono ora responsabili di garantire la coerenza delle chiavi all&#39;interno del database Adobe Campaign. [Ulteriori informazioni](../dev/keys.md)

### Manutenzione semplificata

Gli utenti di Campaign non devono essere esperti di database: non sono più necessarie operazioni complesse di manutenzione del database o di indicizzazione delle tabelle.

## Generazione rapporti

I rapporti di Adobe Campaign sono ottimizzati e offrono funzionalità su scala migliore rispetto a Campaign Classic v7. Le limitazioni esistenti sui cubi non si applicano.

## Funzioni non disponibili{#gs-unavailable-features}

Tieni presente che alcune funzionalità non sono disponibili in questa prima versione, ad esempio:

* Gestione delle risorse marketing
* Marketing distribuito
* Gestione offerte in entrata (modulo di interazione)
* Ottimizzazione di Campaign
* Gestione della risposta
* Modelli di distribuzione on-premise/ibrida
* Messaggi LINE
* Pannello di controllo Campaign

>[!CAUTION]
>
>Per il momento, Campaign v8 è **disponibile solo** come Cloud Service gestito e non può essere distribuito in ambienti on-premise o ibridi.
>
>La migrazione da un ambiente Campaign Classic v7 esistente non è ancora disponibile.
>
>Se non sei sicuro del modello di distribuzione o hai domande, contatta il team del tuo account.

## Funzioni rimosse{#gs-removed}

Per allinearsi alla nuova architettura e al modello di implementazione di Campaign v8, alcune funzionalità storiche di Campaign Classic v7 non sono più disponibili in Campaign v8.

* Coupon
* Tracciamento web
* Indagini
* Social marketing
* Connettore ACS (offerta Prime)

