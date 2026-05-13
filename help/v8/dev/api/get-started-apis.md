---
title: Guida introduttiva alle API REST di Campaign
description: Crea integrazioni e costruisci il tuo ecosistema interfacciando Campaign con un pannello di tecnologie.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Developer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
TQID: https://experienceleague.adobe.com/RRDY-7SFGUwxHk34LLhRHaFN-0U4A9NQfNvLPXO8GM8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 240
ht-degree: 58%

---

# Guida introduttiva alle API REST di Campaign {#get-started-apis}

Le API REST di Campaign mirano a **creare integrazioni** per Adobe Campaign e **creare il proprio ecosistema** interfacciando Adobe Campaign con il pannello di tecnologie utilizzato.

>[!AVAILABILITY]
>
>* Questa funzionalità è disponibile solo su richiesta, per tutti gli [ambienti FDA di Campaign](../../architecture/fda-deployment.md). È **non** disponibile per [distribuzioni Enterprise (FFDA)](../../architecture/enterprise-deployment.md). Per ottenere l’accesso, contatta il tuo rappresentante Adobe.
>
>* Prima di eseguire le chiamate API, controlla le limitazioni delle dimensioni che corrispondono al contratto di licenza. Per ulteriori informazioni, consulta la [Descrizione del prodotto Adobe Campaign v8](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.


Con le API REST di Adobe Campaign, puoi accedere alle seguenti funzionalità:

<table><tr>
 <td valign="top"><a href="retrieving-profiles.md"><img width="60px" alt="condizioni" src="assets/icon_profile.svg"/></a><p><a href="retrieving-profiles.md">Profili</a></p></td>
<td valign="top"><a href="creating-a-service.md"><img width="60px" alt="condizioni" src="assets/icon_services.svg"/></a><p><a href="creating-a-service.md">Servizi e sottoscrizioni</a></p></td>
<td valign="top"><a href="interacting-with-custom-resources.md"><img width="60px" alt="condizioni" src="assets/icon_customresources.svg"/></a><p><a href="interacting-with-custom-resources.md">Risorse personalizzate</a></p></td>
<td valign="top"><a href="controlling-a-workflow.md"><img width="60px" alt="condizioni" src="assets/icon_workflows.svg"/></a><p><a href="controlling-a-workflow.md">Flussi di lavoro</a></p></td>
<td valign="top"><a href="managing-transactional-messages.md"><img width="60px" alt="condizioni" src="assets/icon_transactionalmessage.svg"/></a><p><a href="managing-transactional-messages.md">Messaggi transazionali</a></p></td>
</tr></table>

Per utilizzare le API REST di Campaign, è necessario un account Adobe I/O. Questo passaggio è obbligatorio per andare avanti e scoprire le funzionalità API.
Per ulteriori informazioni al riguardo, consulta [questa sezione](setting-up-api-access.md).

Le API fornite sfruttano **concetti standard** con un’interfaccia REST e payload JSON.

Questa documentazione contiene la descrizione approfondita di tutti gli endpoint con le nozioni generali da conoscere per la manipolazione dell’API, il riferimento API completo, gli esempi di codice e le guide di avvio rapido. Tutti gli esempi funzionano con Postman, ma puoi usare il client REST che preferisci.

