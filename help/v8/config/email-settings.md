---
title: Impostazioni del canale e-mail della campagna
description: Impostazioni del canale e-mail della campagna
feature: Email
role: User
level: Intermediate, Experienced
exl-id: e4e3fb49-9942-4e2d-a020-557d1ac5dcdc
source-git-commit: 1baeb8827a0eab4f9487bb5e5afe4d779e00efe4
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 5%

---

# Impostazioni del canale e-mail della campagna

## Invia e-mail in Ccn {#email-bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

Puoi configurare Adobe Campaign per conservare una copia delle e-mail inviate dalla tua piattaforma.

Adobe Campaign stessa non gestisce i file archiviati. Consente di inviare i messaggi desiderati a un indirizzo e-mail Ccn (copia nascosta) dedicato, da cui possono essere elaborati e archiviati utilizzando un sistema esterno. I file .eml corrispondenti alle e-mail inviate possono quindi essere trasferiti su un server remoto, ad esempio un server e-mail SMTP.

>[!CAUTION]
>
>Per motivi di privacy, le e-mail in formato Ccn devono essere elaborate da un sistema di archiviazione in grado di memorizzare informazioni personali (PII) protette.

La destinazione di archiviazione è l’indirizzo e-mail Ccn scelto, che rimarrà invisibile ai destinatari della consegna.

![](../assets/do-not-localize/speech.png)  In qualità di utente di Managed Cloud Services, [Adobe di contatto](../start/campaign-faq.md#support){target="_blank"} per comunicare l&#39;indirizzo e-mail Ccn da utilizzare per l&#39;archiviazione.

Una volta definito l’indirizzo e-mail Ccn, devi abilitare l’opzione dedicata a livello di consegna.

>[!CAUTION]
>
>Durante la creazione di un nuovo modello di consegna o consegna, **[!UICONTROL Email BCC]** non è attivato per impostazione predefinita. Devi abilitarlo manualmente nel modello di consegna e-mail o.


A tale scopo, segui la procedura indicata di seguito:

1. Vai a **[!UICONTROL Campaign Management]** > **[!UICONTROL Deliveries]**, o **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Seleziona la consegna desiderata o duplica la preconfigurata **[!UICONTROL Email delivery]** , quindi selezionare il modello duplicato.
1. Fai clic sul pulsante **[!UICONTROL Properties]**.
1. Seleziona la scheda **[!UICONTROL Delivery]**.
1. Seleziona l’opzione **[!UICONTROL Email BCC]**.

   ![](assets/email-bcc.png)

1. Seleziona **[!UICONTROL Ok]**.

Una copia di tutti i messaggi inviati per ogni consegna basata su questo modello verrà inviata all’indirizzo e-mail Ccn configurato.

Considera le seguenti specificità e raccomandazioni:

* È possibile utilizzare un solo indirizzo e-mail Ccn.

* Assicurati che l’indirizzo Ccn disponga di una capacità di ricezione sufficiente per archiviare tutte le e-mail inviate.

* CCN e-mail <!--with Enhanced MTA--> effettua la consegna all’indirizzo e-mail Ccn prima di effettuare la consegna ai destinatari; ciò può comportare l’invio di messaggi Ccn anche se le consegne originali potrebbero essere state non consegnate. Per ulteriori informazioni sui mancati recapiti, consulta [Errori di consegna](../send/delivery-failures.md).

* Se le e-mail inviate all’indirizzo Ccn vengono aperte e cliccate attraverso, questo verrà preso in considerazione nel **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** dall’analisi di invio, che potrebbe causare alcuni errori di calcolo.

<!--Only successfully sent emails are taken in account, bounces are not.-->

**Ulteriori informazioni**

In queste sezioni:

* [Utilizzare i modelli di consegna e-mail](../send/create-templates.md)

* [Errori di consegna](../send/delivery-failures.md)


E nella documentazione di Campaign Classic v7:

* [Seleziona formato e-mail](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#selecting-message-formats){target="_blank"}

* [Seleziona codifica caratteri](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#character-encoding){target="_blank"}

* [Impostare l’indirizzo e-mail di mancato recapito](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-emails/sending-an-email/email-parameters.html#managing-bounce-emails){target="_blank"}

