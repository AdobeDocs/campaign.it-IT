---
title: Meccanismo di staging API di Campaign
description: Meccanismo di staging API di Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 96693af9-50db-4298-ae02-c238d35e52b4
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 2%

---

# Meccanismo di staging API di Campaign

Con il database di Campaign Cloud, non si consiglia di eseguire una notifica univoca per quanto riguarda le prestazioni (latenza e concorrenza). L’operazione di batch è sempre preferibile. Per migliorare le prestazioni, le API di acquisizione vengono reindirizzate al database locale.

La funzionalità di staging della campagna è abilitata per impostazione predefinita su alcuni schemi incorporati. Possiamo anche abilitarlo su qualsiasi schema personalizzato. Meccanismo di staging in sintesi:

* La struttura dello schema dati viene duplicata nella tabella di staging locale
* Nuove API dedicate per l’inserimento dei dati scorrono direttamente nella tabella di staging locale. [Ulteriori informazioni](new-apis.md)
* Un flusso di lavoro pianificato viene attivato ogni ora e sincronizza nuovamente i dati con il database cloud. [Ulteriori informazioni](../config/replication.md)

Alcuni schemi incorporati sono impostati per impostazione predefinita, ad esempio nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

Le API di Campaign Classic v7 sono ancora disponibili ma non possono beneficiare di questo nuovo meccanismo di staging: Le chiamate API scorrono direttamente nel database Cloud. L’Adobe consiglia di utilizzare il più possibile un nuovo meccanismo di staging per ridurre la pressione e la latenza complessiva sul database di Campaign Cloud.

>[!CAUTION]
>
>* Con questo nuovo meccanismo, la sincronizzazione dei dati per l&#39;optout del canale, gli abbonamenti, gli annullamenti degli abbonamenti o la registrazione mobile è ora **asincrono**.
>
>* Lo staging si applica solo agli schemi memorizzati nel database cloud. Non abilitare lo staging sugli schemi replicati. Non abilitare lo staging sugli schemi locali. Non abilitare la gestione temporanea su uno schema in fase
>


## Passaggi di implementazione{#implement-staging}

Per implementare il meccanismo di staging di Campaign su una tabella specifica, segui i passaggi seguenti:

1. Crea uno schema personalizzato di esempio sul database di Campaign Cloud. Al passaggio corrente non è abilitata alcuna fase di staging.

   ```
   <srcSchema _cs="Sample Table (dem)" created="YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

   ![](../assets/do-not-localize/glass.png) Ulteriori informazioni sulla creazione di schemi personalizzati in [questa pagina](create-schema.md).

1. Salvare e aggiornare la struttura del database.  [Ulteriori informazioni](update-database-structure.md)

1. Abilita il meccanismo di staging nella definizione dello schema aggiungendo il **autoStg=&quot;true&quot;** parametro .

   ```
   <srcSchema _cs="Sample Table (dem)" "YYYY-DD-MM"
           entitySchema="xtk:srcSchema" img="xtk:schema.png" label="Sample Table"
           lastModified="YYYY-DD-MM HH:MM:SS.TZ" mappingType="sql" md5="XXX"
           modifiedBy-id="0" name="sampleTable" namespace="dem" xtkschema="xtk:srcSchema">
   <element autoStg="true" autopk="true" autouuid="true" dataSource="nms:extAccount:ffda" label="Sample Table"
           name="sampleTable">
       <attribute label="Test Col 1" length="255" name="testcol1" type="string"/>
       <attribute label="Test Col 2" length="255" name="testcol2" type="string"/>
   </element>
   </srcSchema>
   ```

1. Salva la modifica. È disponibile un nuovo schema di staging, che è una copia locale dello schema iniziale.

   ![](assets/staging-mechanism.png)

1. Aggiorna la struttura del database. La tabella di staging verrà creata nel database locale di Campaign.
