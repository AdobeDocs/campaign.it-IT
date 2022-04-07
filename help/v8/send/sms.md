---
title: Inviare SMS con Adobe Campaign
description: Guida introduttiva all’SMS in Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 9e07353859e63b71abb61526f40675f18837bc59
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 2%

---

# Creare e inviare SMS

Utilizza Adobe Campaign per inviare messaggi SMS personalizzati.

![](../assets/do-not-localize/book.png) Scopri come iniziare a utilizzare il canale SMS in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-channel.html){target=&quot;_blank&quot;}

>[!NOTE]
>
>Adobe Campaign consente inoltre di inviare notifiche push sui dispositivi mobili tramite le relative **Canale app Adobe Campaign Mobile (NMAC)** opzione . Ulteriori informazioni in [questa sezione](push.md).

## Configurare il canale SMS

Per inviare a un telefono cellulare, è necessario:

* Un account esterno che specifica un connettore e il tipo di messaggio.

* Un modello di consegna in cui viene fatto riferimento a questo account esterno.

![](../assets/do-not-localize/book.png)  Scopri come configurare un canale SMS in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#sending-messages){target=&quot;_blank&quot;}

Prima di iniziare a inviare SMS:

* Assicurati che i profili dei destinatari contengano almeno un telefono cellulare nel loro profilo.
* Rivedi Adobe Campaign Classic [Best practice per le consegne](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/delivery-bestpractices/delivery-best-practices.html?lang=en#sending-messages){target=&quot;_blank&quot;} che si applicano anche a Campaign v8.

Inoltre, devi avere familiarità con il protocollo e le impostazioni SMS. Scorri la connessione impostata tra Adobe Campaign e un provider SMPP in [presente documento](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-protocol.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

## Creare la prima consegna SMS

1. Per creare una nuova consegna, seleziona **[!UICONTROL Campaigns]** scheda , fai clic su **[!UICONTROL Deliveries]** e fai clic su **[!UICONTROL Create]** , sopra l’elenco delle consegne esistenti.

   ![](assets/delivery_step_1.png)

   ![](../assets/do-not-localize/book.png) Per informazioni globali su come creare una consegna, consulta [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-about-delivery-creation-steps.html?lang=en#sending-messages){target=&quot;_blank&quot;}.

1. Seleziona un modello di consegna che fa riferimento all’account esterno pertinente per inviare consegne SMS.

   ![](assets/sms-template-list.png)

   ![](../assets/do-not-localize/book.png) Scopri come creare un account esterno SMPP in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#creating-an-smpp-external-account){target=&quot;_blank&quot;}

   ![](../assets/do-not-localize/book.png) Scopri come creare un modello di consegna da consegnare ai dispositivi mobili in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up.html?lang=en#changing-the-delivery-template){target=&quot;_blank&quot;}

1. Identifica la consegna con un’etichetta, un codice e una descrizione.

1. Fai clic su **[!UICONTROL Continue]** per confermare e visualizzare la finestra di configurazione del messaggio.

1. Immetti il contenuto del messaggio nel **[!UICONTROL Text content]** della procedura guidata, inclusi i campi di personalizzazione in base alle esigenze.

   ![](assets/sms-content.png)

1. Seleziona la popolazione target.

I passaggi chiave per creare e progettare un SMS sono descritti in dettaglio nella documentazione di Campaign Classic v7 :

* Creare un SMS

   ![](../assets/do-not-localize/book.png) [Scopri come creare una consegna SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Progettazione del contenuto SMS

   ![](../assets/do-not-localize/book.png) [Scopri come definire il contenuto SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-create.html?lang=en#defining-the-sms-content){target=&quot;_blank&quot;}

* Selezionare il pubblico dell’e-mail

   ![](../assets/do-not-localize/book.png) [Scopri come definire la popolazione target](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target=&quot;_blank&quot;}

![](../assets/do-not-localize/glass.png) I passaggi per definire un pubblico sono descritti in dettaglio in [questa pagina](../start/audiences.md).

## Test dell’SMS

Per visualizzare il rendering del messaggio con la relativa personalizzazione, fai clic su **[!UICONTROL Preview]** e seleziona un destinatario.

![](assets/sms-preview.png)

Per inviare una bozza, consulta le seguenti sezioni della documentazione di Campaign Classic v7:

* Convalidare una consegna e inviare bozze
   ![](../assets/do-not-localize/book.png) [Scopri i passaggi chiave per convalidare una consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-validating-the-delivery.html){target=&quot;_blank&quot;}
* Aggiungere indirizzi seed
   ![](../assets/do-not-localize/book.png) [Scopri gli indirizzi di seed](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses.html){target=&quot;_blank&quot;}

## Inviare e monitorare le consegne SMS

I passaggi chiave per inviare e monitorare un SMS sono descritti in dettaglio nella documentazione di Campaign Classic v7 :

* Inviare, monitorare e tenere traccia delle consegne SMS

   ![](../assets/do-not-localize/book.png) [Scopri gli strumenti per inviare, monitorare e tracciare gli SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-send.html?lang=en#sending-messages){target=&quot;_blank&quot;}

* Risolvere i problemi relativi alle consegne SMS

   ![](../assets/do-not-localize/book.png) [Informazioni sulla risoluzione dei problemi relativi agli SMS](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/troubleshooting-sms.html?lang=en#sending-messages){target=&quot;_blank&quot;}
