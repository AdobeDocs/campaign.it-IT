---
product: Adobe Campaign
title: Impostazioni del canale e-mail di Campaign
description: Impostazioni del canale e-mail di Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 6%

---

# Impostazioni del canale e-mail di Campaign

## Ccn e-mail

Puoi configurare Adobe Campaign per mantenere una copia delle e-mail inviate dalla piattaforma.

>[!NOTE]
>La funzionalità CCN dell’e-mail è facoltativa. Controlla il contratto di licenza.

Adobe Campaign non gestisce i file archiviati. Permette infatti di inviare i messaggi di tua scelta a un indirizzo dedicato, dal quale possono essere elaborati e archiviati utilizzando un sistema esterno.

A questo scopo, i file .eml corrispondenti alle e-mail inviate vengono trasferiti a un server remoto, ad esempio un server e-mail SMTP. La destinazione di archiviazione è un indirizzo e-mail CCN (invisibile ai destinatari della consegna) che devi specificare.

Tieni presente che:

* È possibile utilizzare solo **un indirizzo e-mail** CCN.

* Vengono prese in considerazione solo le e-mail inviate con successo. I messaggi non recapitati non lo sono.

[!DNL :speech_balloon:] In qualità di utente di Cloud Services gestiti,  [contatta ](../start/campaign-faq.md#support) Adobe per attivare Ccn e-mail in Campaign. L’indirizzo e-mail CCN desiderato deve essere fornito al team di Adobe che lo configurerà per te.

Una volta configurato il CCN dell’e-mail, accertati che la funzione sia abilitata nel modello di consegna o nella consegna tramite l’opzione **CCN dell’e-mail** .

![](assets/email-bcc.png)


**Argomenti correlati** nella documentazione di Campaign Classic v7:


[!DNL :arrow_upper_right:] [Genera la pagina speculare](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page)

[!DNL :arrow_upper_right:] [Selezionare il formato e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats)

[!DNL :arrow_upper_right:] [Seleziona codifica caratteri](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding)

[!DNL :arrow_upper_right:] [Impostare l&#39;indirizzo e-mail non recapitato](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails)

[!DNL :arrow_upper_right:] [Utilizzare i modelli di consegna e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=it)

[!DNL :arrow_upper_right:] [Errori di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html)
