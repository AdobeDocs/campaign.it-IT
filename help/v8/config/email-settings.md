---
solution: Campaign
product: Adobe Campaign
title: Impostazioni del canale e-mail di Campaign
description: Impostazioni del canale e-mail di Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: 8dd7b5a99a0cda0e0c4850d14a6cb95253715803
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# Impostazioni del canale e-mail di Campaign

## Ccn e-mail

Puoi configurare Adobe Campaign per mantenere una copia delle e-mail inviate dalla piattaforma.

Tuttavia, Adobe Campaign non gestisce i file archiviati. Permette infatti di inviare i messaggi di tua scelta a un indirizzo dedicato, dal quale possono essere elaborati e archiviati utilizzando un sistema esterno.

A questo scopo, i file .eml corrispondenti alle e-mail inviate vengono trasferiti a un server remoto, ad esempio un server e-mail SMTP. La destinazione di archiviazione è un indirizzo e-mail CCN (invisibile ai destinatari della consegna) che devi specificare.

Tieni presente che:

* Puoi utilizzare un solo indirizzo e-mail CCN.

* Vengono prese in considerazione solo le e-mail inviate con successo. I messaggi non recapitati non lo sono.

Una volta configurato il CCN dell’e-mail, accertati che la funzione sia abilitata nel modello di consegna o nella consegna tramite l’opzione **CCN dell’e-mail** .

:arrow_Upper_right: Per ulteriori informazioni, consulta la [documentazione Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html?lang=en#email-bcc)

**Nota**: La funzionalità CCN dell’e-mail è facoltativa. Controlla il contratto di licenza.

:speech_balloon: In qualità di utente di Cloud Services gestiti, [contatta Adobe](../start/support.md#support) per attivare CCN e-mail in Campaign. L’indirizzo e-mail CCN desiderato deve essere fornito al team di Adobe che lo configurerà per te.