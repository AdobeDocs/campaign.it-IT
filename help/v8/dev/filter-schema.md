---
title: Filtrare gli schemi delle campagne
description: Scopri come filtrare gli schemi di Campaign
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
TQID: https://experienceleague.adobe.com/2T0OxjyVTM9-lzsOfcaqv81YVtVvrNpprpyC0VLoWgU
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 401
ht-degree: 2%

---

# Filtrare gli schemi{#filter-schemas}

## Filtri di sistema {#system-filters}

Puoi filtrare l’accesso allo schema per utenti specifici, a seconda delle loro autorizzazioni. I filtri di sistema consentono di gestire le autorizzazioni di lettura e scrittura delle entità dettagliate negli schemi, utilizzando i parametri **readAccess** e **writeAccess**.

>[!NOTE]
>
>Questa restrizione si applica solo agli utenti non tecnici: un utente tecnico, con le autorizzazioni correlate o che utilizza un flusso di lavoro, potrà recuperare e aggiornare i dati.

* **readAccess**: fornisce accesso in sola lettura ai dati dello schema.

  **Avviso** - Tutte le tabelle collegate devono essere impostate con la stessa restrizione. Questa configurazione può influire sulle prestazioni.

* **writeAccess**: fornisce accesso in scrittura ai dati dello schema.

Questi filtri vengono immessi al livello **elemento** principale degli schemi e, come mostrato negli esempi seguenti, possono essere formati per limitare l&#39;accesso.

* Limita autorizzazioni SCRITTURA

  In questo caso, il filtro viene utilizzato per non consentire le autorizzazioni di SCRITTURA sullo schema per gli operatori che non dispongono dell’autorizzazione AMMINISTRAZIONE. Ciò significa che solo gli amministratori avranno autorizzazioni di scrittura sulle entità descritte da questo schema.

  ```
  <sysFilter name="writeAccess">      
   <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
  </sysFilter>
  ```

* Limita le autorizzazioni di LETTURA e SCRITTURA:

  In questo caso, il filtro viene utilizzato per non consentire le autorizzazioni di LETTURA e SCRITTURA sullo schema per tutti gli operatori. Solo l&#39;account **internal**, rappresentato dall&#39;espressione &quot;$(loginId)!=0&quot;, dispone di queste autorizzazioni.

  ```
  <sysFilter name="readAccess"> 
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  
  <sysFilter name="writeAccess">  
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  ```

  I possibili valori dell&#39;attributo **expr** utilizzati per definire la condizione sono TRUE o FALSE.

>[!NOTE]
>
>Se non viene specificato alcun filtro, tutti gli operatori disporranno di autorizzazioni di lettura e scrittura per lo schema.

## Proteggere gli schemi incorporati

Per impostazione predefinita, gli schemi incorporati sono accessibili solo con autorizzazioni di SCRITTURA per gli operatori con diritti di AMMINISTRAZIONE:

* ncm:publishing
* nl:monitoring
* nms:calendar
* xtk:builder
* xtk:connections
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusion
* xtk:image
* xtk:javascript
* xtk:jssp
* xtk:jst
* xtk:navtree
* xtk:operatorGroup
* xtk:package
* xtk:queryDef
* xtk:resourceMenu
* xtk:rights
* xtk:schema
* xtk:scriptContext
* xtk:specFile
* xtk:sql
* xtk:sqlSchema
* xtk:srcSchema
* xtk:strings
* xtk:xslt

>[!CAUTION]
>
>Le autorizzazioni di LETTURA e SCRITTURA per lo schema **xtk:sessionInfo** sono accessibili solo dall&#39;account interno di un&#39;istanza Adobe Campaign.

## Modificare i filtri di sistema degli schemi incorporati

Gli schemi incorporati sono protetti per evitare problemi di compatibilità con le versioni precedenti. Adobe consiglia di non modificare i parametri dello schema predefiniti per garantire una sicurezza ottimale.

Tuttavia, in contesti specifici, potrebbe essere necessario modificare i filtri di sistema degli schemi incorporati. A tale scopo, segui i passaggi indicati di seguito:

1. Crea un&#39;estensione per lo schema integrato o apri un&#39;estensione esistente.
1. Aggiungere un elemento figlio **`<sysfilter name="<filter name>" _operation="delete"/>`** nell&#39;elemento principale per ignorare il filtro nello stesso elemento nello schema predefinito.
1. Puoi aggiungere un nuovo filtro, come descritto nella sezione [Filtri di sistema](#system-filters).
