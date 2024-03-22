---
title: Invia una copia dei messaggi a un indirizzo Ccn
description: Scopri come attivare il campo CCN dell’e-mail in Adobe Campaign
feature: Email
role: User
level: Beginner
exl-id: 35702b81-1984-4a62-8f00-c2bc32ab2b42
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 1%

---

# Invia una copia dei messaggi a un indirizzo Ccn {#bcc}

<!--
>[!NOTE]
>
>This capability is available starting Campaign v8.3. To check your version, refer to [this section](../start/compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)-->

## Informazioni su CCN e-mail {#gs-bcc}

Puoi configurare Adobe Campaign per conservare una copia delle e-mail inviate dalla tua piattaforma. Questa opzione consente di inviare ai messaggi un indirizzo e-mail Ccn (Blind Carbon Copy) dedicato, da cui possono essere elaborati e archiviati utilizzando un sistema esterno.
Adobe Campaign stessa non gestisce i file archiviati. I file .eml corrispondenti alle e-mail inviate possono quindi essere trasferiti su un server remoto, ad esempio un server e-mail SMTP.

La destinazione di archiviazione è l’indirizzo e-mail Ccn scelto, che rimarrà invisibile ai destinatari della consegna. Una volta definito l’indirizzo e-mail Ccn, devi abilitare l’opzione dedicata in [modello di consegna](create-templates.md) livello.

>[!NOTE]
>
>In qualità di utente di Managed Cloud Service, [Adobe di contatto](../start/campaign-faq.md#support){target="_blank"} per comunicare l&#39;indirizzo e-mail Ccn da utilizzare per l&#39;archiviazione.

>[!CAUTION]
>
>Per motivi di privacy, le e-mail in formato Ccn devono essere elaborate da un sistema di archiviazione in grado di memorizzare informazioni personali (PII) protette.


## Abilita CCN e-mail {#enable-bcc}

Per abilitare Ccn per un [modello di consegna](create-templates.md), effettua le seguenti operazioni:

1. Da Esplora campagne, passa alla cartella dei modelli di consegna. Per impostazione predefinita, i modelli di consegna sono memorizzati in **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** cartella.
1. Modifica il modello di consegna da aggiornare con Ccn.
1. Fai clic sul pulsante **[!UICONTROL Properties]**.
1. Dalla sezione **[!UICONTROL Delivery]** , selezionare la scheda **[!UICONTROL Email BCC]** opzione.

   ![](assets/email-bcc.png)

1. Fai clic su **[!UICONTROL Ok]** per confermare.

Una copia di tutti i messaggi inviati per ogni consegna basata su questo modello verrà inviata all’indirizzo e-mail Ccn configurato per la piattaforma.

## Guardrail e raccomandazioni {#recommendations-bcc}

Quando utilizzi CCN e-mail con Adobe Campaign, si applicano i seguenti guardrail e consigli:

* È possibile utilizzare un solo indirizzo e-mail Ccn.

* Assicurati che l’indirizzo Ccn disponga di una capacità di ricezione sufficiente per archiviare tutte le e-mail inviate.

* CCN e-mail <!--with Enhanced MTA--> effettua la consegna all’indirizzo e-mail Ccn prima di effettuare la consegna ai destinatari; ciò può comportare l’invio di messaggi Ccn anche se le consegne originali potrebbero essere state non consegnate. Per ulteriori informazioni sui mancati recapiti, consulta [Errori di consegna](delivery-failures.md).

* Le e-mail inviate all’indirizzo Ccn non devono essere aperte e cliccate attraverso, in quanto tali attività vengono prese in considerazione nella sezione **[!UICONTROL Total opens]** e **[!UICONTROL Clicks]** dall’analisi di invio, può causare errori di calcolo.

<!--Only successfully sent emails are taken in account, bounces are not.-->
