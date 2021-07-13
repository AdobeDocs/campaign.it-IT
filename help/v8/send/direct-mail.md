---
product: Adobe Campaign
title: Inviare direct mailing con Adobe Campaign
description: Guida introduttiva alla direct mailing in Campaign
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: c61d8aa8e0a68ccc81a6141782f860daf061bc61
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 12%

---

# Creare consegne di direct mailing

Le consegne di direct mailing ti consentono di generare un file di estrazione che contiene dati sulla popolazione target. Puoi quindi condividere questo file con il provider che invierà i messaggi alle popolazioni target.

I passaggi per generare il file sono i seguenti:

1. Creare la consegna

   Crea una consegna di direct mailing basata sul modello . Puoi duplicare e configurare il modello **[!UICONTROL Deliver by direct mail (paper)]** incorporato.

   ↗️ Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/creating-a-direct-mail-delivery.html)

1. Definire il pubblico

   I profili dei destinatari devono contenere almeno i loro nomi e indirizzi postali.

   Gli indirizzi postali sono campi calcolati. Per impostazione predefinita, un indirizzo può contenere fino a sei righe: la prima contiene il nome e il cognome, le righe successive contengono l&#39;indirizzo postale (strada, ecc.) e l&#39;ultima riga contiene il codice postale o ZIP e la città o città.

   Un indirizzo viene considerato completo se i campi nome, CAP e città non sono vuoti.

   ↗️ Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/key-steps-when-creating-a-delivery/steps-defining-the-target-population.html)

1. Definire il contenuto del file

   Utilizza la procedura guidata di estrazione per definire le informazioni (colonne) da esportare nel file di output.

   ↗️ Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/defining-the-direct-mail-content.html)

1. Convalidare la consegna

   Controlla il risultato dell&#39;analisi e il contenuto del file di output.

   ↗️ Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-direct-mail/validating.html)

   Nel contesto di una campagna di marketing, alla data di estrazione viene creato il file di estrazione. Puoi visualizzare il contenuto del file estratto, approvarlo o modificarne il formato e riavviarlo, se necessario. Una volta approvato il file, è possibile inviare l&#39;e-mail di notifica al router.

   ↗️ Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html#approving-an-extraction-file)

1. Avvia la consegna

   Dopo aver convalidato il file di estrazione, fai clic su **Conferma consegna** per visualizzare un messaggio di conferma che ti consente di avviare la consegna.

   La conferma avvia l’estrazione dei dati nel file specificato.

   Nel contesto di una campagna di marketing, quando tutte le approvazioni sono state concesse, i file di estrazione vengono creati tramite un flusso di lavoro speciale che, in una configurazione predefinita, viene avviato automaticamente quando una consegna direct mailing è in attesa di estrazione.

   ↗️ Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html#starting-an-offline-delivery)