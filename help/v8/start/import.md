---
solution: Campaign v8
product: Adobe Campaign
title: Guida introduttiva ai profili
description: Guida introduttiva ai profili
feature: Profili
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 905003b74a1f875432f08c5c70edf3d0451b861f
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Importare dati in Campaign {#ootb-profiles}

Campaign ti consente di aggiungere contatti al database Cloud. È possibile caricare un file, pianificare e automatizzare più aggiornamenti dei contatti, raccogliere dati sul Web o immettere informazioni di profilo direttamente nella tabella dei destinatari.

:lampadina: Guida introduttiva a [tipi di pubblico](audiences.md)
:lampadina: Comprendere Campaign [modello dati](../dev/datamodel.md)

## Importare profili in un flusso di lavoro

Le importazioni di profili sono configurate in modelli dedicati eseguiti tramite flussi di lavoro tramite l’attività **Import** . Possono essere ripetuti automaticamente in base a una pianificazione, ad esempio per automatizzare lo scambio di dati tra diversi sistemi di informazione. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html).

![](assets/import-wf.png)

Ulteriori informazioni nella documentazione di Campaign Classic v7:

:arrow_Upper_right: [Guida introduttiva alle importazioni e alle esportazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html)

:arrow_Upper_right: [Best practice per l&#39;importazione e l&#39;esportazione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html)

:arrow_Upper_right: [Configura ed esegui un&#39;importazione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html)

## Eseguire importazioni unitarie

Crea ed esegui un processo di importazione dati generico per caricare i contatti nel database Cloud.

![](assets/new-import.png)

:arrow_Upper_right: Scopri come eseguire processi di importazione unitari per alimentare il database nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html).

## Raccogliere profili tramite app web

Utilizza Campaign per creare moduli web e raccogliere e gestire le informazioni sul profilo in modo semplice ed efficiente. È possibile condividere questi moduli nel sito web, facilitando l&#39;invio delle informazioni ai contatti. Le loro informazioni vengono inviate a Campaign per creare il loro profilo o per aggiornare le loro informazioni, se sono già presenti nel database.

![](assets/web-form-page.png)

:arrow_Upper_right: Scopri come creare moduli web nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html).

**Argomenti correlati**

* [Creare un pubblico](audiences.md)
* [Profili deduplicazione](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html)
* [Arricchire i dati del profilo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html)
