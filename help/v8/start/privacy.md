---
title: Gestire le richieste di accesso ai dati personali in Campaign
description: Scopri come gestire le richieste di accesso ai dati personali in Campaign
feature: Audiences
role: Admin
level: Beginner, Intermediate, Experienced
exl-id: 0f81d318-dbfd-45c8-b391-b1d14d23e9c8
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 90%

---

# Gestire le richieste di accesso ai dati personali in Campaign {#privacy}

A seconda della natura della tua attività e delle giurisdizioni in cui opera, le tue operazioni sui dati possono essere soggette a normative legali sulla privacy. Tali nornmative solitamente tutelano il diritto dei clienti di richiedere l’accesso ai dati raccolti su di loro e memorizzati, e di richiederne l’eliminazione. In questa documentazione, tali richieste sono dette “richieste di accesso a dati personali” o “richieste Privacy”.

Adobe offre ai titolari del trattamento strumenti per creare ed elaborare richieste di accesso ai dati personali per i dati memorizzati in Adobe Campaign. In qualità di titolare del trattamento, avrai pertanto la responsabilità di confermare l’identità dell’interessato che presenta la richiesta e confermare che i dati restituiti al richiedente riguardano l’interessato. Ulteriori informazioni sui dati personali e sulle diverse entità che gestiscono i dati nella [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it#personal-data){target="_blank"}.


Per gestire le richieste di accesso a dati personali in Campaign, devi prima [definire uno spazio dei nomi](#namespaces). Dopodiché puoi creare e gestire le richieste Privacy. Per eseguire le richieste di accesso a dati personali, utilizza l’integrazione **Adobe Privacy Service**. Le richieste di accesso a dati personali inviate da Privacy Service a tutte le soluzioni Adobe Experience Cloud vengono gestite automaticamente da Campaign tramite un flusso di lavoro dedicato. [Ulteriori informazioni](#create-privacy-request)

![](../assets/do-not-localize/speech.png) Informazioni sul **Diritto di accesso** e **Diritto all’oblio** (richiesta DELETE) nella [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=it#right-access-forgotten){target="_blank"}.


>[!NOTE]
>
>Questa funzionalità è disponibile a partire da Campaign v8.3. Per verificare la versione, consulta [questa sezione](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion).

## Definire uno spazio dei nomi {#namespaces}

Prima di creare una richiesta di accesso a dati personali, devi **definire lo spazio dei nomi** che userai. Lo spazio dei nomi è la chiave utilizzata per identificare l’interessato nel database.

>[!NOTE]
>
>Per ulteriori informazioni sugli spazi dei nomi delle identità, consulta la [documentazione di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=it){target="_blank"}.

Al momento Adobe Campaign non supporta l’importazione di spazi dei nomi dal servizio Identity Namespace di Experience Platform . Pertanto, dopo aver creato uno spazio dei nomi nel servizio Identity Namespace, devi creare manualmente lo spazio dei nomi corrispondente nell’interfaccia di Adobe Campaign. Per farlo, segui la procedura indicata di seguito.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. Crea uno spazio dei nomi nel [servizio Namespace Identity](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace){target="_blank"}.

1. Quando [elenco degli spazi dei nomi di identità](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target="_blank"} disponibile per la tua organizzazione, otterrai lo spazio dei nomi nei seguenti dettagli, ad esempio:

   ```
   {
           "updateTime": 1632903236731,
           "code": "lumanamespace",
           "status": "ACTIVE",
           "description": "new namespace for Luma privacy requests",
           "id": 10998717,
           "createTime": 1632903236731,
           "idType": "Email",
           "namespaceType": "Custom",
           "name": "Luma Namespace",
           "custom": true
   }
   ```

1. In Adobe Campaign, passa a **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]** e seleziona **[!UICONTROL New]**.

   ![](assets/privacy-namespaces-new.png)

1. Inserisci un **[!UICONTROL Label]**.

1. Inserisci i nuovi dettagli dello spazio dei nomi per far corrispondere lo spazio dei nomi creato nel servizio Identity Namespace:

   * il valore **[!UICONTROL AEC Namespace ID]** deve corrispondere all’attributo “id”;
   * il valore **[!UICONTROL Internal name]** deve corrispondere all’attributo “code”;
   * il valore **[!UICONTROL Reconciliation key]** deve corrispondere all’attributo “idType”.

   ![](assets/privacy-namespaces-details.png)

   Il campo **[!UICONTROL Reconciliation key]** verrà utilizzato per identificare l’interessato nel database di Adobe Campaign.

1. Seleziona una mappatura target <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)--> per specificare come verrà riconciliato lo spazio dei nomi in Adobe Campaign.

   >[!NOTE]
   >
   >Per utilizzare più mappature target, crea uno spazio dei nomi per ogni mappatura target.

1. Salva le modifiche.

Ora puoi creare richieste di accesso a dati personali in base al nuovo spazio dei nomi. Se utilizzi più spazi dei nomi, crea una richiesta di accesso a dati personali per ogni spazio dei nomi per lo stesso valore di riconciliazione.

## Creare una richiesta di accesso a dati personali {#create-privacy-request}

L’integrazione di **[!DNL Adobe Experience Platform Privacy Service]** consente di automatizzare le richieste di accesso a dati personali in un contesto multisoluzione tramite una singola chiamata API JSON. Adobe Campaign gestisce automaticamente le richieste inviate da Privacy Service tramite un flusso di lavoro dedicato.

Per scoprire come creare richieste di accesso a dati personali dal servizio core per la privacy, fai riferimento alla documentazione del [Privacy Service di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html).{target="_blank"}

Ciascun processo **[!DNL Privacy Service]** è suddiviso in più richieste Privacy in Adobe Campaign in base al numero di spazi dei nomi utilizzati. A ogni richiesta corrisponde uno spazio dei nomi.

È inoltre possibile eseguire un processo su più istanze. In questo caso vengono creati più file per un processo. Ad esempio, se una richiesta ha due spazi di nomi ed è in esecuzione in tre istanze, vengono inviati in totale sei file. Un file per ogni spazio dei nomi e istanza.

Il modello per il nome di un file è: `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: il nome dell’istanza Campaign
* **NamespaceId**: l’ID spazio dei nomi di Identity Service per lo spazio dei nomi utilizzato
* **ReconciliationKey**: la chiave di riconciliazione codificata

>[!CAUTION]
>
>Per inviare una richiesta utilizzando il tipo di spazio dei nomi personalizzato, sfrutta [metodo JSON](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html#json){target="_blank"} and add the namespaceId to the request, or use the [API call](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html#access-delete){target="_blank"} per effettuare la richiesta.
>
>Utilizza solo il [Interfaccia utente Privacy](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html#request-builder){target="_blank"} per inviare richieste utilizzando il tipo di spazio dei nomi standard.

### Tabelle cercate durante l’elaborazione delle richieste {#list-of-tables}

Durante l’esecuzione di una richiesta di eliminazione o di accesso ai dati personali, Adobe Campaign cerca tutti i dati dell’interessato in base al **[!UICONTROL Reconciliation value]** in tutte le tabelle che presentano un collegamento alla tabella dei destinatari (di tipo proprio).

L’elenco delle tabelle integrate prese in considerazione durante l’esecuzione delle richieste di accesso a dati personali è:

* Destinatari (recipient)
* Registro delle consegne ai destinatari (broadLogRcp)
* Registro di tracciamento dei destinatari (trackingLogRcp)
* Registro di consegna degli eventi archiviati (broadLogEventHisto)
* Contenuto dell’elenco destinatari (rcpGrpRel)
* Proposta di offerta del visitatore (propositionVisitor)
* Visitatori (visitor)
* Storico abbonamenti (subHisto)
* Abbonamenti (subscription)
* Proposta di offerta del destinatario (propositionRcp)

Se hai creato tabelle personalizzate con un collegamento alla tabella dei profili (di tipo proprio), anche queste verranno considerate. Ad esempio, se disponi di una tabella di transazioni collegata alla tabella dei destinatari e una tabella di dettagli delle transazioni collegata alla tabella delle transazioni, verranno entrambe considerate.
<!--
>[!CAUTION]
>
>If you perform Privacy batch requests using profile deletion workflows, please take into consideration the following remarks:
>* Profile deletion via workflows do not process children tables.
>* You need to handle the deletion for all the children tables.
>* Adobe recommends that you create an ETL workflow that add the lines to delete in the Privacy Access table and let the **[!UICONTROL Delete privacy requests data]** workflow perform the deletion. We suggest to limit to 200 profiles per day to delete for performance reasons.-->

### Stati delle richieste di accesso a dati personali {#privacy-request-statuses}

Di seguito sono riportati i diversi stati delle richieste di accesso a dati personali in Adobe Campaign e come interpretarli:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: in corso, il flusso di lavoro non ha ancora elaborato la richiesta.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: il flusso di lavoro sta elaborando la richiesta.
* **[!UICONTROL Delete pending]**: il flusso di lavoro ha identificato tutti i dati del destinatario da eliminare.
* **[!UICONTROL Delete in progress]**: il flusso di lavoro sta elaborando l’eliminazione.
* **[!UICONTROL Complete]**: l’elaborazione della richiesta è andata a buon fine.
* **[!UICONTROL Error]**: il flusso di lavoro ha rilevato un errore. Il motivo viene visualizzato nell’elenco delle richieste di accesso a dati personali nella colonna **[!UICONTROL Request status]**. Ad esempio, **[!UICONTROL Error data not found]** significa che nel database non è stato trovato nessun dato del destinatario corrispondente al **[!UICONTROL Reconciliation value]** dell’interessato.

**Argomenti correlati nella documentazione di Campaign Classic v7:**

* [Privacy e consenso](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it){target="_blank"}

* [Guida introduttiva alla gestione della privacy](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=it){target="_blank"}

* [Normative sulla gestione della privacy](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=it#privacy-management-regulations){target="_blank"} (GDPR, CCPA, PDPA e LGPD)

* [Rinuncia alla vendita di informazioni personali](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html?lang=it){target="_blank"} (specifico per CCPA)
