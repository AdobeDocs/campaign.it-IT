---
solution: Campaign v8
product: Adobe Campaign
title: Meccanismo di staging API di Campaign
description: Meccanismo di staging API di Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: 69d69c909e6b17ca3f5fb18d6680aa51d0d701cf
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 3%

---

# Meccanismo di staging API di Campaign

Con il database Campaign Cloud, le chiamate unitarie non sono consigliate a causa delle prestazioni (latenza e concorrenza). L&#39;operazione batch è sempre preferita. Per garantire prestazioni ottimali delle API, Campaign continua a gestire le chiamate API a livello di database locale.

Il meccanismo di gestione temporanea delle campagne è disponibile sia per le tabelle integrate che per quelle personalizzate e presenta i seguenti vantaggi:

* La struttura dello schema dati viene replicata nella tabella di staging locale
* Le nuove API per l’acquisizione scorrono direttamente nella tabella di staging. [Ulteriori informazioni](new-apis.md)
* Un flusso di lavoro pianificato viene attivato ogni ora e sincronizza nuovamente i dati con il database cloud. [Ulteriori informazioni](../config/replication.md).

Alcuni schemi incorporati sono impostati per impostazione predefinita, ad esempio nmsSubscriptionRcp, nmsAppSubscriptionRcp, nmsRecipient.

Le API di Campaign Classic v7 sono ancora disponibili ma non possono beneficiare di questo nuovo meccanismo di staging: Le chiamate API scorrono direttamente nel database Cloud. L’Adobe consiglia di utilizzare il più possibile un nuovo meccanismo di staging per ridurre la pressione e la latenza complessiva sul database di Campaign Cloud.

>[!CAUTION]
>
>Con questo nuovo meccanismo, la sincronizzazione dei dati per gli abbonamenti, gli annullamenti degli abbonamenti o la registrazione mobile è ora **asincrona**.


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

   [!DNL :bulb:] Ulteriori informazioni sulla creazione di schemi personalizzati in  [questa pagina](create-schema.md).

1. Salvare e aggiornare la struttura del database.  [Ulteriori informazioni](update-database-structure.md)

1. Abilita il meccanismo di staging nella definizione dello schema aggiungendo il parametro **autoStg=&quot;true&quot;** .

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
