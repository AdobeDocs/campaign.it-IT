---
product: campaign
title: Test
description: Ulteriori informazioni sull’attività del flusso di lavoro Test
feature: Workflows
exl-id: 0d4d13f6-7128-44d3-ad5c-4ed02257ee64
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 1%

---

# Test{#test}



A **Test** l’attività di tipo attiva la prima transizione che soddisfa la condizione associata. Se non viene soddisfatta alcuna condizione e se **[!UICONTROL Use the default fork]** viene attivata, viene attivata la transizione predefinita.

Una condizione è un’espressione JavaScript che deve essere valutata come &quot;true&quot; o &quot;false&quot;. Per immettere l’espressione, fai clic sull’icona a destra del nome della condizione, quindi seleziona **[!UICONTROL Edit...]**.

![](assets/edit_test.png)

Per ulteriori informazioni su tutte le funzioni JavaScript aggiuntive e i metodi SOAP del server applicativo accessibili tramite JavaScript del flusso di lavoro, consulta [Documentazione JSAPI](https://experienceleague.adobe.com/developer/campaign-api/api/index.html?lang=it){target="_blank"}.

Puoi anche inserire le variabili direttamente da questo editor. Per ulteriori informazioni su come lavorare con le variabili, consulta [questa sezione](javascript-scripts-and-templates.md#variables).

Le condizioni possono essere aggiunte, eliminate o ordinate dalla finestra di modifica delle proprietà dell’attività, ma possono anche essere modificate dalla transizione.

Se il risultato di un calcolo deve essere riutilizzato da condizioni diverse, è possibile calcolarlo nello script di inizializzazione dell’attività. Il risultato deve essere memorizzato in una variabile dell’attività a cui devono accedere gli script di condizione (task.vars.xxx).
