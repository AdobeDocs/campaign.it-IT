---
title: Matrice di funzionalità Campaign Classic v7 e Campaign v8
description: Comprendere le differenze tra Campaign Classic v7 e Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
source-git-commit: 95e1aff491257faeda8e12bf29aa95045901c8b2
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 100%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8: cosa cambia{#gs-matrix}

Per chi già utilizza [!DNL Campaign Classic] v7, non vi sono differenze significative nel modo abituale in cui si interagisce con [!DNL Adobe Campaign]. La maggior parte delle modifiche nella versione 8 non sono visibili, tranne che per le piccole modifiche visualizzate nell’interfaccia utente e nei passaggi di configurazione.

Modifiche principali:

* Creazione di segmenti fino a 200 volte più velocemente
* Aumento della velocità di consegna
* Rapporti in tempo reale con i “cubi”

In qualità di utente di [!DNL Campaign Classic], tieni presente che la maggior parte delle funzioni di [!DNL Campaign Classic] v7 sono disponibili anche in [!DNL Campaign] v8, ad eccezione di un piccolo insieme elencato in [questa sezione](#gs-removed). Altre funzioni saranno disponibili nelle prossime versioni. [Per ulteriori informazioni, consulta questa sezione](#gs-unavailable-features).

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull’architettura di [!DNL Campaign] v8 sono disponibili in [questa pagina](../dev/architecture.md).

## Modifiche alla configurazione del prodotto

### [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

[!DNL Adobe Campaign] v8 funziona con due database: uno locale per la messaggistica in tempo reale, le query unitarie dell’interfaccia utente e le operazioni di scrittura tramite API; e un database cloud per l’esecuzione della campagna, le query batch e l’esecuzione dei fluiso di lavoro.

Questo è un cambiamento fondamentale nell’architettura del software. Adesso i dati sono remoti e Campaign unisce tutti i dati, inclusi i profili. I processi di [!DNL Campaign] ora vengono scalati in modalità end-to-end, dal targeting all’esecuzione dei messaggi: in genere l’acquisizione dei dati, la segmentazione, il targeting, le query e le consegne vengono eseguite in pochi minuti. Questa nuova versione risolve l’intera sfida della scalabilità mantenendo lo stesso livello di flessibilità ed estensibilità. Il numero di profili è quasi illimitato e la conservazione dei dati può essere estesa.

L’archiviazione cloud viene eseguita in **[!DNL Snowflake]**: un nuovo **account esterno** integrato garantisce la connettività con il database cloud. È configurato da Adobe e non deve essere modificato. [Ulteriori informazioni](../config/external-accounts.md)

Le tabelle o gli schemi integrati che devono essere spostati o replicati nel database cloud hanno un’estensione di schema integrato nello spazio dei nomi **xxl**. Tali estensioni contengono eventuali modifiche necessarie per spostare gli schemi integrati dal database locale di [!DNL Campaign] al database cloud [!DNL Snowflake] e per adattarne di conseguenza la struttura: nuovo UUID, collegamenti aggiornati, ecc.

>[!CAUTION]
>
> I dati dei clienti non vengono memorizzati nel database locale di [!DNL Campaign]. Di conseguenza, eventuali tabelle personalizzate devono essere create nel database cloud.

Sono disponibili API specifiche per la gestione dei dati tra il database locale e quello cloud. Per scoprire come funzionano queste nuove API e come utilizzarle, visita [questa pagina](../dev/new-apis.md).

### Replica dei dati

Un flusso di lavoro tecnico specifico gestisce la replica delle tabelle che devono essere presenti su entrambi i lati (database Cloud e database locale di Campaign). Questo flusso di lavoro viene attivato ogni ora e si basa su una nuova libreria JavaScript integrata.

>[!NOTE]
>
> Sono stati creati diversi criteri di replica in base alle dimensioni della tabella (XS, XL, eccetera).
> Alcune tabelle vengono replicate in tempo reale, altre vengono replicate su base oraria. Alcune tabelle avranno aggiornamenti incrementali, altre avranno un aggiornamento completo.

[Ulteriori informazioni sulla replica dei dati](../config/replication.md)

### Gestione ID

Ora gli oggetti di Campaign v8 utilizzano un **ID universalmente univoco (UUID)**, che consente l’identificazione dei dati tramite valori univoci illimitati.

Tieni presente che questo ID è basato su stringhe e non è sequenziale. La chiave primaria non è un valore numerico in Campaign v8 e devi utilizzare gli attributi **autouuid** e **autopk** negli schemi.

In Campaign Classic v7 e versioni precedenti, l’unicità di una chiave all’interno di uno schema (ovvero una tabella) viene gestita a livello di motore del database. Più in generale, i motori di database classici come PostgreSQL, Oracle o SQL Server includono un meccanismo nativo per impedire l’inserimento di righe duplicate basate su una colonna o su un set di colonne attraverso l’uso di chiavi primarie e/o indici univoci. Quando l’indice e le chiavi primarie sono impostati correttamente a livello di database, l’ID duplicato non esiste in queste versioni.

Adobe Campaign v8 viene fornito con Snowflake come database di base. Poiché aumenta notevolmente la scalabilità delle query, l’architettura distribuita del database Snowflake non fornisce i meccanismi che consentono di gestire e dunque applicare l’unicità di una chiave all’interno di una tabella. Di conseguenza, in Adobe Campaign v8, è possibile effettuare l’inserimento di chiavi duplicate all’interno di una tabella. Gli utenti finali sono ora responsabili di garantire la coerenza delle chiavi all’interno del database di Adobe Campaign. [Ulteriori informazioni](../dev/keys.md)

### Manutenzione semplificata

Gli utenti di Campaign non devono essere esperti di database: non sono più necessarie operazioni complesse di manutenzione del database o di indicizzazione delle tabelle.

## Connessione a Campaign

Gli utenti di Campaign si connettono tramite il proprio Adobe ID. Lo stesso Adobe ID viene utilizzato per mantenere tutti i piani e i prodotti di Adobe associati a un singolo account.

![](../assets/do-not-localize/glass.png) Scopri come connetterti a [!DNL Campaign] in [questa pagina](connect.md).

## Generazione rapporti

I rapporti di Adobe Campaign sono ottimizzati e offrono migliori funzioni di scalabilità rispetto a Campaign Classic v7. Le limitazioni sui cubi non sono applicabili.

## Flusso di lavoro {#workflow}

Campaign v8 offre un’ulteriore attività del flusso di lavoro di targeting: **[!UICONTROL Change data source]**.

L’attività **[!UICONTROL Change data source]** consente di modificare l’origine dati di un flusso di lavoro **[!UICONTROL Working table]** per gestire i dati tra diverse origini dati, come FDA, FFDA e database locale.

![](../assets/do-not-localize/glass.png) Per saperne di più sull’attività **[!UICONTROL Change data source]**, visita [questa pagina](../config/workflows.md#change-data-source-activity).

## Funzioni non disponibili{#gs-unavailable-features}

Tieni presente che alcune funzionalità non sono ancora disponibili in questa versione di Campaign, ad esempio:

* Gestione delle risorse marketing
* Marketing distribuito
* Gestione della risposta
* Modelli di distribuzione on-premise/ibrida
* Canale Twitter

>[!CAUTION]
>
>* Per il momento, Campaign v8 è disponibile **solo** come Cloud Service gestito e non può essere implementato in ambienti locali o ibridi.
>
>* La migrazione da un ambiente esistente di Campaign Classic v7 non è ancora disponibile.
>
>* Se hai dubbi sul modello di implementazione o hai altre domande, contatta il team del tuo account.


## Funzioni non supportate{#gs-removed}

Per allinearsi alla nuova architettura e al modello di implementazione di Campaign v8, alcune funzionalità storiche di Campaign Classic v7 non sono più supportate in Campaign v8, come ad esempio:

* Coupon
* Tracciamento web
* Indagini
* Social marketing con Facebook
* Connettore ACS (offerta Prime)
* Integrazione con LDAP
* Accesso utente/password

>[!NOTE]
>
>Alcune funzioni non disponibili o non supportate possono risultare ancora visibili nell’interfaccia utente.