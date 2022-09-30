---
title: Utilizzare Campaign e Adobe Analytics
description: Scopri come integrare Campaign e Analytics
feature: Analytics Integration, Reporting
role: Admin, User
level: Beginner, Intermediate
exl-id: 11370fb6-e192-4626-944e-b80a7496e50d
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 76%

---

# Utilizzare Campaign e Adobe Analytics

Puoi configurare Adobe Analytics per integrare Campaign e Analytics.

Questa integrazione consente ad Adobe Campaign e Adobe Analytics di interagire attraverso **Connettori di Web Analytics** add-on. Questa integrazione invia ad Adobe Analytics gli indicatori e gli attributi delle campagne e-mail inviate da Adobe Campaign.

![](../assets/do-not-localize/speech.png)  Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support) per collegare Campaign ai servizi e alle soluzioni Adobe Experience Cloud. Il componente aggiuntivo per connettore Web Analytics deve essere installato nell’ambiente tramite il pacchetto dedicato.

Utilizzando il connettore Adobe Analytics, Adobe Campaign ha un modo di misurare il pubblico Internet (analisi web). Gli strumenti di analisi web consentono ad Adobe Campaign di inoltrare indicatori e attributi della campagna ad Analytics.

Il perimetro di azione di ogni utensile è il seguente:

* **Adobe Analytics** contrassegna le campagne e-mail avviate con Adobe Campaign

* **Adobe Campaign** invia gli indicatori e gli attributi della campagna al connettore, che a sua volta li inoltra allo strumento di analisi web


>[!CAUTION]
>
>Il connettore Adobe Analytics non è compatibile con la messaggistica transazionale (Centro messaggi).

Per impostare la connessione Campaign-Analytics, è necessario eseguire le operazioni seguenti:

