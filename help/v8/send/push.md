---
solution: Campaign v8
product: Adobe Campaign
title: Inviare notifiche push con Adobe Campaign
description: Guida introduttiva alla notifica push in Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 1%

---

# Creare e inviare notifiche push

Le consegne di app mobili ti consentono di inviare notifiche ai sistemi iOS e Android.

Per inviare notifiche push in Adobe Campaign, devi:

1. Configurare l’ambiente Campaign
1. Crea un servizio di informazioni di tipo app mobile per la tua app mobile.
1. Aggiungi al servizio le versioni iOS e Android dell&#39;applicazione.
1. Crea una consegna per iOS e Android.

:arrow_Upper_right: Scopri come iniziare a utilizzare l’app mobile nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/about-mobile-app-channel.html)

## Integrare con Adobe SDK

### Integrare Campaign SDK

L’SDK di Campaign facilita l’integrazione dell’app mobile nella piattaforma Adobe Campaign.

:arrow_Upper_right: Scopri come integrare Campaign SDK con la tua app nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/integrating-campaign-sdk-into-the-mobile-application.html?lang=en#loading-campaign-sdk)

### Configurare l’estensione Campaign in Launch

Puoi integrare l’SDK di Adobe Experience Platform Launch con Campaign, sfruttando l’estensione Campaign Classic.

:arrow_Upper_right: Ulteriori informazioni nella [documentazione Adobe Mobile SDK](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaignclassic)

## Configurare le impostazioni dell’app in Campaign

Devi definire le impostazioni delle app iOS e Android in Adobe Campaign.

:arrow_Upper_right: Le linee guida per la configurazione di iOS sono descritte in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application.html?lang=en#sending-messages)

:arrow_Upper_right: Le linee guida per la configurazione di Android sono illustrate in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html?lang=en#sending-messages)

## Creare la prima notifica push

:arrow_Upper_right: Scopri come creare le prime notifiche push nella documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/creating-notifications.html?lang=en#sending-notifications-on-ios)


>[!CAUTION]
>
>Con la registrazione mobile v8 di Campaign ora è **asincrono**. [Ulteriori informazioni](../dev/staging.md).
