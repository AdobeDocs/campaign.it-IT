---
product: Adobe Campaign
title: Introduzione ai profili
description: Introduzione ai profili
feature: Profili
role: Data Engineer
level: Beginner
exl-id: b0f8c057-dd4e-4284-b5a4-157986a1d95a
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: ht
source-wordcount: '322'
ht-degree: 100%

---

# Importare dati in Campaign {#ootb-profiles}

Campaign ti aiuta ad aggiungere contatti al database Cloud. Puoi caricare un file, pianificare e automatizzare più aggiornamenti dei contatti alla volta, raccogliere dati sul web o inserire informazioni di profilo direttamente nella tabella dei destinatari.

?? Introduzione ai [tipi di pubblico](audiences.md)
?? Il [modello dati](../dev/datamodel.md) di Campaign

## Importare profili con un flusso di lavoro

Le importazioni di profili sono configurate in modelli dedicati eseguiti tramite flussi di lavoro attraverso l’attività **Importazione**. Possono essere ripetuti automaticamente in base a una pianificazione, ad esempio per automatizzare lo scambio di dati tra diversi sistemi di informazione. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/import-export-workflows.html?lang=it){target=&quot;_blank&quot;}.

![](assets/import-wf.png)

Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7:

↗️ [Introduzione alle importazioni ed esportazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/get-started-data-import-export.html?lang=it){target=&quot;_blank&quot;}

↗️ [Best practice per l’importazione e l’esportazione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/best-practices/import-export-best-practices.html?lang=it){target=&quot;_blank&quot;}

↗️ [Configurare ed eseguire un’importazione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-import-jobs.html?lang=it){target=&quot;_blank&quot;}

## Eseguire importazioni unitarie

Crea ed esegui un processo di importazione dati generico per caricare i contatti nel database Cloud.

![](assets/new-import.png)

↗️ Scopri come eseguire processi di importazione unitari per alimentare il database, nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/about-generic-imports-exports.html?lang=it){target=&quot;_blank&quot;}.

## Raccogliere profili tramite app web

Utilizza Campaign per creare moduli web e raccogliere e gestire le informazioni sul profilo in modo semplice ed efficiente. Puoi condividere questi moduli nel tuo sito web, in modo che i tuoi contatti possano inviarti facilmente i loro dati. Questi vengono inviate a Campaign per creare il profilo cliente o per aggiornare le informazioni già presenti nel database.

![](assets/web-form-page.png)

↗️ Scopri come creare moduli web, nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/about-web-forms.html?lang=it){target=&quot;_blank&quot;}.

**Argomenti correlati**

* [Creare tipi di pubblico](audiences.md)
* [Deduplicare i profili](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/deduplication-merge.html?lang=it){target=&quot;_blank&quot;}
* [Arricchire i dati del profilo](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/use-cases/data-management/enriching-data.html?lang=it) {target=&quot;_blank&quot;}
