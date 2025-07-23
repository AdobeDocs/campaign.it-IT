---
title: Guida introduttiva alle API REST di Campaign
description: Crea integrazioni e costruisci il tuo ecosistema interfacciando Campaign con un pannello di tecnologie.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: c6968252-a012-4029-bbb8-66f4f693e99b
source-git-commit: c74669a0ccdabe735eb905b7e8c1634140a7ea0b
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 47%

---

# Guida introduttiva alle API REST di Campaign {#get-started-apis}

>[!AVAILABILITY]
>
>Questa funzionalità è disponibile solo su richiesta, per tutti gli ambienti FDA di Campaign. È **non** disponibile per le distribuzioni FFDA di Campaign. Per ottenere l’accesso, contatta il tuo rappresentante Adobe.

>[!CAUTION]
>
>Prima di eseguire le chiamate API, controlla le limitazioni delle dimensioni che corrispondono al contratto di licenza. Per ulteriori informazioni, consulta [questa pagina](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

Le API REST di Campaign mirano a **creare integrazioni** per Adobe Campaign e **creare il proprio ecosistema** interfacciando Adobe Campaign con il pannello di tecnologie utilizzato.

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

In questa documentazione sono descritti dettagliatamente tutti gli endpoint con le nozioni generali da conoscere per la manipolazione dell’API, il riferimento API completo, gli esempi di codice e le guide di avvio rapido. Tutti gli esempi funzionano con Postman, ma puoi usare il client REST che preferisci.

Se qualcosa dovesse mancare o sembrare sbagliato, chiedi nella [community](https://experienceleaguecommunities.adobe.com/it/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community).
