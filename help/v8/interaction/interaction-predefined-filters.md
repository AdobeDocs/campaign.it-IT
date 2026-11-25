---
title: Filtri predefiniti per l’offerta di interazione della campagna
description: Scopri come creare filtri predefiniti
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 092262c7-768c-4e86-9b2b-c52516f6a030
TQID: 'https://experienceleague.adobe.com/XWkWbgrMASz-9FfrXC23tTwiw54oQH5U4iWM9fa2FDQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 4%
---
# Creare filtri predefiniti{#creating-pre-defined-filters}

Crea filtri predefiniti per definire le regole di idoneità per la popolazione target, che possono essere facilmente riutilizzate durante la creazione dell’offerta. Sono specifici per ogni ambiente e tengono conto dei parametri dell’offerta.

>[!NOTE]
>
>L’interfaccia web di Adobe Campaign offre un’interfaccia intuitiva per gestire e personalizzare facilmente i filtri predefiniti in base alle tue esigenze specifiche. Crea una sola volta e salva per un utilizzo futuro. Per ulteriori informazioni sui filtri predefiniti per l&#39;interfaccia utente Web, consulta la [documentazione dell&#39;interfaccia utente Web di Adobe Campaign](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/predefined-filters){target=_blank}.


Per creare un filtro predefinito, applica il seguente processo:

1. Individuare la cartella **[!UICONTROL Administration]** e selezionare **[!UICONTROL Pre-defined offer filters]**.

   ![Offerte - struttura di progettazione con il nodo Filtri di offerta predefiniti selezionato in Amministrazione](assets/offer_filter_create_005.png)

1. Fai clic su **[!UICONTROL New]**.

   ![Elenco filtri offerte predefinito con il pulsante Nuovo evidenziato e un filtro di età elencato](assets/offer_filter_create_001.png)

1. Modifica l’etichetta per poter identificare il filtro in un secondo momento.

   ![Finestra di dialogo Filtro applicazioni con il campo Etichetta impostato su Canale e-mail](assets/offer_filter_create_002.png)

1. Seleziona il campo che verrà interessato dalla condizione di filtro.

   ![Seleziona una finestra di dialogo di espressione con il campo E-mail scelto tra i campi Destinatario](assets/offer_filter_create_003.png)

1. Seleziona un operatore e un valore, se necessario, quindi salva la query.

   ![La condizione del filtro nell&#39;espressione e-mail con l&#39;operatore impostato su non è vuota](assets/offer_filter_create_004.png)

1. Fare clic su **[!UICONTROL Preview]** per visualizzare il risultato del filtro.

   ![Scheda Anteprima del filtro del canale e-mail che elenca i destinatari corrispondenti al filtro](assets/offer_filter_create_006.png)
