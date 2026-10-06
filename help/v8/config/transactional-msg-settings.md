---
title: Impostazioni dei messaggi transazionali di Campaign
description: Impostazioni dei messaggi transazionali di Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: d3b34fea-a110-482f-adb2-aae8d686bac8
    internal-label: Transactional messaging
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 4%
---
# Impostazioni dei messaggi transazionali {#mc-settings}

La messaggistica transazionale (Message Center) è un modulo di Campaign progettato per la gestione dei messaggi attivati. Ulteriori informazioni sulla messaggistica transazionale in [questa sezione](../send/transactional.md).

Scopri l&#39;architettura della messaggistica transazionale in [questa pagina](../architecture/architecture.md#transac-msg-archi).


>[!NOTE]
>
>In qualità di utente di Managed Cloud Services, [contatta Adobe](../start/campaign-faq.md#support) per installare e configurare la messaggistica transazionale di Campaign nel tuo ambiente.

## Definire le autorizzazioni {#mc-permissions}

Per creare nuovi utenti per le istanze di esecuzione del Centro messaggi ospitate su Adobe Cloud, contatta il tuo Adobe Transition Manager. Gli utenti del Centro messaggi sono operatori specifici che richiedono autorizzazioni dedicate per accedere alle cartelle &quot;Eventi in tempo reale&quot; (nmsRtEvent).

## Estensioni schema  {#mc-schema-ext}

Tutte le estensioni dello schema effettuate sugli schemi utilizzati dai [flussi di lavoro tecnici del Centro messaggi](#technical-workflows) su istanze di controllo o di esecuzione devono essere duplicate sulle altre istanze utilizzate dal modulo di messaggistica transazionale di Adobe Campaign.

## Inviare notifiche push transazionali {#mc-transactional-push}

In combinazione con il [modulo del canale app mobile](../send/push.md), la messaggistica transazionale consente di inviare messaggi transazionali tramite notifiche su dispositivi mobili.

Per inviare notifiche push transazionali, devi eseguire le seguenti configurazioni:

1. Installa il pacchetto **Canale app mobile** nelle istanze di controllo ed esecuzione.

   >[!CAUTION]
   >
   >Verifica il contratto di licenza prima di installare un nuovo pacchetto integrato di Campaign.

1. Replica il servizio **App mobile** e le applicazioni mobili associate nelle istanze di esecuzione.

Inoltre, l’evento deve contenere i seguenti elementi:

* ID dispositivo mobile: **registrationId** per Android e **deviceToken** per iOS. Questo ID rappresenta l’&quot;indirizzo&quot; a cui viene inviata la notifica.
* Collegamento all&#39;applicazione mobile o alla chiave di integrazione (**uuid**) che consente di recuperare le informazioni di connessione specifiche dell&#39;applicazione.
* Canale a cui verrà inviata la notifica (**wishedChannel**): 41 per iOS e 42 per Android.
* Qualsiasi altro dato di personalizzazione.

Di seguito è riportato un esempio di configurazione di un evento per l’invio di notifiche push transazionali:

```xml
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation="none" uuid="com.adobe.NeoMiles"/>
                <ctx>
                    <deliveryTime>1:30 PM</deliveryTime>
                    <url>http://www.adobe.com</url>
                </ctx>
              </rtEvent>

         </urn:domEvent>
     </urn:PushEvent>           
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

## Eliminare gli eventi {#purge-events}

È possibile adattare le impostazioni della procedura guidata di distribuzione per configurare la durata della memorizzazione dei dati nel database.

La rimozione degli eventi viene eseguita automaticamente dal flusso di lavoro tecnico **Database cleanup**. Questo flusso di lavoro elimina gli eventi ricevuti e memorizzati nelle istanze di esecuzione e gli eventi archiviati in un&#39;istanza di controllo.

Utilizzare le frecce appropriate per modificare le impostazioni di eliminazione per **Events** (in un&#39;istanza di esecuzione) e **Archived events** (in un&#39;istanza di controllo).


## Flussi di lavoro tecnici {#technical-workflows}

Prima di distribuire i modelli di messaggi transazionali, è necessario assicurarsi che i flussi di lavoro tecnici sulle istanze di controllo ed esecuzione siano stati avviati.

È possibile accedere a questi flussi di lavoro dalla cartella **Amministrazione > Produzione > Centro messaggi**.

### Controllare i flussi di lavoro delle istanze {#control-instance-workflows}

Nell&#39;istanza di controllo è necessario creare un flusso di lavoro di archiviazione per ogni account esterno **[!UICONTROL Message Center execution instance]**. Fare clic sul pulsante **[!UICONTROL Create the archiving workflow]** per creare e avviare il flusso di lavoro.

### Flussi di lavoro dell’istanza di esecuzione {#execution-instance-workflows}

Nelle istanze di esecuzione, devi avviare i seguenti flussi di lavoro tecnici:

* **[!UICONTROL Processing batch events]** (nome interno: **[!UICONTROL batchEventsProcessing]** ): questo flusso di lavoro consente di suddividere gli eventi batch in una coda prima che siano collegati a un modello di messaggio.
* **[!UICONTROL Processing real time events]** (nome interno: **[!UICONTROL rtEventsProcessing]** ): questo flusso di lavoro consente di suddividere gli eventi in tempo reale in una coda prima che vengano collegati a un modello di messaggio.
* **[!UICONTROL Update event status]** (nome interno: **[!UICONTROL updateEventStatus]** ): questo flusso di lavoro consente di attribuire uno stato all&#39;evento.

  I possibili stati degli eventi sono:

  * **[!UICONTROL Pending]**: l&#39;evento è in coda. Non è ancora stato assegnato alcun modello di messaggio.
  * **[!UICONTROL Pending delivery]**: l&#39;evento è in coda, gli è stato assegnato un modello di messaggio e viene elaborato dalla consegna.
  * **[!UICONTROL Sent]**: questo stato viene copiato dai log di consegna. Significa che la consegna è stata inviata.
  * **[!UICONTROL Ignored by the delivery]**: questo stato viene copiato dai log di consegna. Significa che la consegna è stata ignorata.
  * **[!UICONTROL Delivery failed]**: questo stato viene copiato dai log di consegna. Significa che la consegna è non è andata a buon fine.
  * **[!UICONTROL Event not taken into account]**: impossibile collegare l&#39;evento a un modello di messaggio. L’evento non verrà elaborato.
