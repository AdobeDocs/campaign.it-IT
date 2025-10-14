---
title: SMS in un’istanza autonoma
description: Scopri come configurare una consegna SMS in un’istanza autonoma
feature: SMS
role: User
hide: true
hidefromtoc: true
level: Beginner, Intermediate
exl-id: 7cebcde0-c5a8-4b9b-baba-27a62bebde91
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# SMS in un’istanza autonoma {#sms-standalone}

>[!IMPORTANT]
>
>Questa documentazione è per Adobe Campaign v8.7.2 e versioni successive.
>
>Per le versioni precedenti, leggere la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/it/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

In un’istanza autonoma, l’invio di una consegna SMS richiede:

1. Un **account esterno** che specifica un connettore e il tipo di messaggio, [ulteriori informazioni qui](#external-account)

1. Un **modello di consegna** in cui si fa riferimento a questo account esterno, [ulteriori informazioni qui](#sms-delivery-template)

## Creare un account esterno {#external-account}

>[!IMPORTANT]
>
>L’utilizzo dello stesso account e della stessa password per più account SMS esterni può causare conflitti e sovrapposizioni tra gli account. Ulteriori informazioni sulla [pagina per la risoluzione dei problemi SMS](smpp-connection.md#sms-troubleshooting).

Di seguito sono riportati i passaggi per creare l’account esterno SMPP:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**, fare clic sull&#39;icona **[!UICONTROL New]**

   ![](assets/sms_extaccount.png){zoomable="yes"}

1. Configura **[!UICONTROL Label]** e **[!UICONTROL Internal name]** dell&#39;account esterno. Definisci il tipo di account come **[!UICONTROL Routing]**, seleziona la casella **[!UICONTROL Enabled]**, seleziona **[!UICONTROL Mobile (SMS)]** per il canale e **[!UICONTROL Bulk delivery]** per la modalità di consegna.

   ![](assets/sms_extaccount_new.png){zoomable="yes"}

1. Nella scheda **[!UICONTROL Mobile]**, mantenere **[!UICONTROL Extended generic SMPP]** nell&#39;elenco a discesa **[!UICONTROL Connector]**.
La casella **[!UICONTROL Send messages through a dedicated process]** è selezionata per impostazione predefinita.

   ![](assets/sms_extaccount_connector.png){zoomable="yes"}

   Per impostare la connessione, è necessario compilare le schede di questo modulo. Per ulteriori informazioni sull&#39;account esterno SMPP[, vedere &#x200B;](smpp-external-account.md#smpp-connection-settings).


## Configurare il modello di consegna {#sms-delivery-template}

Per facilitare la creazione della consegna SMS, crea un modello di consegna SMS in cui si fa riferimento all’account esterno SMPP.

In **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, fai clic con il pulsante destro del mouse sul modello di consegna Mobile esistente e scegli **[!UICONTROL Duplicate]**.

![](assets/sms_template_duplicate.png){zoomable="yes"}

Modifica **[!UICONTROL Label]** e **[!UICONTROL Internal name]** del modello per riconoscerlo facilmente e fai clic sul pulsante **[!UICONTROL Properties]**.

![](assets/sms_template_name.png){zoomable="yes"}

Nella scheda **[!UICONTROL General]**, in **[!UICONTROL Routing]**, seleziona l’account esterno SMPP.

![](assets/sms_template_routing.png){zoomable="yes"}

Nella scheda **[!UICONTROL SMS]** è possibile aggiungere parametri facoltativi al modello.

![](assets/sms_template_properties.png){zoomable="yes"}

[Ulteriori informazioni sulla configurazione della scheda SMS](sms-delivery-settings.md).
