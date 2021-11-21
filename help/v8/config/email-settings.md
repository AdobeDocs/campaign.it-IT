---
title: Impostazioni del canale e-mail di Campaign
description: Impostazioni del canale e-mail di Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
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

* Puoi utilizzare solo **uno** Indirizzo e-mail CCN.

* Vengono prese in considerazione solo le e-mail inviate con successo. I messaggi non recapitati non lo sono.

![](../assets/do-not-localize/speech.png)  Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support) per attivare Ccn e-mail in Campaign. L’indirizzo e-mail CCN desiderato deve essere fornito al team di Adobe che lo configurerà per te.

Una volta configurato il CCN dell’e-mail, assicurati che la funzione sia abilitata nel modello di consegna o nella consegna tramite il **Ccn e-mail** opzione .

![](assets/email-bcc.png)


**Argomenti correlati** nella documentazione di Campaign Classic v7:


* [Genera la pagina speculare](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

* [Selezionare il formato e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

* [Seleziona codifica caratteri](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

* [Impostare l&#39;indirizzo e-mail non recapitato](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

* [Utilizzare i modelli di consegna e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=it){target=&quot;_blank&quot;}

* [Comprendere gli errori di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
