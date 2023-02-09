---
title: Utilizzare Campaign e Adobe Experience Platform
description: Scopri come utilizzare Campaign e Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---

# Utilizzare Campaign e Adobe Experience Platform

I connettori di destinazione e origine dei Cloud Service gestiti di Adobe Campaign consentono l’integrazione diretta tra Adobe Campaign e Adobe Experience Platform.

* Utilizzo **Adobe Campaign Managed Cloud Services** Connessione di destinazione per l’invio di segmenti di Experience Platform ad Adobe Campaign per l’attivazione,

   ![](assets/aep-destination.png)

* Utilizzo **Adobe Campaign Managed Cloud Services** Connessione sorgente per inviare i registri di consegna e tracciamento di Adobe Campaign a Adobe Experience Platform.

   ![](assets/aep-logs.png)

I passaggi per configurare questa integrazione in Adobe Experience Platform sono i seguenti:

1. Configura una nuova connessione di destinazione Adobe Campaign Managed Cloud Services per attivare un segmento/pubblico e inviare tali dati ad Adobe Campaign.

   Fornisci i dettagli sull’istanza Campaign da utilizzare, seleziona i segmenti da attivare per la destinazione, quindi configura gli attributi da esportare in Campaign.

   [Scopri come creare una connessione di destinazione Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Configura una nuova connessione Adobe Campaign Managed Cloud Services Source per acquisire eventi Campaign in Adobe Experience Platform.

   Fornisci i dettagli sull’istanza Campaign e sullo schema da utilizzare, seleziona un set di dati in cui acquisire i dati, quindi configura i campi da recuperare.

   [Scopri come creare una connessione sorgente Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)
