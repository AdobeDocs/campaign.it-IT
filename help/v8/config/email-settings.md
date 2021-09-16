---
title: Impostazioni del canale e-mail di Campaign
description: Impostazioni del canale e-mail di Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '289'
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

? In qualità di utente di Cloud Services gestiti, [contatta Adobe](../start/campaign-faq.md#support) per attivare CCN e-mail in Campaign. L’indirizzo e-mail CCN desiderato deve essere fornito al team di Adobe che lo configurerà per te.

Una volta configurato il CCN dell’e-mail, accertati che la funzione sia abilitata nel modello di consegna o nella consegna tramite l’opzione **CCN dell’e-mail** .

![](assets/email-bcc.png)


**Argomenti correlati** nella documentazione di Campaign Classic v7:


↗️ [Genera la pagina speculare](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

↗️ [Seleziona formato e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

↗️ [Selezionare la codifica dei caratteri](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

↗️ [Imposta indirizzo e-mail non recapitato](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

↗️ [Utilizza modelli di consegna e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=it){target=&quot;_blank&quot;}

↗️ [Comprendere gli errori di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
