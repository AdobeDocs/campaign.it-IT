---
product: campaign
title: Codice SQL e codice JavaScript
description: Ulteriori informazioni sulle attività del flusso di lavoro del codice SQL e JavaScript
feature: Workflows
Role: User
level: Experienced
version: Campaign v8, Campaign Classic v7
exl-id: 8c385847-a320-4cd9-9048-2bf9daf2ee07
TQID: https://experienceleague.adobe.com/J1oZUE7vCyJvodf0-09QoG24gWY9P9sSgqsH7rXibgk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2: id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 9%

---

# Codice SQL e codice JavaScript{#sql-code-and-javascript-code}

## Codice SQL {#sql-code}

Un&#39;attività **[!UICONTROL SQL code]** esegue uno script SQL. Lo script è un modello JST.

![](assets/sql_code.png)

* **[!UICONTROL Script]**

  L’area centrale dell’editor contiene lo script da eseguire. Questo script è un modello JST e può quindi essere configurato in base al contesto del flusso di lavoro.

* **[!UICONTROL Processing errors]**

  Consulta [Errori di elaborazione](monitor-workflow-execution.md#processing-errors).

### Note importanti {#important-notes}

Dalla versione 8.9.1, le attività del flusso di lavoro **[!UICONTROL SQL code]** e **[!UICONTROL SQL Data Management]** sono state migliorate per proteggere meglio i database PostgreSQL e mantenere i flussi di lavoro in esecuzione senza problemi quando l’istruzione SQL personalizzata viene eseguita da Campaign. Di seguito sono riportate alcune best practice da seguire in caso di errori.

Opzioni disponibili in **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Options]**. In caso di errori sono disponibili due soluzioni:

**Soluzione 1**

Imposta `XtkSecurity_FeatureFlag_SqlSensitive` su `0`. La funzione è disattivata.

**Soluzione 2**

Modifica `XtkSecurity_SqlSensitive_Methods`. È possibile cambiare `<method name="TRUNCATE" action="block"/>` in `<method name="TRUNCATE" action="warn"/>`

Altri metodi, quali VACUUM FULL, REINDEX, CREATE INDEX e DROP INDEX, sono bloccati per impostazione predefinita per proteggere l&#39;integrità del database. Presta attenzione se desideri impostarli per l’avviso anziché per il blocco. Questi metodi possono avere un impatto significativo sulle prestazioni del database durante l&#39;esecuzione.

## Codice JavaScript e codice JavaScript avanzato {#javascript-code}

Le attività **[!UICONTROL JavaScript code]** e **[!UICONTROL Advanced JavaScript code]** eseguono uno script JavaScript nel contesto di un flusso di lavoro. Per ulteriori informazioni sugli script, consulta le sezioni seguenti:

* [Script e modelli JavaScript](javascript-scripts-and-templates.md)
* [Esempi di codice JavaScript nei flussi di lavoro](javascript-in-workflows.md)

### Ritardo di esecuzione {#exec-delay}

A partire dalla versione 20.2, è stato aggiunto un ritardo di esecuzione alle attività **[!UICONTROL JavaScript code]** e **[!UICONTROL Advanced JavaScript code]**. Per impostazione predefinita, la fase di esecuzione non può superare 1 ora. Dopo questo ritardo, il processo verrà interrotto con un messaggio di errore e l’esecuzione dell’attività avrà esito negativo.

È possibile modificare questo ritardo nel campo **[!UICONTROL Stop execution after]** disponibile in queste attività.

Per ignorare questo limite, è necessario impostare il valore su **0**.

### Codice JavaScript {#js-code-desc}

![](assets/javascript_code.png)

* **[!UICONTROL Script]**: l&#39;area centrale dell&#39;editor contiene lo script da eseguire.

* **[!UICONTROL Process errors]**: consultare [Errori di elaborazione](monitor-workflow-execution.md#processing-errors).

### Codice JavaScript avanzato {#adv-js-code-desc}

![](assets/advanced_javascript_code.png)

* **[!UICONTROL First call]**: la prima zona dell&#39;editor contiene lo script da eseguire durante la prima chiamata.
* **[!UICONTROL Next calls]**: la seconda zona dell&#39;editor contiene lo script da eseguire durante le chiamate successive.
* **[!UICONTROL Transitions]**: è possibile definire diverse transizioni di output attività.
* **[!UICONTROL Schedule]**: la scheda **[!UICONTROL Schedule]** consente di pianificare quando attivare l&#39;attività.

Advanced JavaScript è un&#39;attività persistente che viene periodicamente richiamata se non è stata contrassegnata come completata. Per terminare l&#39;attività ed evitare richiami futuri, è necessario utilizzare il metodo **task.setCompleted()** nella sezione **[!UICONTROL Next calls]**:

```
task.postEvent(task.transitionByName("ok")); // to transition to Ok branch
task.setCompleted();

return 0;
```
