---
product: Adobe Campaign
title: Utilizzare Campaign e Adobe Analytics
description: Scopri come utilizzare Campaign e Adobe Analytics
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: d1d57aa8-b811-470f-a8a6-18da3a700f1a
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '1392'
ht-degree: 0%

---

# Utilizzare Campaign e Adobe Analytics

Puoi configurare Adobe Analytics per integrare Campaign e Analytics.

Questa integrazione consente ad Adobe Campaign e Adobe Analytics di interagire attraverso il componente aggiuntivo **Connettori di Web Analytics**. Questa integrazione invia ad Adobe Analytics gli indicatori e gli attributi delle campagne e-mail inviate da Adobe Campaign.

Utilizzando il connettore Adobe Analytics, Adobe Campaign ha un modo di misurare il pubblico Internet (Web Analytics). Gli strumenti di analisi web consentono ad Adobe Campaign di inoltrare indicatori e attributi della campagna ad Analytics.

Il perimetro di azione di ogni utensile è il seguente:

* **Adobe Analytics**

   * contrassegna le campagne e-mail avviate con Adobe Campaign
   * salva il comportamento del destinatario, sotto forma di segmenti, sul sito visualizzato dopo aver fatto clic sull’e-mail della campagna. I segmenti sono collegati a prodotti abbandonati (visualizzati ma non aggiunti al carrello o acquistati), acquisti o abbandonamenti del carrello.

* **Adobe Campaign**

   * invia gli indicatori e gli attributi della campagna al connettore, che a sua volta li inoltra allo strumento di analisi web
   * recupera e analizza i segmenti
   * attiva una campagna di ricommercializzazione

