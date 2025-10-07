---
title: Inviare direct mailing con Adobe Campaign
description: Introduzione alla direct mailing in Campaign
feature: Direct Mail
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 110a2cac920ca3087f6fcb3cab8474729f6075be
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 5%

---

# Creare consegne di direct mailing

Le consegne tramite direct mailing ti consentono di generare un file di estrazione che contiene dati sulla popolazione target. Puoi quindi condividere questo file con il provider che distribuirà i messaggi alle popolazioni target.

I passaggi per generare il file sono i seguenti:

1. [Creare la consegna](#creating-a-direct-mail-delivery)
1. [Definire il pubblico](#defining-the-direct-mail-audience)
1. [Definire il contenuto del file](#defining-the-direct-mail-content)
1. [Convalidare la consegna](#validating)
1. [Avviare la consegna](#start-delivery)

## Creare la consegna{#creating-a-direct-mail-delivery}

Crea una consegna direct mailing in base al modello. È possibile duplicare e configurare il modello incorporato di **[!UICONTROL Deliver by direct mail (paper)]**.

Per creare una nuova consegna di direct mailing, segui i passaggi seguenti:

>[!NOTE]
>
>I concetti globali sulla creazione della consegna sono presentati in [questa sezione](../start/create-message.md).

1. Crea una nuova consegna, ad esempio dal dashboard Consegna.
1. Selezionare il modello di consegna **Consegna tramite direct mailing (carta)**.

   ![](assets/direct_mail.png)

1. Identifica la consegna con un’etichetta, un codice e una descrizione. Per ulteriori informazioni al riguardo, consulta [questa sezione](../start/create-message.md#create-the-delivery).
1. Fai clic su **Continua** per confermare queste informazioni e visualizzare la finestra di configurazione del messaggio.

## Definire il pubblico{#defining-the-direct-mail-audience}

I profili dei destinatari devono contenere almeno i propri nomi e indirizzi postali.

Gli indirizzi postali sono campi calcolati. Per impostazione predefinita, un indirizzo può contenere fino a sei righe: la prima contiene il nome e il cognome, le righe successive contengono l’indirizzo postale (strada, ecc.) e l’ultima riga contiene il codice postale o ZIP e la città o città. La definizione del campo postalAddress predefinito calcolato può essere rivista nello schema nms:recipient.

Un indirizzo è considerato completo se il nome, il campo CAP e i campi città non sono vuoti. Tutti i destinatari con indirizzi incompleti saranno esclusi dalle consegne di direct mailing.

Per ulteriori informazioni, consulta [questa sezione](../start/create-message.md#target-population).

## Definire il contenuto del file{#defining-the-direct-mail-content}

Utilizza l’estrazione guidata per definire le informazioni (colonne) da esportare nel file di output.

Il nome del file che contiene i dati estratti è definito nel campo **[!UICONTROL File]**. Il pulsante a destra del campo consente di utilizzare i campi di personalizzazione per creare il nome del file.

Per impostazione predefinita, il file di estrazione viene creato e memorizzato sul server. È possibile salvarlo nel computer. Per eseguire questa operazione, controllare **[!UICONTROL Download the generated file after the analysis of the delivery]**. In questo caso, è necessario indicare il percorso di accesso alla directory di archiviazione locale e il nome del file.

![](assets/s_ncs_user_mail_delivery_local_file.png)

Per una consegna direct mailing, il contenuto dell&#39;estrazione è definito nel collegamento **[!UICONTROL Edit the extraction file format...]**.

![](assets/s_ncs_user_mail_delivery_format_link.png)

Questo collegamento ti consente di accedere all’assistente per l’estrazione e definire le informazioni (colonne) da esportare nel file di output.

![](assets/s_ncs_user_mail_delivery_format_wz.png)

Puoi inserire un URL personalizzato nel file di estrazione. Per ulteriori informazioni, consulta la [documentazione](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-forms/publishing-a-web-form.html?lang=it){target="_blank"} di Adobe Campaign Classic.

>[!NOTE]
>
>L&#39;assistente include i passaggi dell&#39;assistente all&#39;esportazione descritti nella [documentazione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/importing-and-exporting-data/generic-imports-exports/executing-export-jobs.html?lang=it){target="_blank"} di Adobe Campaign Classic.

## Convalidare la consegna{#validating}

Verificare il risultato dell&#39;analisi e il contenuto del file di output.

Nel contesto di una campagna di marketing, alla data di estrazione viene creato il file di estrazione. Puoi visualizzare il contenuto del file estratto, approvarlo o modificare il formato e, se necessario, riavviare l’estrazione. Una volta approvato il file, è possibile inviare il messaggio di notifica al router. Per ulteriori informazioni, consulta [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=it){target="_blank"}.

I concetti globali durante la convalida di una consegna sono presentati in [questa sezione](../start/create-message.md#validate-the-delivery).

Il file di output di una consegna direct mailing viene generato durante l’analisi della consegna. Il contenuto del file dipende dalle colonne di output selezionate (fare riferimento a questo [file di sezione](#defining-the-direct-mail-content)).

>[!NOTE]
>
>La fase di analisi è descritta in questa [sezione](delivery-analysis.md).

Durante la fase di analisi, viene generato il file ma le informazioni relative ai destinatari (ovvero i registri di consegna) non vengono aggiornate. È quindi possibile annullare questo processo senza correre rischi.

Controllare il risultato dell&#39;analisi e il contenuto del file di output prima di fare clic su **[!UICONTROL Confirm delivery]**. Un messaggio di conferma ti consente di avviare la consegna.

La conferma di invio avvia l’estrazione dei dati nel file specificato.

![](assets/s_ncs_user_postal_del_send_confirm_postal.png)

È quindi possibile chiudere l&#39;assistente e visualizzare i registri di consegna tramite la scheda **[!UICONTROL Delivery]**, accessibile tramite i dettagli di consegna.

Puoi configurare la modalità di recupero dei registri di consegna dalla scheda **[!UICONTROL Analysis]** delle proprietà di consegna.

Esistono due modalità:

* **[!UICONTROL Messages are considered sent after validation]** (modalità predefinita): in questa modalità funzione, tutti i broadLog vengono aggiornati quando l&#39;operatore conferma l&#39;invio (il loro stato passa da &quot;Consegna in sospeso&quot; a &quot;Inviato&quot;) e la consegna viene impostata automaticamente su **[!UICONTROL Finished]**.
* **[!UICONTROL A file of results determines the messages that are sent and those that have failed]** : questa modalità consente di aggiornare i broadLog tramite un file esterno inviato dal provider di servizi. In questo caso, è necessario utilizzare un flusso di lavoro per elaborare queste informazioni al fine di aggiornare lo stato del registro di trasmissione.

  >[!NOTE]
  >
  >In questo caso, non appena i broadLog vengono aggiornati, anche lo stato della consegna deve essere modificato in **[!UICONTROL Finished]** dall&#39;utente.

## Avviare la consegna{#start-delivery}

Dopo aver convalidato il file di estrazione, fai clic su **Conferma consegna** un messaggio di conferma ti consente di avviare la consegna.

La conferma avvia l’estrazione dei dati nel file specificato.

Nel contesto di una campagna di marketing, quando tutte le approvazioni sono state concesse, i file di estrazione vengono creati tramite un flusso di lavoro speciale che, in una configurazione predefinita, si avvia automaticamente quando una consegna direct mailing è in attesa di estrazione. Per ulteriori informazioni, consulta [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=it){target="_blank"}.
