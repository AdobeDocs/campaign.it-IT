---
title: Filtrare gli schemi di Campaign
description: Scopri come filtrare gli schemi di Campaign
exl-id: e8ad021c-ce2e-4a74-b9bf-a989d8879fd1
source-git-commit: 00a88cf9217faf32070a3cd34a2c1ae5243d9a6e
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---

# Filtrare gli schemi{#filter-schemas}

## Filtri di sistema {#system-filters}

Puoi filtrare l’accesso allo schema per utenti specifici, in base alle relative autorizzazioni. I filtri di sistema consentono di gestire le autorizzazioni di lettura e scrittura delle entità descritte negli schemi, utilizzando **readAccess** e **writeAccess** Parametri.

>[!NOTE]
>
>Questa restrizione si applica solo agli utenti non tecnici: un utente tecnico con le relative autorizzazioni o che utilizza un flusso di lavoro sarà in grado di recuperare e aggiornare i dati.

* **readAccess**: consente l&#39;accesso in sola lettura ai dati dello schema.

   **Avviso** - Tutte le tabelle collegate devono essere impostate con la stessa restrizione. Questa configurazione può influire sulle prestazioni.

* **writeAccess**: fornisce l&#39;accesso in scrittura ai dati dello schema.

Questi filtri vengono immessi nella pagina principale **elemento** per limitare l’accesso, è possibile creare il livello degli schemi e, come mostrato negli esempi seguenti.

* Limita autorizzazioni DI SCRITTURA

   In questo caso, il filtro viene utilizzato per impedire le autorizzazioni WRITE sullo schema per gli operatori senza l&#39;autorizzazione AMMINISTRAZIONE. Ciò significa che solo gli amministratori avranno le autorizzazioni di scrittura sulle entità descritte da questo schema.

   ```
   <sysFilter name="writeAccess">      
    <condition enabledIf="hasNamedRight('admin')=false" expr="FALSE"/>    
   </sysFilter>
   ```

* Limitare le autorizzazioni di LETTURA e SCRITTURA:

   In questo caso, il filtro viene utilizzato per disabilitare le autorizzazioni READ e WRITE sullo schema per tutti gli operatori. Solo il **interno** account, rappresentato dall&#39;espressione &quot;$(loginId)!=0&quot;, dispone di queste autorizzazioni.

   ```
   <sysFilter name="readAccess"> 
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   
   <sysFilter name="writeAccess">  
    <condition enabledIf="$(loginId)!=0" expr="FALSE"/>
   </sysFilter>
   ```

   Possibile **expr** i valori degli attributi utilizzati per definire la condizione sono TRUE o FALSE.

>[!NOTE]
>
>Se non viene specificato alcun filtro, tutti gli operatori avranno le autorizzazioni di lettura e scrittura per lo schema.

## Schemi incorporati Protect

Per impostazione predefinita, gli schemi incorporati sono accessibili solo con autorizzazioni WRITE per gli operatori con diritti di amministrazione:

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
* xtk:fusione
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
* xtk:stringhe
* xtk:xslt

>[!CAUTION]
>
>Autorizzazioni READ e WRITE per **xtk:sessionInfo** Lo schema è accessibile solo dall’account interno di un’istanza di Adobe Campaign.

## Modificare i filtri di sistema degli schemi incorporati

Gli schemi incorporati sono protetti per evitare problemi di compatibilità con le versioni precedenti. Adobe consiglia di non modificare i parametri dello schema predefiniti per garantire una protezione ottimale.

Tuttavia, in contesti specifici, potrebbe essere necessario modificare i filtri di sistema degli schemi incorporati. Per eseguire questa operazione, effettua le seguenti operazioni:

1. Crea un&#39;estensione per lo schema integrato o apri un&#39;estensione esistente.
1. Aggiungi un elemento figlio **`<sysfilter name="<filter name>" _operation="delete"/>`** nell&#39;elemento principale per ignorare il filtro nello stesso nello schema incorporato.
1. Puoi aggiungere un nuovo filtro, come descritto in [Filtri di sistema](#system-filters) sezione .
