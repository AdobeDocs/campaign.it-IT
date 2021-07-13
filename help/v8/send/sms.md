---
product: Adobe Campaign
title: Inviare SMS con Adobe Campaign
description: Guida introduttiva all’SMS in Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Creare e inviare SMS

Utilizza Adobe Campaign per inviare messaggi SMS personalizzati.

↗️ Scopri come iniziare a utilizzare il canale SMS nella documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;}

>[!NOTE]
>
>Adobe Campaign consente inoltre di inviare notifiche push sui dispositivi mobili tramite l’opzione **Adobe Campaign Mobile App Channel (NMAC)**. Ulteriori informazioni in [questa sezione](push.md).

## Configurare il canale SMS

Per inviare a un telefono cellulare, è necessario:

* Un account esterno che specifica un connettore e il tipo di messaggio.

* Un modello di consegna in cui viene fatto riferimento a questo account esterno.

↗️ Scopri come configurare un canale SMS nella documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;}

Prima di iniziare a inviare SMS:

* Assicurati che i profili dei destinatari contengano almeno un telefono cellulare nel loro profilo.
* Rivedi le best practice per la consegna [Adobe Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target=&quot;_blank&quot;} che si applicano anche a Campaign v8.

Inoltre, devi avere familiarità con il protocollo e le impostazioni SMS. Scorri la connessione impostata tra Adobe Campaign e un provider SMPP in [questo documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

## Creare la prima consegna SMS

1. Per creare una nuova consegna, passa alla scheda **[!UICONTROL Campaigns]** , fai clic su **[!UICONTROL Deliveries]** e fai clic sul pulsante **[!UICONTROL Create]** sopra l’elenco delle consegne esistenti.

   ![](assets/delivery_step_1.png)

   ↗️ Per informazioni globali su come creare una consegna, consulta la documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

1. Seleziona un modello di consegna che fa riferimento all’account esterno pertinente per inviare consegne SMS.

   ![](assets/sms-template-list.png)

   ↗️ Scopri come creare un account esterno SMPP nella documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}

   ↗️ Scopri come creare un modello di consegna da distribuire ai dispositivi mobili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}

1. Identifica la consegna con un’etichetta, un codice e una descrizione.

1. Fai clic su **[!UICONTROL Continue]** per confermare e visualizzare la finestra di configurazione del messaggio.

1. Immetti il contenuto del messaggio nella sezione **[!UICONTROL Text content]** della procedura guidata, inclusi i campi di personalizzazione in base alle esigenze.

   ![](assets/sms-content.png)

1. Seleziona la popolazione target.

I passaggi chiave per creare e progettare un SMS sono descritti in dettaglio nella documentazione di Campaign Classic v7 :

* Creare un SMS

   ↗️ [Scopri come creare una consegna SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Progettazione del contenuto SMS

   ↗️ [Scopri come definire il contenuto SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* Selezionare il pubblico dell’e-mail

   ↗️ [Scopri come definire la popolazione target](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}

? I passaggi per definire un pubblico sono descritti in dettaglio in [questa pagina](../start/audiences.md).

## Test dell’SMS

Per visualizzare il rendering del messaggio con la relativa personalizzazione, fai clic su **[!UICONTROL Preview]** e seleziona un destinatario.

![](assets/sms-preview.png)

Per inviare una bozza, consulta le seguenti sezioni della documentazione di Campaign Classic v7:

* Convalidare una consegna e inviare bozze
↗️ [Scopri i passaggi chiave per convalidare una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* Aggiungi indirizzi di seed
↗️ [Informazioni sugli indirizzi di seed](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## Inviare e monitorare le consegne SMS

I passaggi chiave per inviare e monitorare un SMS sono descritti in dettaglio nella documentazione di Campaign Classic v7 :

* Inviare, monitorare e tenere traccia delle consegne SMS

   ↗️ [Scopri gli strumenti per inviare, monitorare e monitorare SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Risolvere i problemi relativi alle consegne SMS

   ↗️ [Informazioni sulla risoluzione dei problemi SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
