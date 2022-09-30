---
title: Utilizzare Campaign e Adobe Experience Platform
description: Scopri come utilizzare Campaign e Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 0%

---

# Utilizzare Campaign e Adobe Experience Platform

I connettori sorgente e di destinazione del Cloud Service gestito di Adobe Campaign consentono un’integrazione diretta tra Adobe Campaign e Adobe Experience Platform:

* Utilizzo **Connettore Origini gestite da Adobe Campaign** per inviare segmenti di Experience Platform ad Adobe Campaign per l’attivazione,

   ![](assets/aep-destination.png)

* Utilizzo **Connettore di destinazione Adobe Campaign Managed Cloud** per inviare i registri di consegna e tracciamento di Adobe Campaign a Adobe Experience Platform.

   ![](assets/aep-logs.png)

I passaggi per configurare questa integrazione in Adobe Experience Platform sono i seguenti:

1. Configura una nuova connessione di destinazione Adobe Campaign Managed Cloud Services per attivare un segmento/pubblico e inviare tali dati ad Adobe Campaign.

   Fornisci i dettagli sull’istanza Campaign da utilizzare, seleziona i segmenti da attivare per la destinazione, quindi configura gli attributi da esportare in Campaign.

   [Scopri come creare una connessione di destinazione Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

1. Configura una nuova connessione sorgente Adobe Campaign Managed Cloud Services per acquisire eventi Campaign in Adobe Experience Platform.

   Fornisci i dettagli sull’istanza Campaign e sullo schema da utilizzare, seleziona un set di dati in cui acquisire i dati, quindi configura i campi da recuperare.

   [Scopri come creare una connessione sorgente Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)
