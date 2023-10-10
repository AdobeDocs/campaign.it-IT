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
* **[!UICONTROL Live]** ambienti di offerta che includono le offerte approvate quando vengono presentate ai contatti. Le offerte in questo ambiente sono di sola lettura.

![](assets/offer_environments_overview_001.png)

Ogni **[!UICONTROL Design]** l’ambiente è collegato a un **[!UICONTROL Live]** ambiente. Quando un’offerta è completa, il suo contenuto e le relative regole di idoneità sono soggetti a un ciclo di approvazione. Una volta completato il ciclo, l’offerta in questione viene distribuita automaticamente nel **[!UICONTROL Live]** ambiente. Da questo momento, sarà disponibile per la consegna.

Per impostazione predefinita, Campaign viene fornito con **[!UICONTROL Design]** ambiente e **[!UICONTROL Live]** ambiente ad esso collegato. Entrambi gli ambienti sono preconfigurati per la destinazione [tabella dei destinatari incorporata](../dev/datamodel.md#ootb-profiles).

>[!NOTE]
>
>Per eseguire il targeting della tabella dei destinatari, è necessario utilizzare l’assistente per la mappatura di destinazione per creare gli ambienti. [Ulteriori informazioni](#creating-an-offer-environment).

![](assets/offer_environments_overview_002.png)

I responsabili delle consegne possono solo visualizzare **[!UICONTROL Live]** e sfruttare le offerte per distribuirle. I responsabili delle offerte possono visualizzare e utilizzare **[!UICONTROL Design]** e visualizzare **[!UICONTROL Live]** ambiente. [Ulteriori informazioni](interaction-operators.md)

## Creare un ambiente per le interazioni anonime{#create-an-offer-environment}

Per impostazione predefinita, Campaign viene fornito con un ambiente integrato per eseguire il targeting della tabella dei destinatari (offerte identificate). Per eseguire il targeting di un’altra tabella, ad esempio i profili anonimi che visitano il sito web per interazioni in entrata, devi aggiornare la configurazione.

Segui i passaggi seguenti:

1. Sfoglia per **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Target mappings]**, fai clic con il pulsante destro del mouse sulla mappatura di destinazione da utilizzare e seleziona **[!UICONTROL Actions]** > **[!UICONTROL Modify the options of the targeting dimension]**.

   ![](assets/offer_env_anonymous_001.png)

1. Clic **[!UICONTROL Next]**, seleziona la **[!UICONTROL Generate a storage schema for propositions]** e fai clic su **[!UICONTROL Save]**.

   ![](assets/offer_env_anonymous_002.png)

   >[!NOTE]
   >
   >Se l’opzione è già selezionata, deselezionala e ricontrolla.

1. Adobe Campaign crea due ambienti: **[!UICONTROL Design]** e **[!UICONTROL Live]** : con informazioni di targeting dalla mappatura di destinazione precedentemente abilitata. L’ambiente è preconfigurato con le informazioni di targeting.

Se ha attivato **[!UICONTROL Visitor]** mappatura, **[!UICONTROL Environment dedicated to incoming anonymous interactions]** viene selezionata automaticamente nel file **[!UICONTROL General]** scheda.

Questa opzione consente di attivare funzioni specifiche di interazione anonima, in particolare durante la configurazione degli spazi dell’offerta dell’ambiente. Puoi anche configurare le opzioni che ti consentono di passare da un ambiente &quot;identificato&quot; a un ambiente &quot;anonimo&quot;.

Ad esempio, puoi collegare uno spazio dell’offerta in un ambiente destinatario (contatto identificato) con uno spazio dell’offerta che corrisponda a un ambiente visitatore (contatto non identificato). In questo modo, al contatto saranno rese disponibili offerte diverse a seconda che il contatto sia stato identificato o meno. Per ulteriori informazioni, consulta [Creazione di spazi dell’offerta](interaction-offer-spaces.md).

![](assets/offer_env_anonymous_003.png)

>[!NOTE]
>
>Per ulteriori informazioni sulle interazioni anonime su un canale in entrata, consulta [Interazioni anonime](anonymous-interactions.md).
