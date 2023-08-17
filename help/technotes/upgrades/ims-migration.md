---
title: Migrazione degli utenti tecnici alla console Adobe Developer
description: Scopri come migrare gli operatori tecnici di Campaign all’account tecnico nella console Adobe Developer
source-git-commit: b71197027d9521fd648a0c2657b6b76a1aa7fc9a
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 0%

---

# Migrazione degli operatori tecnici di Campaign alla console Adobe Developer {#migrate-tech-users-to-ims}

A partire da Campaign v8.5, il processo di autenticazione per Campaign v8 viene migliorato. Gli operatori tecnici devono utilizzare [Sistema Adobe Identity Management (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} per connettersi a Campaign. Un operatore tecnico è un profilo utente di Campaign creato esplicitamente per l’integrazione API. Questo articolo descrive i passaggi necessari per migrare un operatore tecnico all’account tecnico nella console Adobe Developer.

## Cosa è cambiato?{#ims-changes}

Gli utenti abituali di Campaign si connettono già alla console Adobe Campaign utilizzando il proprio Adobe ID, tramite Adobe Identity Management System (IMS). Come parte del tentativo di rafforzare la sicurezza e il processo di autenticazione, l’applicazione client di Adobe Campaign ora chiama le API di Campaign direttamente utilizzando il token dell’account tecnico IMS.

Ulteriori informazioni sul nuovo processo di autenticazione server-to-server in [Documentazione della console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.

Questa modifica è applicabile a partire da Campaign v8.5 e sarà **obbligatorio** avvio di Campaign v8.6.


## Sei interessato da questo problema?{#ims-impacts}

Se utilizzi le API di Campaign, devi migrare gli operatori tecnici alla console Adobe Developer come descritto di seguito.

## Come effettuare la migrazione?{#ims-migration-procedure}

### Prerequisiti{#ims-migration-prerequisites}

Prima di iniziare la migrazione, devi contattare il rappresentante Adobe in modo che i team tecnici Adobe possano migrare i gruppi di operatori e i diritti denominati esistenti ad Adobe Identity Management System (IMS).

### Passaggio 1: creare/aggiornare il progetto Campaign in Adobe Developer Console{#ims-migration-step-1}

Le integrazioni vengono create come parte di un **Progetto** nella console Adobe Developer. Ulteriori informazioni sui progetti in [Documentazione della console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/projects/){target="_blank"}.

In qualità di utente di Campaign v8, dovresti già disporre di un progetto nella console Adobe Developer. In caso contrario, devi creare un progetto. I passaggi per creare un progetto sono descritti in dettaglio [nella documentazione della console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/getting-started/){target="_blank"}.

Dopo aver effettuato l’accesso al progetto Campaign, puoi aggiungere servizi quali API, Adobe Campaign e API di gestione I/O. Per questa migrazione, devi aggiungere le seguenti API al progetto: **API di gestione I/O** e **Adobe Campaign**.

![](assets/do-not-localize/ims-products-and-services.png)


### Passaggio 2: aggiungere un’API al progetto utilizzando l’autenticazione server-to-server{#ims-migration-step-2}

Una volta creato il progetto nella console Adobe Developer, aggiungi un’API che utilizza l’autenticazione server-to-server. Scopri come impostare le credenziali server-to-server OAuth in [Documentazione della console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/){target="_blank"}.

Una volta stabilita la connessione dell’API, puoi accedere alle credenziali appena generate, inclusi ID client e Segreto client, nonché generare un token di accesso.

### Passaggio 3: aggiungere il profilo di prodotto al progetto{#ims-migration-step-3}

Ora puoi aggiungere al progetto il tuo profilo di prodotto Campaign, come descritto di seguito:

1. Apri l’API di Adobe Campaign.
1. Fai clic su **Modificare i profili di prodotto** pulsante

   ![](assets/do-not-localize/ims-edit-api.png)

1. Assegna all’API tutti i profili di prodotto rilevanti, ad esempio &quot;messagecenter&quot;, e salva le modifiche.
1. Accedi a **Dettagli delle credenziali** del progetto e copia il file **E-mail account tecnico** valore.

### Passaggio 4: aggiornare l’operatore tecnico nella console client {#ims-migration-step-4}


Questo passaggio è necessario solo se per questo operatore sono stati definiti autorizzazioni di cartella o diritti denominati specifici (non tramite il gruppo dell&#39;operatore ).

Ora devi aggiornare l’operatore tecnico appena creato nella console client di Adobe Campaign. È necessario applicare al nuovo operatore tecnico le autorizzazioni esistenti per la cartella dell’operatore tecnico.
Per aggiornare questo operatore, effettua le seguenti operazioni:

1. Dall’Explorer della console client di Campaign, passa alla **Amministrazione > Gestione degli accessi > Operatori**.
1. Accedi all’operatore tecnico esistente utilizzato per le API.
1. Individua le autorizzazioni della cartella e controlla i diritti.
1. Applica le stesse autorizzazioni all’operatore tecnico appena creato. L’e-mail di questo operatore è **E-mail account tecnico** valore copiato in precedenza.
1. Salva le modifiche.


>[!CAUTION]
>
>Il nuovo operatore tecnico deve aver effettuato almeno una chiamata API per essere aggiunto alla console client di Campaign.
>

<!--

>[!CAUTION]
>
>After updating the authentication type for the technical operator, all API integrations with this technical operator will stop working. You must [update your API integrations](#ims-migration-step-6). 

To update the technical operator authentication mode to IMS, follow these steps:

1. From Campaign Client Console explorer, browse to the **Administration > Access Management > Operators**.
1. Edit the existing technical operator used for APIs.
1. Replace the **Name (login)** of this technical operator by the technical account email retrieved earlier.
1. Browse to the **Edit** button on the top left beside **File**, and select **Edit the XML source**.
1. Update the authentication mode to `ims`, as follows:

    ```javascript
    <operator 
    ...
        <access authenticationType="ims" ...
        ...
        </access>
    ...
    </operator>
    ```

1. Save your changes.

You can also update the technical operator programmatically, using SQL scripts or Campaign APIs. These modes help you automate the steps which update operator's name with associated Technical account email address and/or authentication type. 

* Use the following **SQL Script** to replace operator's name with associated email:

    ```sql
    UPDATE xtkoperator
    SET sauthenticationtype = 'ims',
            sname = '{email}'
    WHERE sname = '{name}' AND itype = 0;
    ```

* Use the following `queryDef.ExecuteQuery` **Campaign API** to fetch id of an operator for given technical operator:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <ExecuteQuery xmlns="urn:xtk:queryDef">
                <sessiontoken>{session_token}</sessiontoken>
                <entity>
                    <queryDef schema="xtk:operator" operation="select">
                        <select>
                            <node expr="@id"/>
                        </select>
                        <where>
                            <condition expr="@name='{name}'"/>
                            <condition expr="@type=0"/>
                        </where>
                    </queryDef>
                </entity>
            </ExecuteQuery>
        </soap:Body>
    </soap:Envelope>
    ```

* Use the following `session.Write` **Campaign API** to update name with given technical account email address:

    ```javascript
    <?xml version="1.0" encoding="utf-8"?>
    <soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
        <soap:Body>
            <Write xmlns="urn:xtk:session">
                <sessiontoken>{session_token}</sessiontoken>
                <domDoc xsi:type='ns:Element' SOAP-ENV:encodingStyle='http://xml.apache.org/xml-soap/literalxml'>
                    <operator _operation="update" id="{id}" name="{email}" xtkschema="xtk:operator">
                        <access authenticationType="ims" />
                    </operator>
                </domDoc>
            </Write>
        </soap:Body>
    </soap:Envelope>
    ```
-->

### Passaggio 5: convalidare la configurazione {#ims-migration-step-5}

Per provare la connessione, segui i passaggi descritti in [Guida alle credenziali della console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/#generate-access-tokens){target="_blank"} per generare un token di accesso e copiare il comando cURL di esempio fornito.


### Passaggio 6: aggiornare le integrazioni API di terze parti {#ims-migration-step-6}

Devi aggiornare le integrazioni API con i sistemi di terze parti.

Per ulteriori dettagli sui passaggi di integrazione dell’API, tra cui un codice di esempio per un’integrazione fluida, consulta [Documentazione sull’autenticazione della console Adobe Developer](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/){target="_blank"}.


### Passaggio 7 - Rimuovere il vecchio operatore tecnico {#ims-migration-step-7}


Dopo la migrazione di tutta l’integrazione di API/codice personalizzato con l’utente dell’account tecnico. Puoi eliminare il vecchio operatore tecnico dalla console client di Campaign.

### Esempi di chiamate Soap{#ims-migration-samples}

Una volta completato e convalidato il processo di migrazione, le chiamate Soap vengono aggiornate come segue:

* Prima della migrazione

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken>SESSION_TOKEN</urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```

* Dopo la migrazione

  ```sql
  POST /nl/jsp/soaprouter.jsp HTTP/1.1
  Host: localhost:8080
  Content-Type: application/soap+xml;
  SOAPAction: "nms:rtEvent#PushEvent"
  charset=utf-8
  Authorization: Bearer <IMS_Technical_Token_Token>
  
  <?xml version="1.0" encoding="utf-8"?>  <soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
  <soapenv:Header/>
  <soapenv:Body>
      <urn:PushEvent>
          <urn:sessiontoken></urn:sessiontoken>
          <urn:domEvent>
              <!--You may enter ANY elements at this point-->
              <rtEvent type="type" email="name@domain.com"/>
          </urn:domEvent>
      </urn:PushEvent>
  </soapenv:Body>
  </soapenv:Envelope>
  ```
