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
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 2%

---

# Campaign Classic v7 - Funzionalità di Campaign v8{#gs-matrix}


In qualità di utente esistente di Campaign Classic v7, dovresti aspettarti qualsiasi grande interruzione nel modo in cui di solito &quot;giochi&quot; con Adobe Campaign. La maggior parte delle modifiche non è visibile, tranne piccole modifiche che vengono visualizzate nell’interfaccia utente e nei passaggi di configurazione.

Modifiche chiave:

* Creare segmenti fino a 200 volte più veloci

* Aumento della velocità di consegna

* Rapporti in tempo reale

In qualità di utente Campaign Classic, tieni presente che la maggior parte delle funzioni di Campaign Classic v7 sono disponibili con Campaign v8, ad eccezione di un piccolo set di esse, elencato in [questa sezione](#gs-removed). Altri saranno disponibili nelle prossime versioni. [Ulteriori informazioni](#gs-unavailable-features)


## Modifiche alla configurazione del prodotto

### Campagna e [!DNL Snowflake] {#ac-gs-snowflake}

L&#39;archiviazione cloud viene eseguita in [!DNL Snowflake]: un nuovo account esterno garantisce la connettività con il database cloud. [Ulteriori informazioni](#ac-gs-snowflake).

Questo è un cambiamento fondamentale nell&#39;architettura del software. I dati sono ora remoti: Campaign unisce tutti i dati, inclusi i profili. Il processo di Campaign ora viene ridimensionato in modo completo, dal targeting all’esecuzione della consegna: L’acquisizione dei dati, la segmentazione, il targeting, le query e l’esecuzione della consegna verranno ora eseguite in minuti.

Questa nuova versione risolve l&#39;intera sfida del ridimensionamento, mantenendo lo stesso livello di flessibilità ed estensibilità. Il numero di profili è quasi illimitato e la conservazione dei dati può essere estesa.

Un nuovo account **esterno** integrato è dedicato a Full FDA. Questo è il cuore della connettività di Cloud Database. Consigliamo di partire così com&#39;è.

Qualsiasi schema/tabella incorporata che deve essere spostata o replicata nel database cloud presenta un&#39;estensione dello schema incorporata nello spazio dei nomi **xxl**. Per quanto riguarda l’estensione dello schema, il nuovo spazio dei nomi XXL verrà utilizzato per qualsiasi nuovo elemento di configurazione OOTB come JavaScript, JSSP, ecc.

Tali estensioni contengono qualsiasi modifica necessaria per spostare gli schemi incorporati dal database locale di Campaign al database [!DNL Snowflake] Cloud e per adattare di conseguenza la loro struttura: nuovo UUID, collegamenti aggiornati, ecc.

>[!CAUTION]
>
> I dati del cliente non vengono memorizzati nel database locale di Campaign. Di conseguenza, qualsiasi tabella personalizzata deve essere creata nel database Cloud.


### Replica dati

Un flusso di lavoro tecnico specifico gestisce la replica delle tabelle che devono essere presenti su entrambi i lati (database locale di Campaign e database Cloud). Questo flusso di lavoro viene attivato ogni ora e si basa su una nuova libreria JavaScript integrata.

>[!NOTE]
>
> Sono stati creati più criteri di replica in base alle dimensioni della tabella (XS, XL, ecc.).
> Alcune tabelle vengono replicate in tempo reale, mentre altre sono su base oraria. Alcune tabelle avranno aggiornamenti incrementali, mentre altre saranno aggiornate completamente.


[Ulteriori informazioni sulla replica dei dati](../config/replication.md)

### Gestione ID

Gli oggetti Campaign v8 ora utilizzano **UUID univoco universale (UUID)**, il che implica valori univoci illimitati per identificare i dati

L&#39;ID è basato su stringhe e non sequenziale.

### Manutenzione semplificata

Gli utenti di Campaign non devono essere esperti del database: non sarà più necessario gestire flussi di lavoro lunghi o indicizzare tabelle complesse.

## Funzioni temporanee non disponibili{#gs-unavailable-features}

Tieni presente che alcune funzionalità non sono disponibili in questa prima versione ma saranno presto rilasciate, ad esempio:

* Gestione delle risorse di marketing
* Marketing distribuito
* Messaggi in entrata di Gestione delle offerte (modulo di interazione)
* Ottimizzazione di Campaign
* Gestione della risposta
* Social marketing con Twitter
* Modelli di distribuzione ibrida/on-premise

## Funzioni rimosse{#gs-removed}

Per allinearsi alla nuova architettura e al modello di distribuzione di Campaign v8, alcune funzionalità storiche di Campaign Classic v7 non sono disponibili in Campaign v8.

* Coupon
* Tracciamento web
* Indagini
* Social marketing con Facebook
* Connettore ACS (offerta Prime)
* Database Microsoft SQL
* Database di Oracle
