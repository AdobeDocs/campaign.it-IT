---
title: Nuove API di Campaign v8
description: Nuove API di Campaign v8
feature: Architecture, API, FFDA
role: Developer
level: Intermediate
exl-id: dd822f88-b27d-4944-879c-087f68e79825
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 2%

---

# API specifiche per campagne FFDA{#gs-new-api}

Nell&#39;ambito di una [Distribuzione aziendale (FFDA)](enterprise-deployment.md), Campaign v8 è dotato di due API specifiche per la gestione dei dati tra il database locale di Campaign e il database Cloud. I prerequisiti per utilizzarli sono quelli di abilitare il meccanismo di staging sullo schema. [Ulteriori informazioni](staging.md)

* API di acquisizione: **xtk.session.ingest**

  Questa API è dedicata solo a Data Insert. [Ulteriori informazioni](#data-insert-api)

* API di aggiornamento/eliminazione dati: **xtk.session.ingestExt**

  Questa API viene utilizzata per aggiornare o eliminare i dati. [Ulteriori informazioni](#data-update-api)

Un flusso di lavoro integrato dedicato sincronizzerà i dati nel database cloud.

## Inserisci dati{#data-insert-api}

Il **xtk.session.ingest** L’API è dedicata solo a Data Insert. Nessun aggiornamento/eliminazione.

### Inserisci senza riconciliazione{#insert-no-reconciliation}

**In un flusso di lavoro**

Utilizza il seguente codice in una **Codice JavaScript** attività per inserire dati nel database Cloud senza riconciliazione:

```
var xmlStagingSampleTable = <sampleTableStg
                                testcol1="testValue1"
                                testcol2="testValue2"
                                xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Una volta eseguito il flusso di lavoro, la tabella di staging viene alimentata come previsto.

**Da una chiamata SOAP**

1. Ottieni il token di autenticazione.
1. Attiva l’API. Il payload è:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:Ingest>
           <urn:sessiontoken>___xxxxxxx-xxxx-xxx-xxx-xxxxxxxxxxx</urn:sessiontoken>
           <urn:domDoc>
               <sampleTableStg
                   testcol1="Test Value 1 (from SOAP)"
                   testcol2="Test Value 2 (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:Ingest>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. UUID viene rimandato alla risposta SOAP:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string">e1e7c8b3-6f79-44da-a72d-49ed0f73db2c</pstrSUuids>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Di conseguenza, la tabella di staging viene alimentata come previsto.

![](assets/no-reconciliation.png)

### Inserisci con riconciliazione

**In un flusso di lavoro**

Utilizza il seguente codice in una **Codice JavaScript** attività per inserire dati nel database Cloud con riconciliazione:

```
var xmlStagingSampleTable = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue1"
                              testcol2="testValue2"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;         
strUuid = xtk.session.Ingest(xmlStagingSampleTable);
logInfo(strUuid);
```

Una volta eseguito il flusso di lavoro, la tabella di staging viene alimentata come previsto.

![](assets/with-reconciliation.png)


**Da una chiamata SOAP**

1. Ottieni il token di autenticazione.
1. Attiva l’API. Il payload è:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
     <urn:Ingest>
        <urn:sessiontoken>___5e71f4bf-d38a-4ba8-ac15-35a958f7f138</urn:sessiontoken>
        <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                testcol1="Test Value 1 (from SOAP)"
                testcol2="Test Value 2 (from SOAP)"
                xtkschema="dem:sampleTableStg">
            </sampleTableStg>
        </urn:domDoc>
     </urn:Ingest>
    </soapenv:Body>
   </soapenv:Envelope>
   ```

1. In questo caso, l’UUID non viene fornito nuovamente alla risposta perché è stato fornito nel payload. La risposta è:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default">
           <pstrSUuids xsi:type="xsd:string"/>
       </IngestResponse>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Di conseguenza, la tabella di staging viene alimentata come previsto.

## Aggiornare o eliminare dati{#data-update-api}

Il **xtk.session.IngestExt** L’API è ottimizzata per l’aggiornamento/eliminazione dei dati. Solo per inserimento, preferisci **xtk.session.ingest**. Inserisci funziona indipendentemente dal fatto che la chiave del record non sia nella tabella di gestione temporanea.

### Inserisci/aggiorna

**In un flusso di lavoro**

Utilizza il seguente codice in una **Codice JavaScript** attività per aggiornare i dati nel database Cloud:

```
var xmlStagingRecipient = <sampleTableStg  _key="@id" id="ABC12345"
                              testcol1="testValue A (updated)"
                              testcol2="testValue B (updated)"
                              xtkschema="dem:sampleTableStg">
                            </sampleTableStg>;
xtk.session.IngestExt(xmlStagingRecipient);
```

Una volta eseguito il flusso di lavoro, la tabella di staging viene aggiornata come previsto.

![](assets/updated-data.png)

**Da una chiamata SOAP**

1. Ottieni il token di autenticazione.
1. Attiva l’API. Il payload è:

   ```
   <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:xtk:session">
   <soapenv:Header/>
   <soapenv:Body>
       <urn:IngestExt>
           <urn:sessiontoken>___444cd168-a1e2-4fb6-a2a8-73be9f133489</urn:sessiontoken>
           <urn:domDoc>
           <sampleTableStg  _key="@id" id="ABDCD321"
                   testcol1="Test Value E (from SOAP)"
                   testcol2="Test Value F (from SOAP)"
                   xtkschema="dem:sampleTableStg">
               </sampleTableStg>
           </urn:domDoc>
       </urn:IngestExt>
   </soapenv:Body>
   </soapenv:Envelope>
   ```

1. La risposta SOAP è:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="urn:wpp:default" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
       <IngestExtResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns="urn:wpp:default"/>
   </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Di conseguenza, la tabella di gestione temporanea viene aggiornata come previsto.

## Gestione abbonamenti {#sub-apis}

La gestione degli abbonamenti in Campaign è descritta in [questa pagina](../start/subscriptions.md).

L’inserimento di dati di abbonamento e di annullamento dell’abbonamento si basa sul [Meccanismo di staging](staging.md) nel database locale di Campaign. Le informazioni del sottoscrittore sono temporaneamente memorizzate nelle tabelle intermedie nel database locale e il flusso di lavoro di sincronizzazione invia tali dati dal database locale al database cloud. Di conseguenza, i processi di abbonamento e annullamento dell’abbonamento sono **asincrono**. Le richieste di consenso e rinuncia vengono elaborate ogni ora tramite un flusso di lavoro tecnico specifico. [Ulteriori informazioni](replication.md#tech-wf)


**Argomenti correlati**

* [JSAPI campagna](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html){target="_blank"}
