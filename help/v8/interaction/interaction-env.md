---
title: Utilizzare gli ambienti di interazione di Campaign
description: Scopri come creare ambienti per l’interazione con Campaign
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 31f38870-1781-4185-9022-d4fd6a31c94a
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---

# Utilizzare gli ambienti{#work-with-environments}

## Ambienti di progettazione e live{#live-design-environments}

L’interazione funziona con due tipi di ambienti di offerta:

* **[!UICONTROL Design]** ambienti di offerta che includono offerte in fase di modifica che possono essere modificate. Queste offerte non sono state sottoposte al ciclo di approvazione e non vengono consegnate ai contatti.
* **[!UICONTROL Live]** ambienti di offerta che includono offerte approvate quando vengono presentate ai contatti. Le offerte in questo ambiente sono di sola lettura.

![](assets/offer_environments_overview_001.png)

Ogni ambiente **[!UICONTROL Design]** è collegato a un ambiente **[!UICONTROL Live]**. Quando un’offerta è completa, il suo contenuto e le relative regole di idoneità sono soggetti a un ciclo di approvazione. Al termine del ciclo, l&#39;offerta interessata viene distribuita automaticamente nell&#39;ambiente **[!UICONTROL Live]**. Da questo momento, sarà disponibile per la consegna.

Per impostazione predefinita, Campaign dispone di un ambiente **[!UICONTROL Design]** e di un ambiente **[!UICONTROL Live]** collegati. Entrambi gli ambienti sono preconfigurati per la destinazione della [tabella dei destinatari incorporata](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>Per eseguire il targeting della tabella dei destinatari, è necessario utilizzare l’assistente per la mappatura di destinazione per creare gli ambienti. [Ulteriori informazioni](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

I responsabili della consegna possono solo visualizzare l&#39;ambiente **[!UICONTROL Live]** e sfruttare le offerte per distribuirle. I responsabili delle offerte possono visualizzare e utilizzare l&#39;ambiente **[!UICONTROL Design]** e visualizzare l&#39;ambiente **[!UICONTROL Live]**. [Ulteriori informazioni](interaction-operators.md)

## Creare un ambiente per le interazioni anonime{#create-an-offer-environment}

Per impostazione predefinita, Campaign viene fornito con un ambiente integrato per eseguire il targeting della tabella dei destinatari (offerte identificate). Per eseguire il targeting di un’altra tabella, ad esempio i profili anonimi che visitano il sito web per interazioni in entrata, devi aggiornare la configurazione.

Segui i passaggi seguenti:

1. Selezionare **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**, fare clic con il pulsante destro del mouse sulla mappatura di destinazione che si desidera utilizzare e selezionare **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. Fare clic su **[!UICONTROL Next]**, selezionare l&#39;opzione **[!UICONTROL Generate a storage schema for propositions]** e fare clic su **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Se l’opzione è già selezionata, deselezionala e ricontrolla.

1. Adobe Campaign crea due ambienti - **[!UICONTROL Design]** e **[!UICONTROL Live]** - con informazioni di targeting dalla mappatura di destinazione precedentemente abilitata. L’ambiente è preconfigurato con le informazioni di targeting.

Se hai attivato la mappatura **[!UICONTROL Visitor]**, la casella **[!UICONTROL Environment dedicated to incoming anonymous interactions]** viene selezionata automaticamente nella scheda **[!UICONTROL General]** dell&#39;ambiente.

Questa opzione consente di attivare funzioni specifiche di interazione anonima, in particolare durante la configurazione degli spazi dell’offerta dell’ambiente. Puoi anche configurare le opzioni che ti consentono di passare da un ambiente &quot;identificato&quot; a un ambiente &quot;anonimo&quot;.

Ad esempio, puoi collegare uno spazio dell’offerta in un ambiente destinatario (contatto identificato) con uno spazio dell’offerta che corrisponda a un ambiente visitatore (contatto non identificato). In questo modo, al contatto saranno rese disponibili offerte diverse a seconda che il contatto sia stato identificato o meno. Per ulteriori informazioni, consulta [Creazione di spazi dell&#39;offerta](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>Per ulteriori informazioni sulle interazioni anonime su un canale in entrata, fare riferimento a [Interazioni anonime](anonymous-interactions.md).
