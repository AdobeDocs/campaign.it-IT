---
product: campaign
title: Attività Wait
description: Ulteriori informazioni sull’attività del flusso di lavoro Attendi
feature: Workflows
exl-id: a9bcb214-5c87-4b26-804a-22b868905022
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---

# Attività Wait{#wait}



A **Wait** l’attività attiva la relativa transizione dopo un ritardo di tempo compreso tra pochi secondi e diversi mesi. Un’attività in attesa non blocca l’esecuzione di altre attività; il flusso di lavoro può eseguire le attività in parallelo mentre questa attività è in sospeso.

Puoi immettere l’etichetta e il tempo di attesa utilizzando l’editor, come nell’esempio seguente:

![](assets/edit_wait.png)

In **[!UICONTROL Duration]** , il valore può essere espresso nell&#39;unità scelta: (in base alle impostazioni internazionali dell&#39;operatore):

* Se non si specificano le impostazioni internazionali: **s** per secondi, **m** per minuti, **h** per ore, **d** per giorni, **y** per anni. Al momento dell’omologazione, il valore viene automaticamente convertito nell’unità più leggibile.

   L&#39;unità predefinita è il giorno (**d**).

* Se, ad esempio, le impostazioni internazionali sono impostate su &quot;Français&quot;: **s** per secondi, **mn** per minuti, **h** per ore, **j** per giorni, **m** per mesi, **a** per anni. Al momento dell’omologazione, il valore viene automaticamente convertito nell’unità più leggibile, come nell’esempio precedente **90s** convertito in **1mn 30s**.

   L&#39;unità predefinita è il giorno (**d**).
