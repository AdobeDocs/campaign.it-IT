---
product: campaign
title: Celle
description: Celle
feature: Workflows, Targeting Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: d85645a6-fc15-4c3a-9d67-d4230224e1f7
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 2%

---

# Celle{#cells}

L&#39;attività **[!UICONTROL Cells]** fornisce una visualizzazione dei vari sottoinsiemi come colonne di dati. Semplifica la manipolazione dei sottoinsiemi ed è progettato anche per sfruttare le funzionalità di personalizzazione.

![](assets/wf_split_cells.png)

Questa attività può essere configurata per immettere parametri specifici in base alle esigenze dell’utente. Per impostazione predefinita, i dettagli di ciascun sottoinsieme sono descritti in una finestra dedicata tramite le schede **[!UICONTROL Cells]** e **[!UICONTROL Advanced]**.

![](assets/wf_split_cells_with_customization.png)

Nell&#39;esempio seguente, il modulo di input è stato modificato: è stata aggiunta una scheda **[!UICONTROL Data]** per abilitare l&#39;associazione di un&#39;offerta e un livello di priorità per ogni sottoinsieme.

![](assets/cells-activity-sample.png)

Per questa configurazione, le seguenti informazioni sono state aggiunte al modulo del flusso di lavoro, nel nodo **[!UICONTROL Administration > Configurations > Input forms]** di Adobe Campaign Explorer:

```
<container img="nms:miniatures/mini-enrich.png" label="Data">
                <input xpath="@code"/>
                <container xpath="select/node[@alias='@numTest']">
                  <input alwaysActive="true" expr="'long'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Priority'" type="expr" xpath="@label"/>
                  <input label="Priority" maxValue="12" minValue="0" type="number"
                         xpath="@value" xpathEditFromType="@type"/>
                </container>
                <container xpath="select/node[@alias='@test']">
                  <input alwaysActive="true" expr="'string'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'Identifier'" type="expr" xpath="@label"/>
                  <input label="Cell identifier" xpath="@value"/>
                </container>
                <container xpath="select/node[@alias='linkTest']">
                  <input alwaysActive="true" expr="'link'" type="expr" xpath="@type"/>
                  <input alwaysActive="true" expr="'nms:offer'" type="expr" xpath="@dataType"/>
                  <input alwaysActive="true" expr="'Offre'" type="expr" xpath="@label"/>
                  <input computeStringAlias="@valueLabel" label="Offers" notifyPathList="@_cs|@valueLabel"
                         schema="nms:offer" type="linkEdit" xpath="@value"/>
                </container>
```

La personalizzazione dei moduli di input in Adobe Campaign è riservata agli utenti esperti.