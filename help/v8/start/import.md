---
product: Adobe Campaign
title: Introduzione ai profili
description: Introduzione ai profili
feature: Profili
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 59%

---

# Importare dati in Campaign {#ootb-profiles}

Campaign ti aiuta ad aggiungere contatti al database Cloud. Puoi caricare un file, pianificare e automatizzare più aggiornamenti dei contatti alla volta, raccogliere dati sul web o inserire informazioni di profilo direttamente nella tabella dei destinatari.

[!DNL :bulb:] Guida introduttiva a  [](audiences.md)
[!DNL :bulb:] audiencesComprendere il modello  [dati di Campaign](../dev/datamodel.md)

## Importare profili con un flusso di lavoro

Le importazioni di profili sono configurate in modelli dedicati eseguiti tramite flussi di lavoro attraverso l’attività **Importazione**. Possono essere ripetuti automaticamente in base a una pianificazione, ad esempio per automatizzare lo scambio di dati tra diversi sistemi di informazione. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html?lang=it).

![](assets/import-wf.png)

Ulteriori informazioni nella documentazione di Campaign Classic v7:

[!DNL :arrow_upper_right:] [Guida introduttiva alle importazioni e alle esportazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html?lang=it)

[!DNL :arrow_upper_right:] [Best practice per l’importazione e l’esportazione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html?lang=it)

[!DNL :arrow_upper_right:] [Configurare ed eseguire un’importazione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=it)

## Eseguire importazioni unitarie

Crea ed esegui un processo di importazione dati generico per caricare i contatti nel database Cloud.

![](assets/new-import.png)

[!DNL :arrow_upper_right:] Scopri come eseguire processi di importazione unitari per alimentare il database nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=it).

## Raccogliere profili tramite app web

Utilizza Campaign per creare moduli web e raccogliere e gestire le informazioni sul profilo in modo semplice ed efficiente. È possibile condividere questi moduli nel sito web, facilitando l&#39;invio delle informazioni ai contatti. Le loro informazioni vengono inviate a Campaign per creare il loro profilo o per aggiornare le loro informazioni, se sono già presenti nel database.

![](assets/web-form-page.png)

[!DNL :arrow_upper_right:] Scopri come creare moduli web nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html).

**Argomenti correlati**

* [Creare tipi di pubblico](audiences.md)
* [Eseguire la deduplicazione dei profili](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html?lang=it)
* [Arricchire i dati del profilo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html?lang=it)
