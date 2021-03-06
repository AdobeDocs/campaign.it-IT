---
title: Impostazioni dei messaggi transazionali di Campaign
description: Impostazioni dei messaggi transazionali di Campaign
feature: Transactional Messaging
role: Data Engineer
level: Beginner
exl-id: 2899f627-696d-422c-ae49-c1e293b283af
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Impostazioni dei messaggi transazionali

![](../assets/do-not-localize/speech.png)  Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support) per installare e configurare i messaggi transazionali di Campaign nel tuo ambiente.

![](../assets/do-not-localize/glass.png) Le funzionalità di messaggistica transazionale sono descritte in [questa sezione](../send/transactional.md).

![](../assets/do-not-localize/glass.png) Comprendere l’architettura dei messaggi transazionali in [questa pagina](../architecture/architecture.md).

## Definire le autorizzazioni

Per creare nuovi utenti per le istanze di esecuzione del Centro messaggi ospitate su Adobe Cloud, contatta l’Assistenza clienti Adobe. Gli utenti del Centro messaggi sono operatori specifici che richiedono autorizzazioni dedicate per accedere alle cartelle &quot;Eventi in tempo reale&quot; (nmsRtEvent).

## Estensioni dello schema

Tutte le estensioni dello schema effettuate sugli schemi utilizzati da **Flussi di lavoro tecnici del Centro messaggi** nelle istanze di controllo o di esecuzione devono essere duplicate sulle altre istanze utilizzate dal modulo di messaggistica transazionale di Adobe Campaign.

![](../assets/do-not-localize/book.png) Ulteriori informazioni sui flussi di lavoro tecnici del Centro messaggi in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/configure-transactional-messaging/additional-configurations.html#technical-workflows)

## Inviare notifiche push transazionali

Se combinato con il modulo del canale dell’app mobile, la messaggistica transazionale consente di inviare messaggi transazionali tramite notifiche su dispositivi mobili.

![](../assets/do-not-localize/book.png) Il canale app mobile è descritto in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html?lang=en#sending-messages).

Per inviare notifiche push transazionali, devi eseguire le seguenti configurazioni:

1. Installa il **Canale app mobile** creare pacchetti nelle istanze di controllo ed esecuzione.

   >[!CAUTION]
   >
   >Controlla il contratto di licenza prima di installare un nuovo pacchetto integrato di Campaign.

1. Replicare il **App mobile** e le applicazioni mobili associate alle istanze di esecuzione.

Affinché Campaign possa inviare notifiche push transazionali, l’evento deve contenere i seguenti elementi:

* ID dispositivo mobile: **registrationId** per Android e **deviceToken** per iOS. Questo ID rappresenta l&#39;&quot;indirizzo&quot; a cui verrà inviata la notifica.
* Il collegamento all’app mobile o alla chiave di integrazione (**uuid**), che consente di recuperare informazioni sulla connessione specifiche dell’applicazione.
* Il canale a cui verrà inviata la notifica (**wishChannel**): 41 per iOS e 42 per Android.
* Altri dati da sfruttare per la personalizzazione.

Di seguito è riportato un esempio di evento contenente queste informazioni:

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
