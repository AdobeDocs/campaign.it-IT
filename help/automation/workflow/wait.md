---
product: campaign
title: Attività Wait
description: Ulteriori informazioni sull’attività del flusso di lavoro Wait
feature: Workflows
source-git-commit: 2b1dec4b9c456df4dfcebfe10d18e0ab01599275
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---

# Attività Wait{#wait}



A **Wait** l’attività attiva la relativa transizione dopo un ritardo di tempo compreso tra alcuni secondi e diversi mesi. Un’attività di attesa non blocca l’esecuzione di altre attività; il flusso di lavoro può eseguire attività in parallelo mentre questa attività è in sospeso.

Puoi immettere l’etichetta e attendere il tempo di attesa utilizzando l’editor, come nell’esempio seguente:

![](assets/edit_wait.png)

In **[!UICONTROL Duration]** campo, il valore può essere espresso nell&#39;unità scelta: (secondo le impostazioni regionali dell&#39;operatore):

* Se le impostazioni internazionali non sono specificate: **s** per secondi, **m** per i minuti, **h** per ore, **d** per giorni, **y** per anni. Al momento dell’approvazione, il valore viene automaticamente convertito nell’unità più leggibile.

   L’unità predefinita è il giorno (**d**).

* Se, ad esempio, le impostazioni regionali sono impostate su &quot;Français&quot;: **s** per secondi, **mn** per i minuti, **h** per ore, **j** per giorni, **m** per mesi, **a** per anni. Al momento dell’approvazione, il valore viene automaticamente convertito nell’unità più leggibile, come nell’esempio precedente **Anni 90** è stato convertito in **1 milione e 30 anni**.

   L’unità predefinita è il giorno (**d**).
