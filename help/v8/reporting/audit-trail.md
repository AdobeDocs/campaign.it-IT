---
product: campaign
title: Audit trail
description: Scopri come monitorare l’istanza con Campaign Audit trail
feature: Audit Trail, Monitoring, Workflows
source-git-commit: bb74393f0b24fa5b9781eee15c4527daba527192
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 2%

---

# Audit trail{#audit-trail}

Il **[!UICONTROL Audit trail]** funzionalità di Adobe Campaign offre una registrazione granulare di tutte le modifiche apportate a entità importanti all’interno dell’istanza, in genere quelle che influiscono in modo significativo sul corretto funzionamento dell’istanza. Fungendo da registro in tempo reale, acquisisce un elenco dettagliato di azioni ed eventi nel momento in cui si verificano.

>[!NOTE]
>
>Adobe Campaign non controlla le modifiche apportate all’interno di diritti utente, modelli, personalizzazioni o campagne.\
>L’audit trail può essere gestito solo dagli amministratori dell’istanza.

+++ Ulteriori informazioni sulle entità disponibili in Audit Trail

* **Audit trail dello schema**: ti consente di esplorare le modifiche apportate agli schemi, nonché di identificare chi le ha apportate e quando si sono verificate.

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

  Per ulteriori informazioni su come monitorare i flussi di lavoro, consulta [sezione dedicata](../../automation/workflow/monitor-workflow-execution.md).

* **Opzione audit trail** consente di controllare le attività e le ultime modifiche apportate alle opzioni.

  Per ulteriori informazioni sulle opzioni, consulta questa [pagina](https://experienceleague.adobe.com/en/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options).

* **Audit trail della consegna** consente di controllare le attività e le ultime modifiche apportate alle consegne.

  Per ulteriori informazioni sulle consegne, consulta [pagina](../start/create-message.md).

* **Account esterno** consente di verificare le modifiche apportate ad account esterni, utilizzate da processi tecnici come flussi di lavoro tecnici o flussi di lavoro di campagne.

  Per ulteriori informazioni sull’account esterno, consulta questa [pagina](../config/external-accounts.md).

* **Mappatura consegna** consente di monitorare le attività e le modifiche recenti apportate alle mappature di consegna.

  Per ulteriori informazioni sulla mappatura della consegna, consulta [pagina](../audiences/target-mappings.md).

* **Applicazione web** consente di verificare le modifiche apportate ai moduli web in Campaign V8 utilizzati per creare pagine con campi di input e selezione e che possono includere dati dal database.

  Per ulteriori informazioni sull’applicazione web, consulta questa [pagina](../dev/webapps.md).

* **Offerta** consente di controllare le attività e le ultime modifiche apportate alle offerte.

  Per ulteriori informazioni sull’offerta, consulta questa [pagina](../interaction/interaction.md).

* **Operatore** consente di monitorare le attività e le modifiche recenti apportate agli operatori.

  Per ulteriori informazioni sugli operatori, consulta questa [pagina](../interaction/interaction-operators.md).

+++

## Accesso a Audit trail {#accessing-audit-trail}

Per accedere al di **[!UICONTROL Audit trail]**:

1. Accedere a **[!UICONTROL Explorer]** della tua istanza.

1. Sotto **[!UICONTROL Administration]** menu, seleziona **[!UICONTROL Audit]** allora **[!UICONTROL Audit Trail]**.

   ![](assets/audit-trail-1.png)

1. Il **[!UICONTROL Audit trail]** viene visualizzata la finestra con l&#39;elenco delle entità. Adobe Campaign controllerà le azioni di creazione, modifica ed eliminazione per le diverse entità.

   Selezionate una delle entità per ulteriori informazioni sulle ultime modifiche.

1. Il **[!UICONTROL Audit entity]** La finestra fornisce informazioni più dettagliate sull’entità scelta, ad esempio:

   * **[!UICONTROL Type]**: flusso di lavoro, opzioni, consegne o schemi.
   * **[!UICONTROL Entity]**: nome interno delle attività.
   * **[!UICONTROL Modified by]**: nome utente dell’ultima persona che ha modificato questa entità.
   * **[!UICONTROL Action]**: ultima azione eseguita sull’entità, Creata, Modificata o Eliminata.
   * **[!UICONTROL Modification date]**: data dell’ultima azione eseguita su questa entità.

   ![](assets/audit-trail-2.png)

>[!NOTE]
>
>Per impostazione predefinita, il periodo di conservazione è impostato su 180 giorni per **[!UICONTROL Audit logs]**. Questo valore può essere modificato nella procedura guidata di distribuzione.

## Attiva/disattiva Audit trail {#enable-disable-audit-trail}

L’audit trail può essere facilmente attivato o disattivato per un’attività specifica se, ad esempio, si desidera risparmiare spazio nel database.

Per eseguire questa operazione:

1. Accedere a **[!UICONTROL Explorer]** della tua istanza.

1. Sotto **[!UICONTROL Administration]** menu, seleziona **[!UICONTROL Platform]** allora **[!UICONTROL Options]**.

1. Selezionate una delle seguenti opzioni a seconda dell&#39;entità da attivare/disattivare:

   * Per il flusso di lavoro: **[!UICONTROL XtkAudit_Workflows]**
   * Per gli schemi: **[!UICONTROL XtkAudit_DataSchema]**
   * Per le opzioni: **[!UICONTROL XtkAudit_Option]**
   * Per le consegne: **[!UICONTROL XtkAudit_Delivery]**
   * Per Account Esterno: **[!UICONTROL XtkAudit_ExtAccount]**
   * Per la mappatura della consegna: **[!UICONTROL XtkAudit_DeliveryMapping]**
   * Per l&#39;applicazione Web: **[!UICONTROL XtkAudit_WebApp]**
   * Per offerta: **[!UICONTROL XtkAudit_Offer]**
   * Per Operatore: **[!UICONTROL XtkAudit_Operator]**
   * Per ogni entità: **[!UICONTROL XtkAudit_Enable_All]**

   ![](assets/audit-trail-3.png)

1. Modificare il **[!UICONTROL Value]** a 1 se si desidera abilitare l’entità o a 0 se si desidera disabilitarla.

   ![](assets/audit-trail-4.png)

1. Fai clic su **[!UICONTROL Save]**.
