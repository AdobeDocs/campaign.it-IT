---
title: Comprendere la descrizione dell’evento
description: Scopri come gli eventi di messaggistica transazionale vengono gestiti in Adobe Campaign Classic utilizzando i metodi SOAP
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
source-git-commit: c61f03252c7cae72ba0426d6edcb839950267c0a
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 0%

---


# Comprendere la descrizione dell’evento {#about-event-desc}

## Modello dati di messaggistica transazionale {#about-mc-datamodel}

La messaggistica transazionale si basa sul modello dati di Adobe Campaign e utilizza due tabelle separate aggiuntive. Queste tabelle, **NmsRtEvent** e **NmsBatchEvent**, contiene gli stessi campi e consente di gestire gli eventi in tempo reale da un lato e gli eventi batch dall’altro.

## Metodi SOAP {#soap-methods}

Questa sezione descrive i metodi SOAP associati agli schemi del modulo dei messaggi transazionali.

Due **PushEvent** o **PushEvents** I metodi SOAP sono collegati ai due **nms:rtEvent** e **nms:BatchEvent** dataschemas. È il sistema di informazioni che determina se un evento è un tipo &quot;batch&quot; o &quot;in tempo reale&quot;.

* **PushEvent** consente di inserire un singolo evento nel messaggio,
* **PushEvents** consente di inserire una serie di eventi nel messaggio.

Il percorso WSDL per l’accesso a entrambi i metodi è:

* **http://hostname/nl/jsp/schemawsdl.jsp?schema=nms:rtEvent** per accedere allo schema del tipo in tempo reale.
* **http://hostname/nl/jsp/schemawsdl.jsp?schema=nms:batchEvent** per accedere allo schema del tipo batch.

Entrambi i metodi contengono un **`<urn:sessiontoken>`** per l’accesso al modulo di messaggistica transazionale. È consigliabile utilizzare un metodo di identificazione tramite indirizzi IP attendibili. Per recuperare il token di sessione, esegui una chiamata SOAP di accesso, quindi un token get seguito da una disconnessione. Utilizza lo stesso token per diverse chiamate RT. Gli esempi inclusi in questa sezione utilizzano il metodo token di sessione che è quello consigliato.

Se utilizzi un server con carico bilanciato, puoi utilizzare l’autenticazione Utente/Password (a livello del messaggio RT). Esempio:

```
<PushEvent xmlns="urn:nms:rtEvent">
<sessiontoken>mc/PASSWORD</sessiontoken>
<domEvent>
<rtEvent wishedChannel="41" type="rt_MobileJourney_iOS_Push" registrationToken="c3ddc8aaecc24822df25d0f49865cca61ea3f86c61bfa53ae4d37294e37f4a1c" hashlpId="27EE7571EC14DBA23B9B5CC0EF79BB782DAECF4C03C88E5D92CC9B9DAC4E5DDA" correlationId="415b7593-4f6f-e911-811f-00505691247c" xmlns="">
<mobileApp uuid="236B24DC-C073-412F-8BCB-AC7207096258" _operation="none"/>
<ctx>...</ctx>
</rtEvent>
</domEvent>
</PushEvent>
```

La **PushEvent** è costituito da un **`<urn:domevent>`** che contiene l&#39;evento .

La **PushEvents** è costituito da un **`<urn:domeventcollection>`** che contiene eventi.

Esempio con PushEvent:

```
<urn:PushEvent>

 <sessiontoken>___921f9b38-72ac-49ad-b481-ab32973efc50</sessiontoken>
 
 <urn:domEvent>
 
   <rtEvent>
   
   ...
   
   </rtEvent>
 
 </urn:domEvent>

</urn:PushEvent>
```

>[!NOTE]
>
>In caso di chiamata al **PushEvents** per rispettare gli standard XML, è necessario aggiungere un elemento XML padre. Questo elemento XML inquadrerà i vari **`<rtevent>`** elementi contenuti nell’evento.

Esempio di utilizzo di PushEvents:

```
<urn:PushEvents>

 <sessiontoken>___921f9b38-72ac-49ad-b481-ab32973efc50</sessiontoken>
 
 <urn:domEventCollection>
 
   <Events>
   
     <rtEvent>... </rtEvent>
     
     <rtEvent>... </rtEvent>
     
     ...
   
   </Events>
 
 </urn:domEventCollection>

</urn:PushEvents>
```

La **`<rtevent>`** e **`<batchevent>`** gli elementi hanno un set di attributi e un elemento figlio obbligatorio: **`<ctx>`** per l’integrazione dei dati dei messaggi.

>[!NOTE]
>
>La **`<batchevent>`** consente di aggiungere l’evento alla coda &quot;batch&quot;. La **`<rtevent>`** aggiunge l’evento alla coda &quot;in tempo reale&quot;.

Gli attributi obbligatori del **`<rtevent>`** e **`<batchevent>`** gli elementi sono @type e @email. Il valore di @type deve essere lo stesso del valore di elenco dettagliato definito durante la configurazione dell’istanza di esecuzione. Questo valore ti consente di definire il modello da collegare al contenuto dell’evento durante la consegna.

