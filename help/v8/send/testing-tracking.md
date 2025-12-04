---
title: Verifica tracciamento dei messaggi
description: Scopri come verificare il tracciamento dei messaggi prima di inviare le consegne
feature: Monitoring
role: User
level: Beginner
exl-id: 16ad36b7-c13e-4b77-86ca-41c9ef174172
source-git-commit: edbe7ab49a628436dfb4d27ae17122917d7371e9
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 1%

---

# Verifica tracciamento dei messaggi {#testing-tracking}

Prima di inviare la consegna a tutto il pubblico, è essenziale testare la funzionalità di tracciamento per garantire il corretto funzionamento di tutti i collegamenti e l’acquisizione dei dati di tracciamento. Questo processo di verifica ti aiuta a identificare e risolvere eventuali problemi di tracciamento prima che la campagna venga pubblicata, evitando potenziali problemi con i reindirizzamenti dei collegamenti, il caricamento dei pixel di tracciamento o la raccolta di dati.

Il tracciamento dei test consente di:

* Verifica che tutti i collegamenti nel messaggio siano tracciati correttamente e reindirizzati correttamente
* Verifica che il collegamento alla pagina speculare funzioni e sia tracciato
* Assicurati che i pixel di tracciamento vengano caricati correttamente per il tracciamento delle aperture
* Verifica che i parametri personalizzati negli URL vengano acquisiti con precisione
* Verifica che il flusso di lavoro tecnico di tracciamento elabori correttamente i dati

Puoi verificare il tracciamento su pagine mirror, registri e collegamenti e-mail seguendo la procedura seguente:

## Passaggio 1: creare una consegna di test {#create-test-delivery}

1. Crea una nuova consegna e-mail da utilizzare per il test. [Scopri come creare una consegna](../start/create-message.md)
1. Progetta i contenuti delle e-mail con i collegamenti di cui desideri tenere traccia. [Informazioni sulla progettazione del contenuto delle e-mail](defining-the-email-content.md)
1. Aggiungi un blocco di personalizzazione della pagina speculare nel contenuto dell’e-mail. [Informazioni sui blocchi di personalizzazione](personalization-blocks.md)

   ![](assets/mirror-page-insert.png)

1. Specifica l’utente che riceverà l’e-mail. Poiché questo utente dovrà aprire l’e-mail e fare clic sui collegamenti in essa contenuti, assicurati di selezionare un indirizzo del destinatario di prova che controlli. [Informazioni sui profili di test](../audiences/test-profiles.md)

## Passaggio 2: inviare la consegna del test {#send-test}

1. Verifica che il tracciamento sia abilitato nelle impostazioni di consegna:
   * Apri **[!UICONTROL Properties]** della consegna
   * Vai alla sezione **[!UICONTROL Tracking & Images]**
   * Verifica che **[!UICONTROL Activate tracking]** sia selezionato
   * Assicurati che **[!UICONTROL Opens tracking]** sia selezionato se desideri tenere traccia delle aperture

   ![](assets/s_ncs_user_email_del_tracking_param.png)

[Ulteriori informazioni sulle opzioni di tracciamento URL](url-tracking.md)

