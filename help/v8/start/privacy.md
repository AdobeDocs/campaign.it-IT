---
title: Gestire le richieste di accesso ai dati personali in Campaign
description: Scopri come gestire le richieste di accesso ai dati personali in Campaign
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 0f81d318-dbfd-45c8-b391-b1d14d23e9c8
source-git-commit: 41a213eea434b3fc6ee8b3ea3c29d4364f9c9761
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 72%

---

# Gestire le richieste di accesso ai dati personali in Campaign {#privacy}

A seconda della natura della tua attività e delle giurisdizioni in cui opera, le tue operazioni sui dati possono essere soggette alle normative sulla privacy legali. Questi regolamenti danno spesso ai clienti il diritto di richiedere l&#39;accesso ai dati raccolti e il diritto di richiedere l&#39;eliminazione dei dati memorizzati. Le richieste dei clienti per i loro dati personali sono indicate come &quot;richieste di privacy&quot; in tutta la documentazione.

Adobe offre ai titolari del trattamento strumenti per creare ed elaborare richieste di accesso ai dati personali per i dati memorizzati in Adobe Campaign. In qualità di titolare del trattamento, avrai pertanto la responsabilità di confermare l’identità dell’interessato che presenta la richiesta e confermare che i dati restituiti al richiedente riguardano l’interessato. Ulteriori informazioni sui dati personali e sulle diverse entità che gestiscono i dati nella [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it#personal-data){target=&quot;_blank&quot;}.


Per gestire la richiesta di accesso a dati personali in Campaign, devi prima [definire uno spazio dei nomi](#namespaces). Puoi quindi creare e gestire le richieste di accesso a dati personali. Per eseguire le richieste di privacy, utilizza il **Adobe Privacy Service** integrazione. Le richieste di privacy inviate da Privacy Service a tutte le soluzioni Adobe Experience Cloud vengono gestite automaticamente da Campaign tramite un flusso di lavoro dedicato. [Ulteriori informazioni](#create-privacy-request)

![](../assets/do-not-localize/speech.png) Informazioni sul **Diritto di accesso** e **Diritto all’oblio** (elimina richiesta) nella [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=it#right-access-forgotten){target=&quot;_blank&quot;}.


>[!NOTE]
>
>Questa funzionalità è disponibile a partire da Campaign v8.3. Per verificare la versione, consulta [questa sezione](compatibility-matrix.md#how-to-check-your-campaign-version-and-buildversion)

## Definire uno spazio dei nomi {#namespaces}

Prima di creare una richiesta di accesso a dati personali, devi **definire lo spazio dei nomi** da utilizzare. Lo spazio dei nomi è la chiave utilizzata per identificare l’interessato nel database.

>[!NOTE]
>
>Ulteriori informazioni sugli spazi dei nomi delle identità in [Documentazione di Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=it){target=&quot;_blank&quot;}.

Al momento Adobe Campaign non supporta l’importazione di spazi dei nomi dal servizio Identity Namespace di Experience Platform . Pertanto, dopo aver creato uno spazio dei nomi nel servizio Identity Namespace, devi creare manualmente lo spazio dei nomi corrispondente nell’interfaccia di Adobe Campaign. Per farlo, segui la procedura indicata di seguito.

<!--v7?
Three namespaces are available out-of-the-box: email, phone and mobile phone. If you need a different namespace (a recipient custom field, for example), you can create a new one from **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]**.

>[!NOTE]
>
>For optimal performance, it is recommended to use out-of-the-box namespaces.
-->

1. Crea uno spazio dei nomi nel [servizio Namespace Identity](https://developer.adobe.com/experience-platform-apis/references/identity-service/#tag/Identity-Namespace){target=&quot;_blank&quot;}.

1. Quando [elenco dei namespace di identità](https://developer.adobe.com/experience-platform-apis/references/identity-service/#operation/getIdNamespaces){target=&quot;_blank&quot;} disponibile per la tua organizzazione, ottieni lo spazio dei nomi nei seguenti dettagli, ad esempio:

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

1. In Adobe Campaign, cerca **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL Namespaces]** e seleziona **[!UICONTROL New]**.

   ![](assets/privacy-namespaces-new.png)

1. Inserisci un **[!UICONTROL Label]**.

1. Inserisci i nuovi dettagli dello spazio dei nomi per far corrispondere lo spazio dei nomi creato nel servizio Identity Namespace:

   * la **[!UICONTROL AEC Namespace ID]** deve corrispondere all&#39;attributo &quot;id&quot;
   * la **[!UICONTROL Internal name]** deve corrispondere all&#39;attributo &quot;code&quot;
   * la **[!UICONTROL Reconciliation key]** deve corrispondere all&#39;attributo &quot;idType&quot;

   ![](assets/privacy-namespaces-details.png)

   Il campo **[!UICONTROL Reconciliation key]** verrà utilizzato per identificare l’interessato nel database di Adobe Campaign.

1. Seleziona una mappatura target <!--(**[!UICONTROL Recipients]**, **[!UICONTROL Real time event]** or **[!UICONTROL Subscriptions]**)--> per specificare come verrà riconciliato lo spazio dei nomi in Adobe Campaign.

   >[!NOTE]
   >
   >Se devi utilizzare diverse mappature di destinazione, crea un namespace per ogni mappatura di destinazione.

1. Salva le modifiche.

Ora puoi creare richieste di accesso a dati personali in base al nuovo spazio dei nomi. Se utilizzi più spazi dei nomi, crea una richiesta di accesso a dati personali per ogni spazio dei nomi per lo stesso valore di riconciliazione.

## Creare una richiesta di accesso a dati personali {#create-privacy-request}

La **[!DNL Adobe Experience Platform Privacy Service]** l’integrazione consente di automatizzare le richieste di privacy in un contesto con più soluzioni tramite una singola chiamata API JSON. Adobe Campaign gestisce automaticamente le richieste inviate dal servizio per la privacy tramite un flusso di lavoro dedicato.

Per scoprire come creare richieste di accesso a dati personali dal servizio core per la privacy, fai riferimento alla documentazione del [servizio per la privacy di Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=it){target=&quot;_blank&quot;}

Ogni **[!DNL Privacy Service]**  il processo viene suddiviso in più richieste di Privacy in Adobe Campaign in base al numero di spazi dei nomi utilizzati, una richiesta corrispondente a uno spazio dei nomi.

È inoltre possibile eseguire un processo su più istanze. In questo caso vengono creati più file per un processo. Ad esempio, se una richiesta ha due spazi di nomi ed è in esecuzione in tre istanze, vengono inviati in totale sei file. Un file per ogni spazio dei nomi e istanza.

Il modello per il nome di un file è: `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: il nome dell’istanza Campaign
* **NamespaceId**: l’ID spazio dei nomi di Identity Service per lo spazio dei nomi utilizzato
* **ReconciliationKey**: la chiave di riconciliazione codificata

>[!CAUTION]
>
>Per inviare una richiesta utilizzando il tipo di spazio dei nomi personalizzato, sfrutta il [metodo JSON](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=it#json){target=&quot;_blank&quot;} e aggiungi namespaceId alla richiesta, oppure utilizza la [chiamata API](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/privacy-jobs.html?lang=it#access-delete){target=&quot;_blank&quot;} per effettuare la richiesta.
>
>Per inviare richieste utilizzando il tipo di spazio dei nomi standard, utilizza solo l’[interfaccia utente Privacy](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/user-guide.html?lang=it#request-builder){target=&quot;_blank&quot;}.

### Tabelle cercate durante l’elaborazione delle richieste {#list-of-tables}

Durante l’esecuzione di una richiesta di eliminazione o di accesso ai dati personali, Adobe Campaign cerca tutti i dati dell’interessato in base al **[!UICONTROL Reconciliation value]** in tutte le tabelle che presentano un collegamento alla tabella dei destinatari (di tipo proprio).

L’elenco delle tabelle integrate prese in considerazione durante l’esecuzione delle richieste di Privacy è:

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

Di seguito sono riportati i diversi stati delle richieste di accesso a dati personali in Adobe Campaign e come interpretarle:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: in corso, il flusso di lavoro non ha ancora elaborato la richiesta.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: il flusso di lavoro sta elaborando la richiesta.
* **[!UICONTROL Delete pending]**: il flusso di lavoro ha identificato tutti i dati del destinatario da eliminare.
* **[!UICONTROL Delete in progress]**: il flusso di lavoro sta elaborando l’eliminazione.
* **[!UICONTROL Complete]**: l’elaborazione della richiesta è andata a buon fine.
* **[!UICONTROL Error]**: il flusso di lavoro ha rilevato un errore. Il motivo viene visualizzato nell’elenco delle richieste di accesso a dati personali nella colonna **[!UICONTROL Request status]**. Ad esempio, **[!UICONTROL Error data not found]** significa che nel database non è stato trovato nessun dato del destinatario corrispondente al **[!UICONTROL Reconciliation value]** dell’interessato.

**Argomenti correlati nella documentazione di Campaign Classic v7:**

* [Privacy e consenso](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it){target=&quot;_blank&quot;}

* [Guida introduttiva alla gestione della privacy](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=it){target=&quot;_blank&quot;}

* [Regolamenti sulla gestione della privacy](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=it#privacy-management-regulations){target=&quot;_blank&quot;} (GDPR, CCPA, PDPA e LGPD)

* [Rinuncia alla vendita di informazioni personali](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-requests/privacy-requests-ccpa.html?lang=it){target=&quot;_blank&quot;} (specifico per CCPA)