`<rtevent> configuration example:`

```
<rtEvent type="order_confirmation" email="john.doe@domain.com" origin="eCommerce" wishedChannel="0" externalId="1242" mobilePhone="+33620202020"> 
```

In questo esempio vengono forniti due canali: l&#39;indirizzo e-mail e il numero di telefono cellulare. La **wishChannel** consente di selezionare il canale da utilizzare per trasformare l’evento in un messaggio. Il valore &quot;0&quot; corrisponde al canale e-mail, il valore &quot;1&quot; al canale mobile, ecc.

Se desideri posticipare la consegna di un evento, aggiungi la **[!UICONTROL scheduled]** campo seguito dalla data preferita. L’evento verrà trasformato in un messaggio in questa data.

È consigliabile compilare gli attributi @wishChannel e @emailFormat con valori numerici. La tabella delle funzioni che collega valori numerici ed etichette si trova nella descrizione dello schema dati.

>[!NOTE]
>
>Nella descrizione della **nms:rtEvent** e **nms:BatchEvent** schema dati.

La **`<ctx>`** contiene i dati del messaggio. Il relativo contenuto XML è aperto, il che significa che può essere configurato a seconda del contenuto da distribuire.

>[!NOTE]
>
>È importante ottimizzare il numero e la dimensione dei nodi XML contenuti nel messaggio per evitare di sovraccaricare i server durante la distribuzione.

Esempio di dati:

```
   <ctx>
               <client>
                        <firstname>John</firstname>
                        <lastname>Doe</lastname>
               </client>
               <action>
                         <type>Order confirmation</type>
                          <number>CN23453</number>
               </action>
               <orderdetails>
                          <article num="1">
                                   <name>Generic USB key</name>
                                   <price>20</price>
                           </article>
               </orderdetails>
    </ctx>
```

## Informazioni restituite dalla chiamata SOAP {#information-returned-by-the-soap-call}

Quando riceve un evento, Adobe Campaign genera un ID di ritorno univoco. ID della versione archiviata dell&#39;evento.

>[!IMPORTANT]
>
>Quando si ricevono chiamate SOAP, Adobe Campaign verifica il formato dell’indirizzo e-mail. Se un indirizzo e-mail non è formattato correttamente, viene restituito un errore.

* Esempio di identificatore restituito dal metodo quando l&#39;elaborazione dell&#39;evento ha esito positivo:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="http://xml.apache.org/xml-soap" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
      <SOAP-ENV:Body>
         <urn:PushEventResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns:urn="urn:nms:rtEvent">
            <plId xsi:type="xsd:long">72057594037935966</plId>
         </urn:PushEventResponse>
      </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

Se il valore dell’identificatore restituito è rigorosamente maggiore di zero, significa che l’evento è stato archiviato correttamente in Adobe Campaign.

Tuttavia, se l’elaborazione dell’evento non riesce, il metodo restituisce un messaggio di errore o un valore uguale a zero.

* Esempio di elaborazione di un evento non riuscito quando la query non contiene un login o l’operatore specificato non dispone dei diritti richiesti:

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
      <SOAP-ENV:Body>
         <SOAP-ENV:Fault>
            <faultcode>SOAP-ENV:Client</faultcode>
            <faultstring xsi:type="xsd:string">Error while reading parameters of method 'PushEvent' of service 'nms:rtEvent'.</faultstring>
            <detail xsi:type="xsd:string">Invalid login or password. Connection denied.</detail>
         </SOAP-ENV:Fault>
      </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

* Esempio di un evento non riuscito a causa di un errore nella query (la classificazione XML non è rispettata):

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
      <SOAP-ENV:Body>
         <SOAP-ENV:Fault>
            <faultcode>SOAP-ENV:Client</faultcode>
            <faultstring xsi:type="xsd:string">The XML SOAP message is invalid (service 'PushEvent', method 'nms:rtEvent').</faultstring>
            <detail xsi:type="xsd:string"><![CDATA[(16:8) : Expected end of tag 'rtevent'
   Error while parsing XML string '<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:urn="urn:nms:rtEvent">
      <soapenv:Header/>
      <soapenv:Body>
         <urn:PushEvent>
            <urn:sessiontoken>mc/</urn:sessiontoken>
            <urn:domEvent>
   <rtevent type="create_account" email="esther.hall@adobe.com" origin="eCommerce" wishedChannel="email" 
         externalId="1596" language="english" country="EN" emailFormat="2"
         mobilePhone="+447700123123">
     <ctx>
      <website name="eCommerce" url="http://www.eCo']]></detail>
         </SOAP-ENV:Fault>
      </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

* Esempio di evento non riuscito che ha restituito un identificatore zero (nome metodo errato):

   ```
   <SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns="http://xml.apache.org/xml-soap" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
      <SOAP-ENV:Body>
         <urn:PushEventResponse SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/" xmlns:urn="urn:nms:rtEvent">
            <plId xsi:type="xsd:long">0</plId>
         </urn:PushEventResponse>
      </SOAP-ENV:Body>
   </SOAP-ENV:Envelope>
   ```