1. Invia la consegna al destinatario del test. [Informazioni sull&#39;invio di consegne](configure-and-send.md)

## Passaggio 3: verificare la funzionalità di tracciamento {#verify-tracking}

1. Una volta ricevuta l’e-mail, aprila e fai clic sul collegamento della pagina speculare. [Informazioni sulle pagine mirror](mirror-page.md)
1. Fai clic su vari collegamenti nell’e-mail per generare i dati di tracciamento.
1. Dopo essere stato reindirizzato correttamente alla pagina mirror, accedere alla cartella **[!UICONTROL Administration > Production > Technical workflows]**. [Informazioni sui flussi di lavoro](../config/workflows.md)
1. Apri il flusso di lavoro **[!UICONTROL Tracking]**.
1. Avviare il flusso di lavoro oppure fare clic con il pulsante destro del mouse sull&#39;attività **[!UICONTROL Scheduler]** e selezionare **[!UICONTROL Execute pending task now]**.
1. Attendi circa 30 secondi prima che il flusso di lavoro elabori i registri di tracciamento.
1. Selezionare la scheda **[!UICONTROL Audit]** del flusso di lavoro. Verifica che sia stato trovato almeno un record del registro di tracciamento. Fare clic su **[!UICONTROL Refresh]** se non vengono visualizzati nuovi registri.

1. Verifica i registri di tracciamento nella consegna:
   * Torna alla consegna
   * Seleziona la scheda **[!UICONTROL Tracking]**
   * Verifica che venga visualizzato l’elenco dei registri di tracciamento con gli URL su cui hai fatto clic e altri eventi di tracciamento

   ![](assets/s_ncs_user_delivery_tracking_tab.png)

## Passaggio 4: controllare la scheda di tracciamento dei destinatari {#check-recipient-tracking}

1. Vai alla pagina del profilo del destinatario utilizzato per il test. [Informazioni sulla visualizzazione dei profili](../audiences/view-profiles.md)
   * Per impostazione predefinita, la pagina del profilo del destinatario si trova nella cartella **[!UICONTROL Profiles and Targets > Recipients]**.

1. Seleziona la scheda **[!UICONTROL Tracking]**. [Ulteriori informazioni sui registri di tracciamento](tracking-logs.md)

   ![](assets/s_ncs_user_select_tracking_tab_from_recipient.png)

1. Verifica che i record di tracciamento vengano visualizzati con:
   * Il valore **[!UICONTROL Mirror Page]** nella colonna **[!UICONTROL Type]**
   * **[!UICONTROL Open]** valori nella colonna **[!UICONTROL Type]** per le aperture e-mail
   * **[!UICONTROL Email click]** valori nella colonna **[!UICONTROL Type]** per i clic sui collegamenti

## Risoluzione dei problemi del test di tracciamento {#troubleshooting-tracking-test}

Se i registri di tracciamento non vengono visualizzati:

1. **Verifica le impostazioni di consegna**: accedi alla consegna e accedi al relativo **[!UICONTROL Properties]** per assicurarti che siano verificate sia le opzioni **[!UICONTROL Activate tracking]** che **[!UICONTROL Opens tracking]**. [Ulteriori informazioni sulle opzioni di tracciamento URL](url-tracking.md)

1. **Verifica il flusso di lavoro di tracciamento**: assicurati che il flusso di lavoro tecnico **[!UICONTROL Tracking]** sia in esecuzione senza errori. [Informazioni sulla risoluzione dei problemi del flusso di lavoro di tracciamento](tracking-logs.md#check-tracking-workflow)

1. **Verifica il formato dell&#39;URL**: verifica che gli URL siano formattati correttamente e racchiusi tra delimitatori. [Ulteriori informazioni sulla configurazione dei collegamenti tracciati](tracked-links.md)

1. **Rivedi il comportamento del client e-mail**: alcuni client e-mail potrebbero bloccare i pixel di tracciamento o modificare i collegamenti. Prova a eseguire test con client e-mail diversi. [Scopri le best practice per la consegna](../start/delivery-best-practices.md)

1. **Attesa elaborazione**: il flusso di lavoro di tracciamento viene eseguito ogni ora per impostazione predefinita. Se lo attivi manualmente, attendi un tempo sufficiente per l’elaborazione prima di verificare i risultati. [Ulteriori informazioni sui registri di tracciamento](tracking-logs.md)

## Argomenti correlati {#related-topics}

* [Scopri come configurare i collegamenti tracciati](tracked-links.md)
* [Scopri come accedere ai registri di tracciamento](tracking-logs.md)
* [Comprendere i rapporti di tracciamento](../reporting/delivery-reports.md#tracking-indicators)

