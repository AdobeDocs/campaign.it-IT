---
title: Utilizzare Campaign e SFDC
description: Scopri come utilizzare Campaign e Salesforce.com
feature: Salesforce Integration
role: Admin, User
level: Beginner, Intermediate, Experienced
exl-id: 1e20f3b9-d1fc-411c-810b-6271360286f9
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 3%

---

# Utilizzare Campaign e SFDC{#crm-sfdc}

Scopri come configurare il connettore CRM di Campaign per collegare Campaign v8 a **Salesforce.com**.

Al termine della configurazione, la sincronizzazione dei dati tra sistemi viene eseguita tramite un’attività del flusso di lavoro dedicata. [Ulteriori informazioni](crm-data-sync.md).

>[!NOTE]
>
>Le versioni di SFDC supportate sono descritte in dettaglio in Campaign [Matrice di compatibilità](../start/compatibility-matrix.md).

Segui i passaggi seguenti per configurare un account esterno dedicato per importare ed esportare i dati di Salesforce in Adobe Campaign.

## Creare la connessione{#new-sfdc-external-account}

Innanzitutto, devi creare l’account esterno Salesforce.

1. Sfoglia **[!UICONTROL Administration > Platform > External accounts]** dell’Explorer di Campaign e creare un account esterno.
1. Seleziona **[!UICONTROL Salesforce.com]** account esterno in **Tipo** sezione.
1. Immettere le impostazioni per abilitare la connessione.

   ![](assets/sfdc-external-account.png)

   Per configurare l’account esterno del sistema di gestione delle relazioni con i clienti di Salesforce affinché funzioni con Adobe Campaign, è necessario fornire i seguenti dettagli:

   * Inserisci il tuo login a Salesforce in **[!UICONTROL Account]** campo.
   * Immetti la password Salesforce.
   * Puoi ignorare **[!UICONTROL Client identifier]** campo.
   * Copia/incolla Salesforce **[!UICONTROL Security token]**
   * Seleziona il **[!UICONTROL API version]**. Le versioni API SFDC supportate sono elencate in Campaign [Matrice di compatibilità](../start/compatibility-matrix.md).

1. Seleziona la **Abilita** per attivare l’account in Campaign.

>[!NOTE]
>
>Per approvare la configurazione, è necessario disconnettersi e accedere nuovamente alla console client di Adobe Campaign.

## Seleziona tabelle da sincronizzare{#sfdc-create-tables}

È ora possibile configurare le tabelle da sincronizzare.

1. Fai clic su **[!UICONTROL Salesforce CRM configuration wizard...]**.
1. Selezionare le tabelle da sincronizzare e avviare il processo.
1. Controlla lo schema generato in Adobe Campaign nel **[!UICONTROL Administration > Configuration > Data schemas]** nodo.

   Esempio di **Salesforce** schema importato in Campaign:

   ![](assets/sfdc-schemas.png)

## Sincronizzare le enumerazioni{#sfdc-enum-sync}

Una volta creato lo schema, puoi sincronizzare automaticamente le enumerazioni da Salesforce ad Adobe Campaign.

1. Apri l’assistente da  **[!UICONTROL Synchronizing enumerations...]** collegamento.
1. Seleziona l’enumerazione Adobe Campaign che corrisponde all’enumerazione Salesforce.
Puoi sostituire tutti i valori di un’enumerazione Adobe Campaign con quelli del CRM: a questo scopo, seleziona **[!UICONTROL Yes]** nel **[!UICONTROL Replace]** colonna.

   ![](assets/sfdc-enum.png)

1. Clic **[!UICONTROL Next]** e poi **[!UICONTROL Start]** per avviare l&#39;importazione delle enumerazioni.

1. Sfoglia **[!UICONTROL Administration > Platform > Enumerations]** per controllare i valori importati. Ulteriori informazioni sulle enumerazioni in [questa pagina](../config/ui-settings.md#enumerations).

Adobe Campaign e Salesforce.com sono ora connessi. È possibile impostare la sincronizzazione dei dati tra i due sistemi.

Per sincronizzare i dati tra i dati di Adobe Campaign e SFDC, crea un flusso di lavoro e utilizza **[!UICONTROL CRM connector]** attività.

Ulteriori informazioni sulla sincronizzazione dei dati [in questa pagina](crm-data-sync.md).
