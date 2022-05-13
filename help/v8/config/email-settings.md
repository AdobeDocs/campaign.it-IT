---
title: Impostazioni del canale e-mail di Campaign
description: Impostazioni del canale e-mail di Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 9457652f62810eb401c4010acd9b5da42d88d796
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 6%

---

# Impostazioni del canale e-mail di Campaign

## Ccn e-mail {#email-bcc}

>[!NOTE]
>
>Questa funzionalità è disponibile a partire da Campaign v8.3. Per verificare la versione, consulta [questa sezione](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

Puoi configurare Adobe Campaign per mantenere una copia delle e-mail inviate dalla piattaforma.

Adobe Campaign non gestisce i file archiviati. Permette infatti di inviare i messaggi di tua scelta a un indirizzo e-mail dedicato CCN (copia in carbonio per ciechi), da dove possono essere elaborati e archiviati utilizzando un sistema esterno. I file .eml corrispondenti alle e-mail inviate possono quindi essere trasferiti a un server remoto, ad esempio un server di posta elettronica SMTP.

>[!CAUTION]
>
>Per motivi di privacy, le e-mail CCN devono essere elaborate da un sistema di archiviazione in grado di memorizzare informazioni personali (PII) sicure.

La destinazione di archiviazione è l’indirizzo e-mail CCN desiderato, che rimarrà invisibile ai destinatari della consegna.

![](../assets/do-not-localize/speech.png)  Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support){target=&quot;_blank&quot;} per comunicare l&#39;indirizzo e-mail CCN da utilizzare per l&#39;archiviazione.

Una volta definito l’indirizzo e-mail CCN, devi abilitare l’opzione dedicata a livello di consegna.

>[!CAUTION]
>
>Quando crei un nuovo modello di consegna o consegna, **[!UICONTROL Email BCC]** non è abilitato per impostazione predefinita. È necessario abilitarlo manualmente nel modello di consegna o consegna e-mail.


Per farlo, segui la procedura indicata di seguito:

1. Vai a **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]** oppure **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Seleziona la consegna desiderata o duplica la preconfigurata **[!UICONTROL Email delivery]** , quindi seleziona il modello duplicato.
1. Fai clic sul pulsante **[!UICONTROL Properties]**.
1. Seleziona la scheda **[!UICONTROL Delivery]**.
1. Seleziona l’opzione **[!UICONTROL Email BCC]**.

   ![](assets/email-bcc.png)

1. Seleziona **[!UICONTROL Ok]**.

Una copia di tutti i messaggi inviati per ogni consegna basata su questo modello verrà inviata all’indirizzo CCN dell’e-mail configurato.

Prendi nota delle seguenti specificità e raccomandazioni:

* Puoi utilizzare un solo indirizzo e-mail CCN.

* Assicurati che l’indirizzo CCN abbia una capacità di ricezione sufficiente per archiviare tutte le e-mail inviate.

* Ccn e-mail <!--with Enhanced MTA--> consegna all’indirizzo e-mail Ccn prima della consegna ai destinatari, il che può comportare l’invio di messaggi CCN anche se le consegne originali potrebbero essere rimbalzate. Per ulteriori informazioni sui rimbalzi, vedi [Comprendere gli errori di consegna](../send/delivery-failures.md).

* Se le e-mail inviate all’indirizzo CCN vengono aperte e fai clic su di esse, questo verrà preso in considerazione nella sezione **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** dall’analisi dell’invio, che potrebbe causare alcuni calcoli errati.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7**

* [Genera la pagina speculare](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#generating-mirror-page){target=&quot;_blank&quot;}

* [Selezionare il formato e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target=&quot;_blank&quot;}

* [Seleziona codifica caratteri](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target=&quot;_blank&quot;}

* [Impostare l&#39;indirizzo e-mail non recapitato](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target=&quot;_blank&quot;}

* [Utilizzare i modelli di consegna e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-delivery-templates/about-templates.html?lang=it){target=&quot;_blank&quot;}

* [Comprendere gli errori di consegna](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/monitoring-deliveries/understanding-delivery-failures.html){target=&quot;_blank&quot;}
