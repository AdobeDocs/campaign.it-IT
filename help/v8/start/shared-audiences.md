---
title: Condividere tipi di pubblico con le soluzioni Adobe Experience Cloud
description: Scopri come condividere i tipi di pubblico con le soluzioni Adobe Experience Cloud
feature: Subscriptions
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 100%

---

# Condividere tipi di pubblico con le soluzioni Adobe Experience Cloud{#shared-audiences}


Opzione 1: origini e destinazioni AEP

Opzione 2: Adobe People/AAM

È possibile integrare **Adobe Campaign** con il **servizio core People** o Adobe Audience Manager. Potrai quindi:

* Importare tipi di pubblico/segmenti condivisi da diverse soluzioni Adobe Experience Cloud in Adobe Campaign. I tipi di pubblico possono essere importati tramite elenchi in Adobe Campaign.

* Esportare elenchi sotto forma di tipi di pubblico condivisi di Adobe Experience Cloud. Questi tipi di pubblico possono essere utilizzati nelle diverse soluzioni Adobe Experience Cloud che utilizzi. I tipi di pubblico possono essere esportati dopo il targeting in un flusso di lavoro, utilizzando un’attività **[!UICONTROL Update shared audience]**.

Questa integrazione supporta due tipi di ID Adobe Experience Cloud:

* **ID visitatore**: questo tipo di identificatore riconcilia i visitatori di Adobe Experience Cloud con i destinatari di Adobe Campaign.
* **ID dichiarato**: questo tipo di identificatore riconcilia tutti i tipi di dati con gli elementi del database Adobe Campaign. In Adobe Campaign è rappresentato come chiave di riconciliazione predefinita.

  >[!NOTE]
  >
  > L’origine dati ID dichiarato ora piò essere utilizzata anche con l’integrazione del servizio core People.
  >
  >Se utilizzi l’integrazione con il servizio core People e desideri aggiungere l’integrazione con Audience Manager, ti servirà l’aiuto di un consulente Adobe Audience Manager per evitare di perdere tutte le sincronizzazioni ID raccolte durante la transizione all’utilizzo dell’origine dati ID dichiarato in un contesto Adobe Audience Manager.

A questo proposito, consulta la sezione:

[https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=it](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=it)

[https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=it](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=it)