1. [Creare la suite di rapporti in Adobe Analytics](#report-suite-analytics)
1. [Configurare le variabili di conversione e gli eventi di successo](#configure-conversion-success)
1. [Configurare l’account esterno in Adobe Campaign](#external-account-ac)

## Creare la suite di rapporti di Analytics {#report-suite-analytics}

Per creare **[!UICONTROL Report suite]** in [!DNL Adobe Analytics], segui i passaggi seguenti:

1. Da [!DNL Adobe Analytics], seleziona la **[!UICONTROL Admin tab]** e fai clic su **[!UICONTROL All admin]**.

   ![](assets/analytics_connnector_1.png)

1. Fai clic su **[!UICONTROL Report suites]**.

   ![](assets/analytics_connnector_2.png)

1. Dalla pagina **[!UICONTROL Report suite manager]**, fai clic su **[!UICONTROL Create new]** e quindi su **[!UICONTROL Report suite]**.

   Per la procedura dettagliata sulla creazione di **[!UICONTROL Report suite]**, consulta questa [sezione](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/new-report-suite/t-create-a-report-suite.html?lang=it#prerequisites).

   ![](assets/analytics_connnector_3.png)

1. Seleziona un modello.

1. Configura la nuova suite di rapporti con le seguenti informazioni:

   * **[!UICONTROL Report Suite ID]**
   * **[!UICONTROL Site Title]**
   * **[!UICONTROL Time Zone]**
   * **[!UICONTROL Go Live Date]**
   * **[!UICONTROL Estimated Page Views Per Day]**

   ![](assets/analytics_connnector_4.png)

1. Una volta configurata, fai clic su **[!UICONTROL Create report suite]**.

## Configurare le variabili di conversione e gli eventi di successo {#configure-conversion-success}

Dopo aver creato la **[!UICONTROL Report suite]**, è necessario configurare **[!UICONTROL Conversion variables]** e **[!UICONTROL Success events]** come segue:

1. Seleziona la **[!UICONTROL Report suite]** configurata in precedenza.

1. Dal pulsante **[!UICONTROL Edit settings]**, seleziona **[!UICONTROL Conversion]** > **[!UICONTROL Conversion variables]**.

   ![](assets/analytics_connnector_5.png)

1. Fai clic su **[!UICONTROL Add new]** per creare gli identificatori necessari per misurare l’impatto della campagna e-mail, ovvero il nome della campagna interna (cid) e l’ID della tabella iNmsBroadlog (bid).

   Per informazioni su come modificare le **[!UICONTROL Conversion variables]**, consulta questa [sezione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/t-conversion-variables-admin.html?lang=it#admin-tools).

   ![](assets/analytics_connnector_6.png)

1. Al termine della configurazione, fai clic su **[!UICONTROL Save]**.

1. Quindi, per creare **[!UICONTROL Success events]**, seleziona **[!UICONTROL Conversion]** > **[!UICONTROL Success events]** dal pulsante **[!UICONTROL Edit settings]**.

   ![](assets/analytics_connnector_7.png)

1. Fai clic su **[!UICONTROL Add new]** per configurare i seguenti **[!UICONTROL Success events]**:

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

   Per informazioni su come configurare **[!UICONTROL Success events]**, consulta questa [sezione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/success-events/t-success-events.html?lang=it#admin-tools)

   ![](assets/analytics_connnector_8.png)

1. Al termine della configurazione, fai clic su **[!UICONTROL Save]**.

Quando la suite di rapporti è configurata, dovrai configurare gli **[!UICONTROL External accounts]** in Adobe Campaign.

## Configurare l’account esterno di Campaign {#external-account-ac}

Ora devi configurare l’account esterno **[!UICONTROL Web Analytics]** in Adobe Campaign per abilitare la sincronizzazione tra le due soluzioni.

Nota che se uno dei **[!UICONTROL Report suite]**, **[!UICONTROL Conversion variables]** o **[!UICONTROL Success events]** non è visibile durante la configurazione dell’account esterno, significa che manca un’autorizzazione per questo componente appena creato nel **[!UICONTROL Product profile]** associato all’utente.

Per ulteriori informazioni, consulta la pagina [Profili di prodotto per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=it#product-profile-admins).

1. Vai alla cartella **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External accounts]** della struttura Adobe Campaign e fai clic su **[!UICONTROL New]**.

   ![](assets/analytics_connnector_9.png)

1. Utilizza l’elenco a discesa per selezionare il tipo **[!UICONTROL Web Analytics]** e **[!UICONTROL Adobe Analytics]** dal menu a discesa **[!UICONTROL Integration]**.

   ![](assets/analytics_connnector_10.png)

1. Fai clic su **[!UICONTROL Configure]** accanto al menu a discesa **[!UICONTROL Integration]**.

1. Dalla finestra **[!UICONTROL Configure Analytics integration]**, mappa il tuo account esterno con la suite di rapporti creata in precedenza, fornendo le seguenti informazioni:

   * **[!UICONTROL E-Mail]**
   * **[!UICONTROL IMS Org]**
   * **[!UICONTROL Analytics Company]**
   * **[!UICONTROL Report Suite]**


1. Dalla categoria **[!UICONTROL eVars]**, mappa le due **[!UICONTROL Conversion variables]** configurate in [!DNL Adobe Analytics].

   ![](assets/analytics_connnector_11.png)

1. Dalla categoria **[!UICONTROL Events]**, mappa i dieci **[!UICONTROL Success events]** configurati in [!DNL Adobe Analytics].

1. Al termine della configurazione, fai clic su **[!UICONTROL Submit]**. Adobe Campaign creerà una **[!UICONTROL Data source]**, **[!UICONTROL Calculated metrics]**, **[!UICONTROL Remarketing segments]** e **[!UICONTROL Classifications]** nella **[!UICONTROL Report Suite]** mappata di Analytics.

   Al termine della sincronizzazione tra [!DNL Adobe Analytics] e Adobe Campaign, puoi chiudere la finestra.

1. Le impostazioni possono essere visualizzate dalla scheda **[!UICONTROL Data Settings]** della finestra **[!UICONTROL Configure Analytics integration]**.

   Utilizzando il pulsante **[!UICONTROL Sync]**, [!DNL Adobe Campaign] sincronizzerà le modifiche al nome effettuate in [!DNL Adobe Analytics]. Se il componente viene eliminato in [!DNL Adobe Analytics], il componente verrà barrato in [!DNL Adobe Campaign] o visualizzato con un messaggio **non trovato**.

   ![](assets/analytics_connnector_12.png)

   >[!NOTE]
   >
   > Non puoi aggiungere o rimuovere segmenti in questa versione di Campaign v8.

1. Dall’**[!UICONTROL External account]**, fai clic sul collegamento **[!UICONTROL Enrich the formula...]** per modificare la formula di calcolo dell’URL per specificare le informazioni sull’integrazione dello strumento di analisi web (ID campagna) e i domini dei siti di cui è necessario tenere traccia dell’attività.

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

   * **[!UICONTROL Lifespan]**: consente di specificare il ritardo (in giorni) dopo il quale gli eventi web vengono recuperati in Adobe Campaign dai flussi di lavoro tecnici. Predefinito: 180 giorni.
   * **[!UICONTROL Persistence]**: consente di specificare il periodo durante il quale tutti gli eventi web (ad esempio, un acquisto) possono essere attribuiti a una campagna di remarketing, predefinito: 7 giorni.

>[!NOTE]
>
>Se utilizzi diversi strumenti di misurazione del pubblico, puoi selezionare **[!UICONTROL Other]** nell’elenco a discesa **[!UICONTROL Partners]** durante la creazione dell’account esterno. Puoi fare riferimento a un solo account esterno nelle proprietà di consegna: sarà quindi necessario adattare la formula degli URL tracciati aggiungendo i parametri previsti dallo strumento di misurazione Adobe e da tutti gli altri strumenti di misurazione utilizzati.

## Flusso di lavoro tecnico dei processi di analisi web {#technical-workflows-of-web-analytics-processes}

Lo scambio di dati tra Adobe Campaign e Adobe Analytics è gestito da un flusso di lavoro tecnico che viene eseguito come attività in background.

Questo flusso di lavoro è disponibile nella struttura di Esplora risorse di Campaign, sotto **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]** > **[!UICONTROL Web analytics process]** cartella.

![](assets/webanalytics_workflows.png)

La **[!UICONTROL Sending of indicators and campaign attributes]** flusso di lavoro consente di inviare gli indicatori della campagna e-mail tramite Adobe Campaign a Adobe Experience Cloud utilizzando il connettore Adobe Analytics. Questo flusso di lavoro viene attivato alle 4 del mattino ogni giorno e possono essere necessarie 24 ore per l’invio dei dati ad Analytics.

Tieni presente che questo flusso di lavoro non deve essere riavviato altrimenti invierà nuovamente tutti i dati precedenti che possono distorcere i risultati di Analytics.

Gli indicatori interessati sono i seguenti:

* **[!UICONTROL Messages to deliver]** (@toDeliver)
* **[!UICONTROL Processed]** (@processed)
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
* **[!UICONTROL Label]** (operation/@label): solo se il pacchetto **Campaign** è installato
* **[!UICONTROL Nature]** (operation/@nature): solo se il pacchetto **Campaign** è installato
* **[!UICONTROL Tag 1]** (webAnalytics/@tag1)
* **[!UICONTROL Tag 2]** (webAnalytics/@tag2)
* **[!UICONTROL Tag 3]** (webAnalytics/@tag3)
* **[!UICONTROL Contact date]** (scheduling/@contactDate)

## Tracciare le consegne {#tracking-deliveries-in-adobe-campaign}

Affinché Adobe Experience Cloud sia in grado di monitorare l’attività sui siti una volta inviata la consegna da Adobe Campaign, è necessario fare riferimento al connettore corrispondente nelle proprietà di consegna. A questo scopo, esegui i seguenti passaggi:

1. Apri la consegna della campagna da tracciare.

   ![](assets/webanalytics_delivery_properties_003.png)

1. Apri le proprietà di consegna.
1. Vai alla scheda **[!UICONTROL Web Analytics]** e seleziona l’account esterno creato in precedenza. Consulta [Configurare l’account esterno in Adobe Campaign](#external-account-ac).

   ![](assets/webanalytics_delivery_properties_002.png)

1. Ora puoi inviare la consegna e accedere al relativo rapporto in Adobe Analytics.


**Argomenti correlati**

* [Campaign - Integrazione di Experience Cloud Triggers](ac-triggers.md)
