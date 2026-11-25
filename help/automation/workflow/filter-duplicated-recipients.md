---
product: campaign
title: Filtrare i destinatari duplicati
description: Scopri come filtrare i destinatari duplicati
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
TQID: 'https://experienceleague.adobe.com/jwnm0saAGOFD4FjCniKHBm6xDd8H2QggSy3UvrMAb-E'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: e13b3537d149f2bdad7e9dd66768837e5c4b595b
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 2%
---
# Filtrare i destinatari duplicati {#filtering-duplicated-recipients}



In questo esempio, vogliamo filtrare i destinatari che compaiono due o più volte in una consegna per recuperare i profili duplicati.

Per creare questo esempio, attieniti alla seguente procedura:

1. Trascinare e rilasciare un&#39;attività **[!UICONTROL Query]** in un flusso di lavoro e aprire l&#39;attività.
1. Fare clic su **[!UICONTROL Edit query]** e impostare la destinazione e le dimensioni filtro su **[!UICONTROL Recipients]**.

   ![Passaggio della dimensione di targeting e filtro dell&#39;attività Query con destinatari selezionati, condizioni di filtro evidenziate.](assets/query_recipients_1.png)

1. Definisci la seguente condizione di filtro per eseguire il targeting dei destinatari esistenti nel registro di consegna. Scegliere **Registro recapito destinatari (broadlog)** nella colonna **Espressione**, scegliere **esiste come** nella colonna **Operatore**.

   ![Passaggio filtro con la condizione Registri di consegna destinatari (broadLog) e l&#39;operatore esiste come.](assets/query_recipients_2.png)

1. Definisci la seguente condizione di filtro per eseguire il targeting della consegna. Scegliere **[!UICONTROL Internal name]** nella colonna Espressione e **[!UICONTROL equal to]** nella colonna Operatore.
1. Nella colonna Valore aggiungi il nome interno della consegna di destinazione.

   ![Condizione filtro in base al nome interno della consegna, uguale al valore summer_delivery_sales, in esistente ad esempio.](assets/query_recipients_3.png)

1. Con un operatore **[!UICONTROL AND]**, ripeti le stesse operazioni per eseguire il targeting di altre consegne.

   ![Esistono due condizioni, ad esempio quelle a cui si unisce And, con targeting summer_delivery_sales e summer_delivery_new_collection.](assets/query_recipients_4.png)

La transizione in uscita contiene i destinatari duplicati target delle consegne.
