---
title: Filtrare gli schemi delle campagne
description: Scopri come filtrare gli schemi di Campaign
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 2%

---

# Filtrare gli schemi{#filter-schemas}

## Filtri di sistema {#system-filters}

Puoi filtrare l’accesso allo schema per utenti specifici, a seconda delle loro autorizzazioni. I filtri di sistema consentono di gestire le autorizzazioni di lettura e scrittura delle entità descritte negli schemi, utilizzando **readAccess** e **writeAccess** parametri.

>[!NOTE]
>
>Questa restrizione si applica solo agli utenti non tecnici: un utente tecnico, con le autorizzazioni correlate o che utilizza un flusso di lavoro, potrà recuperare e aggiornare i dati.

* **readAccess**: fornisce accesso in sola lettura ai dati dello schema.

  **Avvertenza** - Tutte le tabelle collegate devono essere impostate con la stessa restrizione. Questa configurazione può influire sulle prestazioni.

* **writeAccess**: fornisce accesso in scrittura ai dati dello schema.

Questi filtri vengono immessi nella **elemento** degli schemi e, come mostrato negli esempi seguenti, possono essere formati per limitare l’accesso.

* Limita autorizzazioni SCRITTURA

  In questo caso, il filtro viene utilizzato per non consentire le autorizzazioni di SCRITTURA sullo schema per gli operatori che non dispongono dell’autorizzazione AMMINISTRAZIONE. Ciò significa che solo gli amministratori avranno autorizzazioni di scrittura sulle entità descritte da questo schema.

  ```
  <sysFilter name="writeAccess">      
   <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
  </sysFilter>
  ```

* Limita le autorizzazioni di LETTURA e SCRITTURA:

  In questo caso, il filtro viene utilizzato per non consentire le autorizzazioni di LETTURA e SCRITTURA sullo schema per tutti gli operatori. Solo il **interno** , rappresentato dall&#39;espressione &quot;$(loginId)!=0&quot;, dispone delle seguenti autorizzazioni.

  ```
  <sysFilter name="readAccess"> 
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  
  <sysFilter name="writeAccess">  
   <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
  </sysFilter>
  ```

  Possibile **espr** I valori degli attributi utilizzati per definire la condizione sono TRUE o FALSE.

>[!NOTE]
>
>Se non viene specificato alcun filtro, tutti gli operatori disporranno di autorizzazioni di lettura e scrittura per lo schema.

## Schemi incorporati di Protect

Per impostazione predefinita, gli schemi incorporati sono accessibili solo con autorizzazioni di SCRITTURA per gli operatori con diritti di AMMINISTRAZIONE:

* ncm:pubblicazione
* nl:monitoraggio
* nms:calendario
* xtk:builder
* xtk:connessioni
* xtk:dbInit
* xtk:entityBackupNew
* xtk:entityBackupOriginal
* xtk:entityOriginal
* xtk:form
* xtk:funcList
* xtk:fusion
* xtk:immagine
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
* xtk:stringhe
* xtk:xslt

>[!CAUTION]
>
>Autorizzazioni di LETTURA e SCRITTURA per **xtk:sessionInfo** sono accessibili solo dall’account interno di un’istanza Adobe Campaign.

## Modificare i filtri di sistema degli schemi incorporati

Gli schemi incorporati sono protetti per evitare problemi di compatibilità con le versioni precedenti. L’Adobe consiglia di non modificare i parametri dello schema predefiniti per garantire una sicurezza ottimale.

Tuttavia, in contesti specifici, potrebbe essere necessario modificare i filtri di sistema degli schemi incorporati. A tale scopo, segui i passaggi indicati di seguito:

1. Crea un&#39;estensione per lo schema integrato o apri un&#39;estensione esistente.
1. Aggiungere un elemento figlio **`<sysfilter name="<filter name>" _operation="delete"/>`** nell’elemento principale per ignorare il filtro nello stesso nello schema integrato.
1. Puoi aggiungere un nuovo filtro, come descritto nella sezione [Filtri di sistema](#system-filters) sezione.
