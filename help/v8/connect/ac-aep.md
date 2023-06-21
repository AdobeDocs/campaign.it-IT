---
title: Utilizzare Campaign e Adobe Experience Platform
description: Scopri come utilizzare Campaign e Adobe Experience Platform
feature: Platform Integration
role: Data Engineer
level: Beginner
exl-id: 21cf5611-ccaa-4e83-8891-a1a2353515aa
source-git-commit: f8c4e05ba2fc97d981fb31f9b11c5de1dcc1ff6e
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 9%

---

# Utilizzare Campaign e Adobe Experience Platform

I connettori di origine e destinazione del Cloud Service gestito di Adobe Campaign consentono un’integrazione ottimizzata tra Adobe Campaign e Adobe Experience Platform.

* Utilizzare un Adobe Campaign Managed Cloud Services **Connessione di destinazione** per inviare segmenti Experience Platform ad Adobe Campaign per l’attivazione:

  A questo scopo, configura un nuovo Adobe Campaign Managed Cloud Services **Connessione di destinazione** per attivare un segmento/pubblico e inviare tali dati ad Adobe Campaign. Fornisci i dettagli sull’istanza di Campaign da utilizzare, seleziona i segmenti da attivare per la destinazione, quindi configura gli attributi da esportare in Campaign. [Scopri come creare una connessione di destinazione Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/destinations-adobe-campaign-managed-cloud-services-en)

  ![](assets/aep-destination.png){width="800" align="center"}

* Utilizzare un Adobe Campaign Managed Cloud Services **Connessione sorgente** per inviare i registri di consegna e tracciamento di Adobe Campaign a Adobe Experience Platform:

  A questo scopo, configura un nuovo Adobe Campaign Managed Cloud Services **Connessione sorgente** per acquisire gli eventi di Campaign in Adobe Experience Platform. Fornisci dettagli sull’istanza Campaign e sullo schema da utilizzare, seleziona un set di dati in cui acquisire i dati, quindi configura i campi da recuperare. [Scopri come creare una connessione sorgente Adobe Campaign Managed Cloud Services](https://www.adobe.com/go/sources-campaign-ui-en)

  ![](assets/aep-logs.png){width="800" align="center"}
