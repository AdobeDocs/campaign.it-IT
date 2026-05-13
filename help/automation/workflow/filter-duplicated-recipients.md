---
product: campaign
title: Filtrare i destinatari duplicati
description: Scopri come filtrare i destinatari duplicati
feature: Workflows
role: User
version: Campaign v8, Campaign Classic v7
exl-id: cfa1f45c-e1ac-4055-996c-6e8d041889bb
TQID: https://experienceleague.adobe.com/jwnm0saAGOFD4FjCniKHBm6xDd8H2QggSy3UvrMAb-E
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 147
ht-degree: 4%

---

# Filtrare i destinatari duplicati {#filtering-duplicated-recipients}



In questo esempio, vogliamo filtrare i destinatari che compaiono due o più volte in una consegna per recuperare i profili duplicati.

Per creare questo esempio, attieniti alla seguente procedura:

1. Trascinare e rilasciare un&#39;attività **[!UICONTROL Query]** in un flusso di lavoro e aprire l&#39;attività.
1. Fare clic su **[!UICONTROL Edit query]** e impostare la destinazione e le dimensioni filtro su **[!UICONTROL Recipients]**.

   ![](assets/query_recipients_1.png)

1. Definisci la seguente condizione di filtro per eseguire il targeting dei destinatari esistenti nel registro di consegna. Scegliere **Registro recapito destinatari (broadlog)** nella colonna **Espressione**, scegliere **esiste come** nella colonna **Operatore**.

   ![](assets/query_recipients_2.png)

1. Definisci la seguente condizione di filtro per eseguire il targeting della consegna. Scegliere **[!UICONTROL Internal name]** nella colonna Espressione e **[!UICONTROL equal to]** nella colonna Operatore.
1. Nella colonna Valore aggiungi il nome interno della consegna di destinazione.

   ![](assets/query_recipients_3.png)

1. Con un operatore **[!UICONTROL AND]**, ripeti le stesse operazioni per eseguire il targeting di altre consegne.

   ![](assets/query_recipients_4.png)

La transizione in uscita contiene i destinatari duplicati target delle consegne.
