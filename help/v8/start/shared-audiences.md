---
title: Condividere tipi di pubblico con le soluzioni Adobe Experience Cloud
description: Scopri come condividere i tipi di pubblico con le soluzioni Adobe Experience Cloud
feature: Audiences
role: User
level: Beginner
hide: true
exl-id: c4d30771-db5e-40be-8af6-50f0fab9f9af
TQID: 'https://experienceleague.adobe.com/Q7eY7lPXlHWEcaj-Hx4Bbqj-hwzMvrlxGGYeN5AxzRE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 76%
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

[Documentazione di Adobe Audience Manager](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=it){target="_blank"}

[Guida ai componenti dell’interfaccia centrale di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/services/audiences/audience-library.html?lang=it){target="_blank"}

