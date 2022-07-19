---
product: campaign
title: Attività Test
description: Ulteriori informazioni sull’attività del flusso di lavoro Test
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 4%

---

# Attività Test{#test}



A **Test** l’attività type attiva la prima transizione che soddisfa la condizione associata. Se non è soddisfatta alcuna condizione e se la **[!UICONTROL Use the default fork]** se attivata, verrà attivata la transizione predefinita.

Una condizione è un&#39;espressione JavaScript che deve essere valutata come &#39;true&#39; o &#39;false&#39;. Per immettere l’espressione, fai clic sull’icona a destra del nome della condizione, quindi seleziona **[!UICONTROL Edit...]**.

![](assets/edit_test.png)

Per ulteriori informazioni su tutte le funzioni JavaScript aggiuntive e i metodi SOAP del server applicativo accessibili tramite il flusso di lavoro JavaScript, fare riferimento a [Documentazione JSAPI](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=it).

Puoi anche inserire le variabili direttamente da questo editor. Per ulteriori informazioni su come utilizzare le variabili, consulta [questa sezione](javascript-scripts-and-templates.md#variables).

Le condizioni possono essere aggiunte, eliminate o ordinate dalla finestra di modifica della proprietà dell’attività, ma possono anche essere modificate dalla transizione.

Se il risultato di un calcolo deve essere riutilizzato da condizioni diverse, è possibile calcolarlo nello script di inizializzazione dell&#39;attività. Il risultato deve essere memorizzato in una variabile dell&#39;attività a cui devono accedere gli script di condizione (task.vars.xxx).
