---
title: Condivisione di tipi di pubblico con le soluzioni Adobe Experience Cloud
description: Scopri come condividere i tipi di pubblico con le soluzioni Adobe Experience Cloud
feature: Subscriptions
role: User
level: Beginner
hide: true
hidefromtoc: true
source-git-commit: ec46a6f41d640b11306a88d6a966f81f8c2e43e0
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 5%

---

# Condivisione di tipi di pubblico con le soluzioni Adobe Experience Cloud{#shared-audiences}


Opzione 1: Origini e destinazioni AEP

Opzione 2: Adobe People/AAM

È possibile integrare **Adobe Campaign** con **Servizio core persone** o Adobe Audience Manager. Potrai quindi:

* Importa tipi di pubblico/segmenti condivisi da diverse soluzioni Adobe Experience Cloud in Adobe Campaign. I tipi di pubblico possono essere importati tramite elenchi in Adobe Campaign.

* Esporta elenchi sotto forma di tipi di pubblico condivisi di Adobe Experience Cloud. Questi tipi di pubblico possono essere utilizzati nelle diverse soluzioni Adobe Experience Cloud che utilizzi. I tipi di pubblico possono essere esportati dopo il targeting in un flusso di lavoro, utilizzando un **[!UICONTROL Update shared audience]** attività.

Questa integrazione supporta due tipi di ID Adobe Experience Cloud:

* **ID visitatore**: questo tipo di identificatore concilia i visitatori di Adobe Experience Cloud con i destinatari di Adobe Campaign.
* **ID dichiarato**: questo tipo di identificatore riconcilia tutti i tipi di dati con gli elementi del database Adobe Campaign. È rappresentato in Adobe Campaign come chiave di riconciliazione predefinita.

   >[!NOTE]
   >
   > L’origine dati Declared ID (ID dichiarato) può ora essere utilizzata anche con l’integrazione del servizio core People.
   >
   >Se utilizzi l’integrazione del servizio core Persone e desideri aggiungere l’integrazione di Audience Manager, ti servirà l’aiuto di un consulente Adobe Audience Manager per evitare di perdere tutte le sincronizzazioni ID raccolte durante la transizione all’utilizzo di questa origine dati Declared ID in un contesto Adobe Audience Manager.

A questo proposito, consulta la sezione:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=en)
