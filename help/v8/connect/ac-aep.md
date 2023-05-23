---
title: Utilizzare Campaign e Adobe Experience Platform
description: Scopri come utilizzare Campaign e Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: 3c7455f348468a8f00fb853a3269a1d63b81e7b8
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Utilizzare Campaign e Adobe Experience Platform

I connettori di origine e destinazione del Cloud Service gestito di Adobe Campaign consentono un’integrazione perfetta tra Adobe Campaign e Adobe Experience Platform.

* Utilizzare **Destinazione Adobe Campaign Managed Cloud Services** connessione per inviare segmenti Experience Platform ad Adobe Campaign per l’attivazione

   ![](assets/aep-destination.png)

* Utilizzare **Origine Adobe Campaign Managed Cloud Services** connessione per inviare i registri di consegna e tracciamento di Adobe Campaign a Adobe Experience Platform

   ![](assets/aep-logs.png)

I passaggi per configurare questa integrazione in Adobe Experience Platform sono i seguenti:

1. Configura una nuova connessione di destinazione Adobe Campaign Managed Cloud Services per attivare un segmento/pubblico e inviare tali dati ad Adobe Campaign.

   Fornisci i dettagli sull’istanza di Campaign da utilizzare, seleziona i segmenti da attivare per la destinazione, quindi configura gli attributi da esportare in Campaign.

   [Scopri come creare una connessione di destinazione Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Configura una nuova connessione sorgente Adobe Campaign Managed Cloud Services per acquisire gli eventi Campaign in Adobe Experience Platform.

   Fornisci dettagli sull’istanza Campaign e sullo schema da utilizzare, seleziona un set di dati in cui acquisire i dati, quindi configura i campi da recuperare.

   [Scopri come creare una connessione sorgente Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)
