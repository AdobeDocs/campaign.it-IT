---
title: Impostazioni dei messaggi transazionali di Campaign
description: Impostazioni dei messaggi transazionali di Campaign
feature: Transactional Messaging
role: Admin, Developer
level: Intermediate, Experienced
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 2d10a8f4349b9e2405847fc6a3db1ed568c60387
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 5%

---

# Impostazioni dei messaggi transazionali

La messaggistica transazionale (Message Center, Centro messaggi) è un modulo Campaign progettato per la gestione dei messaggi attivati. Ulteriori informazioni sulla messaggistica transazionale in [questa sezione](../send/transactional.md).

Comprendere l’architettura dei messaggi transazionali in [questa pagina](../architecture/architecture.md#transac-msg-archi).

![](../assets/do-not-localize/speech.png) Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support) per installare e configurare i messaggi transazionali di Campaign nel tuo ambiente.

## Definire le autorizzazioni

Per creare nuovi utenti per le istanze di esecuzione del Centro messaggi ospitate su Adobe Cloud, contatta l’Assistenza clienti Adobe. Gli utenti del Centro messaggi sono operatori specifici che richiedono autorizzazioni dedicate per accedere alle cartelle &quot;Eventi in tempo reale&quot; (nmsRtEvent).

## Estensioni dello schema

Tutte le estensioni dello schema effettuate sugli schemi utilizzati da [Flussi di lavoro tecnici del Centro messaggi](#technical-workflows) nelle istanze di controllo o di esecuzione devono essere duplicate sulle altre istanze utilizzate dal modulo di messaggistica transazionale di Adobe Campaign.

## Inviare notifiche push transazionali

Se combinato con [Modulo del canale app mobile](../send/push.md), la messaggistica transazionale consente di inviare messaggi transazionali tramite notifiche su dispositivi mobili.

Per inviare notifiche push transazionali, devi eseguire le seguenti configurazioni:

1. Installa il **Canale app mobile** creare pacchetti nelle istanze di controllo ed esecuzione.

   >[!CAUTION]
   >
   >Controlla il contratto di licenza prima di installare un nuovo pacchetto integrato di Campaign.

1. Replicare il **App mobile** e le applicazioni mobili associate alle istanze di esecuzione.

Inoltre, l&#39;evento deve contenere i seguenti elementi:

* ID dispositivo mobile: **registrationId** per Android e **deviceToken** per iOS. Questo ID rappresenta l&#39;&quot;indirizzo&quot; a cui viene inviata la notifica.
* Il collegamento all’app mobile o alla chiave di integrazione (**uuid**), che consente di recuperare informazioni sulla connessione specifiche dell’applicazione.
* Il canale a cui verrà inviata la notifica (**wishChannel**): 41 per iOS e 42 per Android.
* Qualsiasi altro dato di personalizzazione.

Di seguito è riportato un esempio di configurazione di un evento per l’invio di notifiche push transazionali:

```
<SOAP-ENV:Envelope xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Body>
     <urn:PushEvent>
         <urn:sessiontoken>mc/</urn:sessiontoken>
         <urn:domEvent>

              <rtEvent wishedChannel="41" type="DELIVERY" registrationToken="2cefnefzef758398493srefzefkzq483974">
                <mobileApp _operation=”none” uuid="com.adobe.NeoMiles"/>
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

È possibile adattare le impostazioni della procedura guidata di distribuzione per configurare per quanto tempo i dati devono essere memorizzati nel database.

L&#39;eliminazione degli eventi viene eseguita automaticamente dal **Pulizia del database** flusso di lavoro tecnico. Questo flusso di lavoro elimina gli eventi ricevuti e memorizzati nelle istanze di esecuzione e gli eventi archiviati in un’istanza di controllo.

Utilizzare le frecce appropriate per modificare le impostazioni di eliminazione per **Eventi** (su un’istanza di esecuzione) e **Eventi archiviati** (su un&#39;istanza di controllo).


## Flussi di lavoro tecnici {#technical-workflows}

Devi accertarti che i flussi di lavoro tecnici sulle istanze di controllo ed esecuzione siano stati avviati prima di distribuire qualsiasi modello di messaggio transazionale.

Questi flussi di lavoro sono quindi accessibili dal **Amministrazione > Produzione > Centro messaggi** cartella.

### Controllare i flussi di lavoro delle istanze {#control-instance-workflows}

Nell’istanza di controllo è necessario creare un flusso di lavoro di archiviazione per ogni **[!UICONTROL Message Center execution instance]** conto esterno. Fai clic sul pulsante **[!UICONTROL Create the archiving workflow]** per creare e avviare il flusso di lavoro.

### Flussi di lavoro dell’istanza di esecuzione {#execution-instance-workflows}

Nelle istanze di esecuzione, devi avviare i seguenti flussi di lavoro tecnici:

* **[!UICONTROL Processing batch events]** (nome interno: **[!UICONTROL batchEventsProcessing]** ): questo flusso di lavoro ti consente di suddividere gli eventi batch in una coda prima che siano collegati a un modello di messaggio.
* **[!UICONTROL Processing real time events]** (nome interno: **[!UICONTROL rtEventsProcessing]** ): questo flusso di lavoro ti consente di suddividere gli eventi in tempo reale in una coda prima che siano collegati a un modello di messaggio.
* **[!UICONTROL Update event status]** (nome interno: **[!UICONTROL updateEventStatus]** ): questo flusso di lavoro ti consente di attribuire uno stato all’evento.

   Gli stati possibili dell’evento sono:

   * **[!UICONTROL Pending]**: l’evento è in coda. Non è ancora stato assegnato alcun modello di messaggio.
   * **[!UICONTROL Pending delivery]**: l’evento è in coda, gli è stato assegnato un modello di messaggio e viene elaborato dalla consegna.
   * **[!UICONTROL Sent]**: questo stato viene copiato dai log di consegna. Significa che la consegna è stata inviata.
   * **[!UICONTROL Ignored by the delivery]**: questo stato viene copiato dai log di consegna. Significa che la consegna è stata ignorata.
   * **[!UICONTROL Delivery failed]**: questo stato viene copiato dai log di consegna. Significa che la consegna è non è andata a buon fine.
   * **[!UICONTROL Event not taken into account]**: impossibile collegare l&#39;evento a un modello di messaggio. L’evento non viene elaborato.
