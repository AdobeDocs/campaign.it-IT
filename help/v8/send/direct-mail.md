---
title: Inviare direct mailing con Adobe Campaign
description: Introduzione alla direct mailing in Campaign
feature: Direct Mail
role: User
level: Beginner
exl-id: ff2be012-72f3-428d-a973-196fea7ec4ab
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 13%

---

# Creare consegne di direct mailing

Le consegne tramite direct mailing ti consentono di generare un file di estrazione che contiene dati sulla popolazione target. Puoi quindi condividere questo file con il provider che distribuirà i messaggi alle popolazioni target.

I passaggi per generare il file sono i seguenti:

1. Creare la consegna

   Crea una consegna direct mailing in base al modello. È possibile duplicare e configurare il modello incorporato di **[!UICONTROL Deliver by direct mail (paper)]**.

   Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html){target="_blank"}

1. Definire il pubblico

   I profili dei destinatari devono contenere almeno i propri nomi e indirizzi postali.

   Gli indirizzi postali sono campi calcolati. Per impostazione predefinita, un indirizzo può contenere fino a sei righe: la prima contiene il nome e il cognome, le righe successive contengono l’indirizzo postale (strada, ecc.) e l’ultima riga contiene il codice postale o ZIP e la città o città. La definizione del campo postalAddress predefinito calcolato può essere rivista nello schema nms:recipient.

   Un indirizzo è considerato completo se il nome, il campo CAP e i campi città non sono vuoti. Tutti i destinatari con indirizzi incompleti saranno esclusi dalle consegne di direct mailing.

   Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html){target="_blank"}

1. Definire il contenuto del file

   Utilizza l’estrazione guidata per definire le informazioni (colonne) da esportare nel file di output.

   Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html){target="_blank"}

1. Convalidare la consegna

   Verificare il risultato dell&#39;analisi e il contenuto del file di output.

   Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html){target="_blank"}

   Nel contesto di una campagna di marketing, alla data di estrazione viene creato il file di estrazione. Puoi visualizzare il contenuto del file estratto, approvarlo o modificare il formato e, se necessario, riavviare l’estrazione. Una volta approvato il file, è possibile inviare il messaggio di notifica al router. Per ulteriori informazioni, consulta [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-approval.html?lang=it)

1. Avviare la consegna

   Dopo aver convalidato il file di estrazione, fai clic su **Conferma consegna** un messaggio di conferma ti consente di avviare la consegna.

   La conferma avvia l’estrazione dei dati nel file specificato.

   Nel contesto di una campagna di marketing, quando tutte le approvazioni sono state concesse, i file di estrazione vengono creati tramite un flusso di lavoro speciale che, in una configurazione predefinita, si avvia automaticamente quando una consegna direct mailing è in attesa di estrazione. Per ulteriori informazioni, consulta [questa sezione](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-deliveries.html?lang=it){target="_blank"}.