[!DNL :speech_balloon:]  In qualità di utente di Cloud Services gestiti,  [contatta ](../start/campaign-faq.md#support) Adobe per integrare Adobe Analytics Connector con Campaign. Il componente aggiuntivo per connettore Web Analytics deve essere installato nell’ambiente tramite il pacchetto dedicato.


>[!CAUTION]
>
>Il connettore Adobe Analytics non è compatibile con i messaggi transazionali (Centro messaggi).

Per impostare la connessione Campaign-Analytics, è necessario eseguire le operazioni seguenti:

1. [Creare la suite di rapporti in Adobe Analytics](#report-suite-analytics)
1. [Configurare le variabili di conversione e gli eventi di successo](#configure-conversion-success)
1. [Configurare l’account esterno in Adobe Campaign](#external-account-ac)

## Crea la tua suite di rapporti in Adobe Analytics {#report-suite-analytics}

Per creare il **[!UICONTROL Report suite]** in [!DNL Adobe Analytics], segui i passaggi seguenti:

1. Da [!DNL Adobe Analytics], seleziona il **[!UICONTROL Admin tab]** e fai clic su **[!UICONTROL All admin]**.

   ![](assets/analytics_connnector_1.png)

1. Fai clic su **[!UICONTROL Report suites]**.

   ![](assets/analytics_connnector_2.png)

1. Dalla pagina **[!UICONTROL Report suite manager]**, fai clic su **[!UICONTROL Create new]** e quindi su **[!UICONTROL Report suite]**.

   Per la procedura dettagliata sulla creazione di **[!UICONTROL Report suite]**, consulta questa [sezione](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/t-create-a-report-suite.html?lang=en#prerequisites).

   ![](assets/analytics_connnector_3.png)

1. Seleziona un modello.

1. Configura la nuova suite di rapporti con le seguenti informazioni:

   * **[!UICONTROL Report Suite ID]**
   * **[!UICONTROL Site Title]**
   * **[!UICONTROL Time Zone]**
   * **[!UICONTROL Go Live Date]**
   * **[!UICONTROL Estimated Page Views Per Day]**

   ![](assets/analytics_connnector_4.png)

1. Una volta configurato, fai clic su **[!UICONTROL Create report suite]**.

## Configura le variabili di conversione e gli eventi di successo {#configure-conversion-success}

Dopo aver creato il **[!UICONTROL Report suite]**, è necessario configurare i **[!UICONTROL Conversion variables]** e **[!UICONTROL Success events]** come segue:

1. Seleziona il **[!UICONTROL Report suite]** configurato in precedenza.

1. Dal pulsante **[!UICONTROL Edit settings]**, seleziona **[!UICONTROL Conversion]** > **[!UICONTROL Conversion variables]**.

   ![](assets/analytics_connnector_5.png)

1. Fai clic su **[!UICONTROL Add new]** per creare gli identificatori necessari per misurare l’impatto della campagna e-mail, ovvero il nome della campagna interna (cid) e l’ID della tabella iNmsBroadlog (bid).

   Per informazioni su come modificare **[!UICONTROL Conversion variables]**, consulta questa [sezione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/t-conversion-variables-admin.html?lang=en#admin-tools).

   ![](assets/analytics_connnector_6.png)

1. Al termine, fai clic su **[!UICONTROL Save]** .

1. Quindi, per creare il **[!UICONTROL Success events]**, seleziona **[!UICONTROL Conversion]** > **[!UICONTROL Success events]** dal pulsante **[!UICONTROL Edit settings]**.

   ![](assets/analytics_connnector_7.png)

1. Fai clic su **[!UICONTROL Add new]** per configurare quanto segue **[!UICONTROL Success events]**:

   * **[!UICONTROL Clicked]**
   * **[!UICONTROL Opened]**
   * **[!UICONTROL Person clicks]**
   * **[!UICONTROL Processed]**
   * **[!UICONTROL Scheduled]**
   * **[!UICONTROL Sent]**
   * **[!UICONTROL Total bounces]**
   * **[!UICONTROL Unique Clicks]**
   * **[!UICONTROL Unique Opens]**
   * **[!UICONTROL Unsubscribed]**

   Per informazioni su come configurare **[!UICONTROL Success events]**, consulta questa [sezione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/t-success-events.html?lang=en#admin-tools)

   ![](assets/analytics_connnector_8.png)

1. Al termine, fai clic su **[!UICONTROL Save]** .

Quando la suite di rapporti è configurata, dovrai configurare il **[!UICONTROL External accounts]** in Adobe Campaign.

## Configurare l’account esterno in Adobe Campaign {#external-account-ac}

Ora devi configurare l’account esterno **[!UICONTROL Web Analytics]** in Adobe Campaign per abilitare la sincronizzazione tra le due soluzioni.

Nota che se uno dei **[!UICONTROL Report suite]**, **[!UICONTROL Conversion variables]** o **[!UICONTROL Success events]** non è visibile durante la configurazione dell’account esterno, significa che manca un’autorizzazione per questo componente appena creato nel **[!UICONTROL Product profile]** associato all’utente.

Per ulteriori informazioni, consulta la pagina [Profili di prodotto per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=en#product-profile-admins) .

1. Vai alla cartella **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External accounts]** della struttura Adobe Campaign e fai clic su **[!UICONTROL New]**.

   ![](assets/analytics_connnector_9.png)

1. Utilizza l’elenco a discesa per selezionare il tipo **[!UICONTROL Web Analytics]** e **[!UICONTROL Adobe Analytics]** dal menu a discesa **[!UICONTROL Integration]**.

   ![](assets/analytics_connnector_10.png)

1. Fai clic su **[!UICONTROL Configure]** accanto al menu a discesa **[!UICONTROL Integration]** .

1. Dalla finestra **[!UICONTROL Configure Analytics integration]** , mappa il tuo account esterno con la suite di rapporti creata in precedenza, fornendo le seguenti informazioni:

   * **[!UICONTROL E-Mail]**
   * **[!UICONTROL IMS Org]**
   * **[!UICONTROL Analytics Company]**
   * **[!UICONTROL Report Suite]**

1. Dalla categoria **[!UICONTROL eVars]** , mappa i due **[!UICONTROL Conversion variables]** configurati in [!DNL Adobe Analytics].

   ![](assets/analytics_connnector_11.png)

1. Dalla categoria **[!UICONTROL Events]** , mappa i dieci **[!UICONTROL Success events]** configurati in [!DNL Adobe Analytics].

1. Al termine, fai clic su **[!UICONTROL Submit]** . Adobe Campaign creerà un **[!UICONTROL Data source]**, **[!UICONTROL Calculated metrics]**, **[!UICONTROL Remarketing segments]** e **[!UICONTROL Classifications]** nell&#39;Analytics mappato **[!UICONTROL Report Suite]**.

   Al termine della sincronizzazione tra [!DNL Adobe Analytics] e Adobe Campaign, puoi chiudere la finestra.

1. Le impostazioni possono essere visualizzate dalla scheda **[!UICONTROL Data Settings]** della finestra **[!UICONTROL Configure Analytics integration]**.

   Utilizzando il pulsante **[!UICONTROL Sync]**, [!DNL Adobe Campaign] sincronizzerà le modifiche al nome effettuate in [!DNL Adobe Analytics]. Se il componente viene eliminato in [!DNL Adobe Analytics], il componente verrà barrato in [!DNL Adobe Campaign] o visualizzato con un messaggio **non trovato**.

   ![](assets/analytics_connnector_12.png)

1. Se necessario, puoi aggiungere o rimuovere segmenti dalla scheda **[!UICONTROL Update Segments]** .

1. Dal **[!UICONTROL External account]**, fai clic sul collegamento **[!UICONTROL Enrich the formula...]** per modificare la formula di calcolo dell’URL per specificare le informazioni sull’integrazione dello strumento di analisi web (ID campagna) e i domini dei siti di cui è necessario tenere traccia dell’attività.

   ![](assets/analytics_connnector_13.png)

1. Specifica i nomi di dominio dei siti.

   ![](assets/analytics_connnector_14.png)

1. Fai clic su **[!UICONTROL Next]** e assicurati che i nomi di dominio siano stati salvati.

   ![](assets/analytics_connnector_15.png)

1. Se necessario, è possibile sovraccaricare la formula di calcolo. A questo scopo, seleziona la casella e modifica la formula direttamente nella finestra.

   >[!IMPORTANT]
   >
   >Questa modalità di configurazione è riservata agli utenti esperti: eventuali errori in questa formula possono causare consegne e-mail interrotte.

1. La scheda **[!UICONTROL Advanced]** ti consente di configurare o modificare le impostazioni tecniche.

   * **[!UICONTROL Lifespan]**: consente di specificare il ritardo (in giorni_ dopo il quale gli eventi web vengono recuperati in Adobe Campaign dai flussi di lavoro tecnici. Predefinito: 180 giorni.
   * **[!UICONTROL Persistence]**: consente di specificare il periodo durante il quale tutti gli eventi web (ad esempio, un acquisto) possono essere attribuiti a una campagna di remarketing, Predefinito: 7 giorni.

>[!NOTE]
>
>Se utilizzi diversi strumenti di misurazione del pubblico, puoi selezionare **[!UICONTROL Other]** nell’elenco a discesa **[!UICONTROL Partners]** durante la creazione dell’account esterno. Puoi fare riferimento a un solo account esterno nelle proprietà di consegna: sarà quindi necessario adattare la formula degli URL tracciati aggiungendo i parametri previsti dall’Adobe e tutti gli altri strumenti di misurazione utilizzati.

## Flussi di lavoro tecnici dei processi di analisi web {#technical-workflows-of-web-analytics-processes}

Lo scambio di dati tra Adobe Campaign e Adobe Analytics è gestito da un flusso di lavoro tecnico che viene eseguito come attività in background.

Questo flusso di lavoro è disponibile dalla struttura di Campaign Explorer, nella cartella **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** > **[!UICONTROL Web analytics process]** .

![](assets/webanalytics_workflows.png)

Il flusso di lavoro **[!UICONTROL Sending of indicators and campaign attributes]** consente di inviare gli indicatori delle campagne e-mail tramite Adobe Campaign a Adobe Experience Cloud utilizzando il connettore Adobe Analytics. Questo flusso di lavoro viene attivato alle 4 del mattino ogni giorno e può essere necessario 24 ore per l’invio dei dati ad Analytics.

Tieni presente che questo flusso di lavoro non deve essere riavviato altrimenti invierà nuovamente tutti i dati precedenti che possono distorcere i risultati di Analytics.

Gli indicatori interessati sono i seguenti:

* **[!UICONTROL Messages to deliver]** (@toDeliver)
* **[!UICONTROL Processed]** (@elaborati)
* **[!UICONTROL Success]** (@success)
* **[!UICONTROL Total count of opens]** (@totalRecipientOpen)
* **[!UICONTROL Recipients who have opened]** (@recipientOpen)
* **[!UICONTROL Total number of recipients who clicked]** (@totalRecipientClick)
* **[!UICONTROL People who clicked]** (@personClick)
* **[!UICONTROL Number of distinct clicks]** (@recipientClick)
* **[!UICONTROL Opt-Out]** (@optOut)
* **[!UICONTROL Errors]** (@error)

>[!NOTE]
>
>I dati inviati sono il delta basato sull’ultima istantanea che può portare a un valore negativo nei dati della metrica.

Gli attributi inviati sono i seguenti:

* **[!UICONTROL Internal name]** (@internalName)
* **[!UICONTROL Label]** (@label)
* **[!UICONTROL Label]** (operation/@label): solo se il pacchetto  **** Campaign è installato
* **[!UICONTROL Nature]** (operation/@nature): solo se il pacchetto  **** Campaign è installato
* **[!UICONTROL Tag 1]** (webAnalytics/@tag1)
* **[!UICONTROL Tag 2]** (webAnalytics/@tag2)
* **[!UICONTROL Tag 3]** (webAnalytics/@tag3)
* **[!UICONTROL Contact date]** (programmazione/@contactDate)

## Tracciamento delle consegne in Adobe Campaign {#tracking-deliveries-in-adobe-campaign}

Affinché Adobe Experience Cloud sia in grado di monitorare l’attività sui siti una volta inviata la consegna da Adobe Campaign, è necessario fare riferimento al connettore corrispondente nelle proprietà di consegna. A questo scopo, esegui i seguenti passaggi:

1. Apri la consegna della campagna da tracciare.

   ![](assets/webanalytics_delivery_properties_003.png)

1. Apri le proprietà di consegna.
1. Vai alla scheda **[!UICONTROL Web Analytics]** e seleziona l’account esterno creato in precedenza. Consulta [Configurare l&#39;account esterno in Adobe Campaign](#external-account-ac).

   ![](assets/webanalytics_delivery_properties_002.png)

1. Ora puoi inviare la consegna e accedere al rapporto in Adobe Analytics.

## Creazione di una campagna di remarketing {#creating-a-re-marketing-campaign}

Per preparare la campagna di remarketing, è sufficiente creare modelli di consegna da utilizzare per campagne di tipo remarketing. Quindi configura la tua campagna di remarketing e collegala a un segmento. Ogni segmento deve avere una campagna di remarketing diversa.

Le campagne di ricommercializzazione vengono avviate automaticamente una volta che Adobe Campaign ha completato il recupero dei segmenti analizzando il comportamento delle persone target della campagna iniziale. In caso di abbandono del carrello o di visualizzazione del prodotto senza acquisto, viene inviata una consegna ai destinatari interessati affinché la loro navigazione sul sito finisca in un acquisto.

Adobe Campaign fornisce modelli di consegna personalizzati su cui puoi utilizzare o creare un database per preparare le campagne.

1. Dalla cartella **[!UICONTROL Explorer]**, vai alla cartella **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** della struttura Adobe Campaign.

1. Duplica il modello **[!UICONTROL Email delivery (re-marketing)]** o gli esempi di modelli di remarketing offerti da Adobe Campaign.

   ![](assets/webanalytics_delivery_model.png)

1. Personalizza il modello in base alle tue esigenze e salvalo.

1. Crea una nuova campagna e seleziona il modello **[!UICONTROL Re-marketing campaign]** dall’elenco a discesa.

   ![](assets/webanalytics_remarketing_campaign_002.png)

1. Fai clic sul collegamento **[!UICONTROL Configure...]** per specificare il segmento e il modello di consegna collegati alla campagna.

1. Seleziona l’account esterno configurato in precedenza.

   ![](assets/webanalytics_remarketing_campaign_003.png)

1. Seleziona il segmento interessato.

   ![](assets/webanalytics_remarketing_campaign_005.png)

1. Seleziona il modello di consegna da utilizzare per la campagna di remarketing, quindi fai clic su **[!UICONTROL Finish]** per chiudere la finestra.

   ![](assets/webanalytics_remarketing_campaign_006.png)

1. Fai clic su **[!UICONTROL OK]** per chiudere la finestra della campagna.

Il rapporto **[!UICONTROL Re-marketing efficiency]** è accessibile tramite la pagina dei report globali. Ti consente di visualizzare il numero di contatti convertiti (ovvero che hai acquistato qualcosa) in relazione al numero di abbandoni del carrello a seguito della campagna di remarketing Adobe Campaign. Il tasso di conversione viene calcolato per settimana, mese o dall’inizio della sincronizzazione tra gli strumenti di Adobe Campaign e Web analytics.

![](assets/webanalytics_reporting.png)


**Argomenti correlati**

* [Campaign - Integrazione di Experience Cloud Triggers](ac-triggers.md)
