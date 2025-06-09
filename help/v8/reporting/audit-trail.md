---
product: campaign
title: Audit trail
description: Scopri come monitorare l’istanza con Campaign Audit trail
feature: Audit Trail, Monitoring, Workflows
exl-id: 6a937575-42d4-4dc5-8168-43c25bb2cde6
source-git-commit: b4b361a4aabd1b33554166c2638989b99a02baec
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 2%

---

# Audit trail{#audit-trail}

La funzionalità **[!UICONTROL Audit trail]** di Adobe Campaign offre un record granulare di tutte le modifiche apportate a entità importanti all&#39;interno dell&#39;istanza, in genere quelle che influiscono in modo significativo sul corretto funzionamento dell&#39;istanza. Fungendo da registro in tempo reale, acquisisce un elenco dettagliato di azioni ed eventi nel momento in cui si verificano.

>[!NOTE]
>
>Adobe Campaign non controlla le modifiche apportate all’interno di diritti utente, modelli, personalizzazioni o campagne.\
>L’audit trail può essere gestito solo dagli amministratori dell’istanza.

+++ Ulteriori informazioni sulle entità disponibili in Audit Trail

* **Audit trail dello schema**: consente di esplorare le modifiche apportate agli schemi, nonché di identificare chi ha apportato tali modifiche e quando si sono verificate.

  Per informazioni dettagliate sugli schemi, consulta [pagina](../dev/schemas.md).

* **Audit trail del flusso di lavoro** tiene traccia di tutte le azioni relative ai flussi di lavoro, tra cui:

   * Inizio
   * Pausa
   * Interruzione
   * Riavvio
   * Pulizia uguale all’azione Cancella cronologia
   * Simula, che è uguale all’azione Avvia in modalità simulazione
   * Attivazione uguale all&#39;azione Esegui attività in sospeso ora
   * Arresto totale

  Per ulteriori informazioni sui flussi di lavoro, consulta questa [pagina](../../automation/workflow/about-workflows.md).

  Per ulteriori informazioni su come monitorare i flussi di lavoro, consulta la [sezione dedicata](../../automation/workflow/monitor-workflow-execution.md).

* **Option audit trail** consente di controllare le attività e le ultime modifiche apportate alle opzioni.

  Per ulteriori informazioni sulle opzioni, consulta questa [pagina](https://experienceleague.adobe.com/it/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options).

* **Audit trail consegna** consente di controllare le attività e le ultime modifiche apportate alle consegne.

  Per ulteriori informazioni sulle consegne, consulta questa [pagina](../start/create-message.md).

* **Account esterno** consente di controllare le modifiche apportate agli account esterni, utilizzate da processi tecnici quali flussi di lavoro tecnici o flussi di lavoro per campagne.

  Per ulteriori informazioni sull&#39;account esterno, fare riferimento a questa [pagina](../config/external-accounts.md).

* **Mappatura consegna** consente di monitorare le attività e le modifiche recenti apportate alle mappature di consegna.

  Per ulteriori informazioni sulla mappatura della consegna, consulta questa [pagina](../audiences/target-mappings.md).

* **Applicazione Web** consente di controllare le modifiche apportate ai moduli Web in Campaign V8 utilizzati per creare pagine con campi di input e di selezione e che possono includere dati dal database.

  Per ulteriori informazioni sull&#39;applicazione Web, fare riferimento a questa [pagina](../dev/webapps.md).

* **Offerta** ti consente di controllare le attività e le ultime modifiche apportate alle offerte.

  Per ulteriori informazioni sull&#39;offerta, consulta questa [pagina](../interaction/interaction.md).

* **Operatore** consente di monitorare le attività e le modifiche recenti apportate agli operatori.

  Per ulteriori informazioni sugli operatori, consulta questa [pagina](../interaction/interaction-operators.md).

+++

## Accesso a Audit trail {#accessing-audit-trail}

Per accedere a **[!UICONTROL Audit trail]** dell&#39;istanza:

1. Accedi al menu **[!UICONTROL Explorer]** della tua istanza.

1. Nel menu **[!UICONTROL Administration]**, selezionare **[!UICONTROL Audit]** e quindi **[!UICONTROL Audit Trail]**.

   ![](assets/audit-trail-1.png)

1. Viene visualizzata la finestra **[!UICONTROL Audit trail]** con l&#39;elenco delle entità. Adobe Campaign controllerà le azioni di creazione, modifica ed eliminazione per le diverse entità.

   Selezionate una delle entità per ulteriori informazioni sulle ultime modifiche.

1. La finestra **[!UICONTROL Audit entity]** fornisce informazioni più dettagliate sull&#39;entità scelta, ad esempio:

   * **[!UICONTROL Type]**: flusso di lavoro, opzioni, consegne o schemi.
   * **[!UICONTROL Entity]**: nome interno delle attività.
   * **[!UICONTROL Modified by]**: nome utente dell&#39;ultima persona che ha modificato l&#39;entità.
   * **[!UICONTROL Action]**: ultima azione eseguita sull&#39;entità, Creata, Modificata o Eliminata.
   * **[!UICONTROL Modification date]**: data dell&#39;ultima azione eseguita su questa entità.

   ![](assets/audit-trail-2.png)

>[!NOTE]
>
>Per impostazione predefinita, il periodo di conservazione è impostato su 180 giorni per **[!UICONTROL Audit logs]**. Questo valore può essere modificato nella procedura guidata di distribuzione.

## Attiva/disattiva Audit trail {#enable-disable-audit-trail}

L’audit trail può essere facilmente attivato o disattivato per un’attività specifica se, ad esempio, si desidera risparmiare spazio nel database.

Per eseguire questa operazione:

1. Accedi al menu **[!UICONTROL Explorer]** della tua istanza.

1. Nel menu **[!UICONTROL Administration]**, selezionare **[!UICONTROL Platform]** e quindi **[!UICONTROL Options]**.

1. Selezionate una delle seguenti opzioni a seconda dell&#39;entità da attivare/disattivare:

   * Per il flusso di lavoro: **[!UICONTROL XtkAudit_Workflows]**
   * Per gli schemi: **[!UICONTROL XtkAudit_DataSchema]**
   * Per le opzioni: **[!UICONTROL XtkAudit_Option]**
   * Per le consegne: **[!UICONTROL XtkAudit_Delivery]**
   * Per Account Esterno: **[!UICONTROL XtkAudit_ExtAccount]**
   * Per mapping di consegna: **[!UICONTROL XtkAudit_DeliveryMapping]**
   * Per l&#39;applicazione Web: **[!UICONTROL XtkAudit_WebApp]**
   * Per offerta: **[!UICONTROL XtkAudit_Offer]**
   * Per l&#39;operatore: **[!UICONTROL XtkAudit_Operator]**
   * Per ogni entità: **[!UICONTROL XtkAudit_Enable_All]**

   ![](assets/audit-trail-3.png)

1. Modificare **[!UICONTROL Value]** in 1 se si desidera abilitare l&#39;entità o in 0 se si desidera disabilitarla.

   ![](assets/audit-trail-4.png)

1. Fai clic su **[!UICONTROL Save]**.
