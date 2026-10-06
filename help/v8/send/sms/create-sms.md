---
title: Creare una consegna SMS
description: Scopri come creare una consegna SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 3b15eb3e-8625-4049-bf0d-327407ae5ea6
TQID: 'https://experienceleague.adobe.com/9hRirStfl9Rb2piTS3xY7C4Gb7zsUGeuoTxFFKgjf-8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 7%
---
# Creare la prima consegna SMS {#sms-delivery}

Per creare una nuova consegna SMS, segui i passaggi seguenti:

1. Crea una nuova consegna e seleziona il [modello di consegna SMS](sms-mid-sourcing.md#sms-delivery-template) creato per le invii SMS.

   ![](assets/sms_create.png){zoomable="yes"}

   I passaggi per la creazione della consegna sono descritti in [questa pagina](../../start/create-message.md).

<!--
 * For standalone instance,  [learn more here](sms-standalone-instance.md#sms-delivery-template).
* For mid-sourcing infrastructure,
-->

1. Rinomina la consegna nel campo **[!UICONTROL Label]** e aggiungi le informazioni nel campo **[!UICONTROL Delivery code]** e nell&#39;elenco **[!UICONTROL Nature]**, se necessario, per il tracciamento. Puoi anche aggiungere **[!UICONTROL Description]** alla consegna.

1. Fare clic sul pulsante **[!UICONTROL Continue]**. Ora nella consegna sono presenti tutte le impostazioni del modello.

1. È possibile archiviare il pulsante **[!UICONTROL Properties]** in modo che tutto sia configurato in base alle esigenze. [Ulteriori informazioni sulla scheda SMS](sms-delivery-settings.md#sms-tab)

   ![](assets/sms_settings.png){zoomable="yes"}

1. [Definisci il contenuto](sms-content.md) della consegna.

1. [Selezionare il pubblico](sms-audience.md).

I passaggi per definire un pubblico sono descritti in dettaglio in [questa pagina](../../audiences/create-audiences.md).

## Convalidare e inviare SMS {#sms-validate}

Dopo la creazione della consegna, puoi:

1. [Invia bozze](sms-proofs.md) per convalidare il rendering e il contenuto,

1. Quindi [invia al pubblico finale](sms-send.md).

## Monitorare e tenere traccia degli SMS {#sms-monitor}

Dopo l&#39;invio, [scopri come monitorare e tenere traccia dell&#39;SMS](sms-monitor.md).
