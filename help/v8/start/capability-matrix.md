---
solution: Campaign
product: Adobe Campaign
title: Campaign Classic v7 - Matrice di funzionalità per Campaign v8
description: Comprendere le differenze tra Campaign Classic v7 e Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62,7105477f-d29e-4af8-8789-82b4459761b0
translation-type: tm+mt
source-git-commit: e1308398e5a33f2ad9659ad632aeb05af9916e69
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 3%

---

# Campaign Classic v7 - Funzionalità di Campaign v8{#gs-matrix}


In qualità di utente esistente di Campaign Classic v7, non dovrebbe verificarsi alcuna interruzione importante nel modo in cui si interagisce solitamente con Adobe Campaign. La maggior parte delle modifiche nella versione v8 non sono visibili, tranne che per le piccole modifiche visualizzate nell’interfaccia utente e nei passaggi di configurazione.

Modifiche chiave:

* Creare segmenti fino a 200 volte più veloci

* Aumento della velocità di consegna

* Rapporti in tempo reale

In qualità di utente Campaign Classic, tieni presente che la maggior parte delle funzioni di Campaign Classic v7 sono disponibili con Campaign v8, ad eccezione di un piccolo set di esse, elencato in [questa sezione](#gs-removed). Altri saranno disponibili nelle prossime versioni. [Ulteriori informazioni](#gs-unavailable-features)


## Modifiche alla configurazione del prodotto

### Campagna e [!DNL Snowflake] {#ac-gs-snowflake}

L&#39;archiviazione cloud viene eseguita in [!DNL Snowflake]: un nuovo account esterno garantisce la connettività con il database cloud. [Ulteriori informazioni](#ac-gs-snowflake).

Questo è un cambiamento fondamentale nell&#39;architettura del software. I dati sono ora remoti e Campaign unisce tutti i dati, inclusi i profili. I processi di Campaign ora vengono ridimensionati in modo end-to-end, dal targeting all’esecuzione dei messaggi: in genere, l’acquisizione di dati, la segmentazione, il targeting, le query e le consegne vengono eseguite in pochi minuti.

Questa nuova versione risolve l&#39;intera sfida della scalabilità mantenendo lo stesso livello di flessibilità ed estensibilità. Il numero di profili è quasi illimitato e la conservazione dei dati può essere estesa.

Un nuovo account **esterno** integrato è dedicato a Full FDA. Questo è il cuore della connettività di Cloud Database. Consigliamo di partire così com&#39;è.

Qualsiasi schema/tabella incorporata che deve essere spostata o replicata nel database cloud viene fornito con un&#39;estensione dello schema incorporata nello spazio dei nomi **xxl** .

Tali estensioni contengono eventuali modifiche necessarie per spostare gli schemi incorporati dal database locale di Campaign al database [!DNL Snowflake] Cloud e per adattare di conseguenza la loro struttura: nuovo UUID, collegamenti aggiornati, ecc.

>[!CAUTION]
>
> I dati del cliente non vengono memorizzati nel database locale di Campaign. Di conseguenza, qualsiasi tabella personalizzata deve essere creata nel database Cloud.


### Replica dati

Un flusso di lavoro tecnico specifico gestisce la replica delle tabelle che devono essere presenti su entrambi i lati (database locale di Campaign e database Cloud). Questo flusso di lavoro viene attivato ogni ora e si basa su una nuova libreria JavaScript integrata.

>[!NOTE]
>
> Sono stati creati più criteri di replica in base alle dimensioni della tabella (XS, XL, ecc.).
> Alcune tabelle vengono replicate in tempo reale, altre vengono replicate su base oraria. Alcune tabelle avranno aggiornamenti incrementali, altre avranno un aggiornamento completo.


[Ulteriori informazioni sulla replica dei dati](../config/replication.md)

### Gestione ID

Gli oggetti Campaign v8 ora utilizzano un **ID universale univoco (UUID)**, che consente l’identificazione dei dati con valori univoci illimitati

L&#39;ID è basato su stringhe e non sequenziale.

### Manutenzione semplificata

Gli utenti di Campaign non devono essere esperti del database: non sono più necessarie operazioni complesse di manutenzione del database o indicizzazione complessa delle tabelle.

## Funzioni temporanee non disponibili{#gs-unavailable-features}

Tieni presente che alcune funzionalità non sono ancora disponibili in questa prima versione, ad esempio:

* Gestione delle risorse di marketing
* Marketing distribuito
* Gestione delle offerte in entrata (modulo di interazione)
* Ottimizzazione di Campaign
* Gestione della risposta
* Modelli di distribuzione ibrida/on-premise

## Funzioni rimosse{#gs-removed}

Per allinearsi alla nuova architettura e al modello di implementazione di Campaign v8, alcune funzionalità storiche di Campaign Classic v7 non sono più disponibili in Campaign v8.

* Coupon
* Tracciamento web
* Indagini
* Social marketing
* Connettore ACS (offerta Prime)

