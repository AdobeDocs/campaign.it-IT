---
title: Utilizzare Campaign e SFDC
description: Scopri come utilizzare Campaign e Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
TQID: 'https://experienceleague.adobe.com/N50ecfMFC641fveGfyxx4W9XvZgWPgddrdpj9KrCHBY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: f09afca2-2160-4624-bedb-639c4f4c236f
    internal-label: Salesforce integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 3%
---
# Utilizzare Campaign e SFDC{#crm-sfdc}

Scopri come configurare il connettore di gestione delle relazioni con i clienti di Campaign per collegare Campaign v8 a **Salesforce.com**.

Al termine della configurazione, la sincronizzazione dei dati tra sistemi viene eseguita tramite un’attività del flusso di lavoro dedicata. [Ulteriori informazioni](crm-data-sync.md).

>[!NOTE]
>
>Le versioni di SFDC supportate sono descritte in dettaglio nella [Matrice di compatibilità](../start/compatibility-matrix.md) di Campaign.

Segui i passaggi seguenti per configurare un account esterno dedicato per importare ed esportare dati Salesforce in Adobe Campaign.

## Creare la connessione{#new-sfdc-external-account}

Innanzitutto, devi creare l’account esterno di Salesforce.

1. Sfoglia il nodo **[!UICONTROL Administration > Platform > External accounts]** di Esplora campagne e crea un account esterno.
1. Selezionare l&#39;account esterno **[!UICONTROL Salesforce.com]** nella sezione **Tipo**.
1. Immettere le impostazioni per abilitare la connessione.

   ![](assets/sfdc-external-account.png)

   Per configurare l’account esterno di Salesforce CRM per l’utilizzo con Adobe Campaign, è necessario fornire i seguenti dettagli:

   * Immetti l&#39;accesso a Salesforce nel campo **[!UICONTROL Account]**.
   * Immettere la password Salesforce.
   * È possibile ignorare il campo **[!UICONTROL Client identifier]**.
   * Copia/incolla il tuo Salesforce **[!UICONTROL Security token]**
   * Seleziona **[!UICONTROL API version]**. Le versioni dell&#39;API SFDC supportate sono elencate nella [Matrice di compatibilità](../start/compatibility-matrix.md) di Campaign.

1. Seleziona l&#39;opzione **Abilita** per attivare l&#39;account in Campaign.

>[!NOTE]
>
>Per approvare la configurazione, è necessario disconnettersi e accedere nuovamente alla console client di Adobe Campaign.

## Seleziona tabelle da sincronizzare{#sfdc-create-tables}

È ora possibile configurare le tabelle da sincronizzare.

1. Fare clic su **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. Selezionare le tabelle da sincronizzare e avviare il processo.
1. Controllare lo schema generato in Adobe Campaign nel nodo **[!UICONTROL Administration > Configuration > Data schemas]**.

   Esempio di schema **Salesforce** importato in Campaign:

   ![](assets/sfdc-schemas.png)

## Sincronizzare le enumerazioni{#sfdc-enum-sync}

Una volta creato lo schema, puoi sincronizzare automaticamente le enumerazioni da Salesforce ad Adobe Campaign.

1. Apri l&#39;assistente dal collegamento **[!UICONTROL Synchronizing enumerations...]**.
1. Seleziona l’enumerazione Adobe Campaign che corrisponde all’enumerazione Salesforce.
È possibile sostituire tutti i valori di un&#39;enumerazione Adobe Campaign con quelli del CRM: a questo scopo, selezionare **[!UICONTROL Yes]** nella colonna **[!UICONTROL Replace]**.

   ![](assets/sfdc-enum.png)

1. Fare clic su **[!UICONTROL Next]** e quindi su **[!UICONTROL Start]** per avviare l&#39;importazione delle enumerazioni.

1. Sfoglia il nodo **[!UICONTROL Administration > Platform > Enumerations]** per controllare i valori importati. Ulteriori informazioni sulle enumerazioni in [questa pagina](../config/ui-settings.md#enumerations).

Adobe Campaign e Salesforce.com sono ora connessi. È possibile impostare la sincronizzazione dei dati tra i due sistemi.

Per sincronizzare i dati tra Adobe Campaign e SFDC, creare un flusso di lavoro e utilizzare l&#39;attività **[!UICONTROL CRM connector]**.

Ulteriori informazioni sulla sincronizzazione dei dati [sono disponibili in questa pagina](crm-data-sync.md).

Ulteriori informazioni sulla gestione dell&#39;enumerazione in Campaign [in questa pagina](../config/enumerations.md).
