---
title: Ambienti di interazione di Campaign
description: Scopri come creare ambienti per l’interazione con Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
source-git-commit: 213a10fea36b3b08c1dd8525084d212e191b2fc7
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 2%

---

# Utilizzare gli ambienti{#work-with-environments}

## Ambienti live e di progettazione{#live-design-environments}

L’interazione funziona con due tipi di ambienti di offerta:

* **[!UICONTROL Design]** ambienti di offerte che includono offerte in fase di modifica e che possono essere modificate. Queste offerte non hanno superato il ciclo di approvazione e non vengono consegnate ai contatti.
* **[!UICONTROL Live]** gli ambienti di offerte che includono offerte approvate mentre vengono presentate ai contatti. Le offerte in questo ambiente sono di sola lettura.

![](assets/offer_environments_overview_001.png)

Ogni **[!UICONTROL Design]** l&#39;ambiente è collegato a un **[!UICONTROL Live]** ambiente. Quando un&#39;offerta è completa, il suo contenuto e le sue regole di idoneità sono soggette a un ciclo di approvazione. Una volta completato questo ciclo, l&#39;offerta in questione viene automaticamente distribuita nel **[!UICONTROL Live]** ambiente. Da questo momento in poi sarà disponibile per la consegna.

Per impostazione predefinita, Campaign viene fornito con un **[!UICONTROL Design]** ambiente e **[!UICONTROL Live]** ambiente ad esso collegato. Entrambi gli ambienti sono preconfigurati per eseguire il targeting [tabella dei destinatari integrata](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>Per eseguire il targeting della tabella dei destinatari, è necessario utilizzare l’assistente di mappatura di destinazione per creare gli ambienti. [Ulteriori informazioni](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

I gestori di consegne possono visualizzare solo **[!UICONTROL Live]** e sfruttare le offerte per fornirle. I gestori di offerte possono visualizzare e utilizzare **[!UICONTROL Design]** e visualizzare **[!UICONTROL Live]** ambiente. [Ulteriori informazioni](interaction-operators.md)

## Creare un ambiente per le interazioni anonime{#create-an-offer-environment}

Per impostazione predefinita, Campaign viene fornito con un ambiente integrato per eseguire il targeting della tabella dei destinatari (offerte identificate). Per eseguire il targeting di un’altra tabella, ad esempio profili anonimi che visitano il sito web per interazioni in entrata, devi aggiornare la configurazione.

Segui i passaggi seguenti:

1. Sfoglia per **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**, fai clic con il pulsante destro del mouse sulla mappatura di destinazione che desideri utilizzare e seleziona **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. Fai clic su **[!UICONTROL Next]**, seleziona **[!UICONTROL Generate a storage schema for propositions]** e fai clic su **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Se l’opzione è già selezionata, deselezionala e ricontrolla.

1. Adobe Campaign crea due ambienti: **[!UICONTROL Design]** e **[!UICONTROL Live]** - con informazioni di targeting dalla mappatura di destinazione precedentemente abilitata. L’ambiente è preconfigurato con le informazioni di targeting.

Se hai attivato **[!UICONTROL Visitor]** mappatura, **[!UICONTROL Environment dedicated to incoming anonymous interactions]** viene selezionato automaticamente nel **[!UICONTROL General]** scheda .

Questa opzione consente di attivare funzioni specifiche per l’interazione anonima, in particolare durante la configurazione degli spazi di offerta dell’ambiente. Puoi anche configurare le opzioni che ti consentono di passare da un ambiente &quot;identificato&quot; a un ambiente &quot;anonimo&quot;.

Ad esempio, puoi collegare uno spazio di offerta nell’ambiente destinatario (contatto identificato) con uno spazio di offerta corrispondente a un ambiente visitatore (contatto non identificato). In questo modo, il contatto potrà ricevere diverse offerte a seconda che il contatto sia identificato o meno. Per ulteriori informazioni, consulta [Creazione di spazi di offerta](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>Per ulteriori informazioni sulle interazioni anonime su un canale in entrata, consulta [Interazioni anonime](anonymous-interactions.md).
