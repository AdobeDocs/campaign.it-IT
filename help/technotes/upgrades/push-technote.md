---
product: campaign
title: Modifiche imminenti del canale di notifica push
description: Modifiche imminenti del canale di notifica push
hide: true
hidefromtoc: true
source-git-commit: fc274e1266d37611c8781a007ccb6a293a683c21
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 1%

---

# Modifiche imminenti del canale di notifica push {#push-upgrade}

Puoi utilizzare Campaign per inviare notifiche push su dispositivi Android. Per eseguire questa operazione, Campaign si basa su account esterni Android specifici e servizi di abbonamento. Alcune modifiche importanti al servizio Android Firebase Cloud Messaging (FCM) saranno rilasciate nel 2024 e potrebbero influire sull’implementazione di Adobe Campaign.

## Cosa è cambiato? {#fcm-changes}

Come parte del continuo sforzo di Google per migliorare i suoi servizi, le API FCM legacy saranno interrotte il **20 giugno 2024**. Ulteriori informazioni sul protocollo HTTP Firebase Cloud Messaging in [Documentazione di Google](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 e Adobe Campaign v8 supportano già le API più recenti per l’invio di messaggi di notifica push. Tuttavia, alcune implementazioni precedenti si basano ancora sulle API legacy. Queste implementazioni devono essere aggiornate.

## Sei interessato da questo problema? {#fcm-impact}

Se l’implementazione corrente supporta i servizi di abbonamento che si connettono a FCM utilizzando le API legacy, sei interessato. Per evitare distrazioni di servizio, è necessario eseguire la migrazione alle API più recenti. In tal caso, i team di Adobi ti contatteranno.

Per verificare se sei interessato, puoi filtrare il **Servizi e abbonamenti** secondo il filtro seguente:

![](assets/filter-services-fcm.png)


* Se una delle tue campagne di notifica push attive utilizza **HTTP (legacy)** API, la configurazione sarà direttamente interessata da questa modifica. È necessario rivedere le configurazioni correnti e migrare alle API più recenti come descritto di seguito.

* Se la configurazione utilizza esclusivamente **HTTP v1** API per notifiche push Android, sei già conforme e non saranno richieste ulteriori azioni da parte tua.

## Come effettuare la migrazione?{#fcm-migration-procedure}

### Prerequisiti{#fcm-migration-prerequisites}

* Per Campaign Classic v7, il supporto di HTTP v1 è stato aggiunto nella versione 20.3.1. Se l’ambiente è in esecuzione su una versione precedente, un prerequisito per la migrazione a HTTP v1 è aggiornare l’ambiente a [build Campaign Classic più recente](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Per Campaign v8, HTTP v1 è supportato da tutte le versioni. Non è necessario alcun aggiornamento.

* Per eseguire la migrazione, è necessario il file JSON dell’account del servizio Admin SDK per Android Firebase per spostare l’app mobile su HTTPv1. Fai riferimento a questo [pagina](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Per le distribuzioni ibride, in hosting e Managed Services, contatta l’Adobe per aggiornare il server di esecuzione in tempo reale (RT).

### Procedura di migrazione {#fcm-migration-steps}

Per migrare l’ambiente a HTTP v1, segui questi passaggi sui server di esecuzione Marketing e Real-Time:

1. Sfoglia l’elenco di **Servizi e abbonamenti**.
1. Individua tutte le applicazioni mobili utilizzando **HTTP (legacy)** Versione API.
1. Per ciascuna di queste applicazioni mobili, imposta il **Versione API** a **HTTP v1**.
1. Fai clic su **[!UICONTROL Load project json file to extract project details...]** collegamento per caricare direttamente il file di chiave JSON.

   È inoltre possibile immettere manualmente i seguenti dettagli:
   * **[!UICONTROL Project Id]**
   * **[!UICONTROL Private Key]**
   * **[!UICONTROL Client Email]**

   ![](assets/android-http-v1-config.png)

1. Clic **[!UICONTROL Test the connection]** per verificare che la configurazione sia corretta e che il server di marketing abbia accesso a FCM. Tieni presente che per le distribuzioni Mid-Sourcing, il **[!UICONTROL Test connection]** non può verificare se il server ha accesso al servizio Android Firebase Cloud Messaging (FCM).
1. Come opzione, puoi arricchire il contenuto di un messaggio push con **[!UICONTROL Application variables]** se necessario. Questi sono completamente personalizzabili e fanno parte del payload del messaggio inviato al dispositivo mobile.
1. Fai clic su **[!UICONTROL Finish]**, quindi su **[!UICONTROL Save]**.

Di seguito sono riportati i nomi del payload FCM per personalizzare ulteriormente la notifica push. Queste opzioni sono dettagliate [qui](#fcm-apps).

| Tipo di messaggio | Elemento del messaggio configurabile (nome del payload FCM) | Opzioni configurabili (nome payload FCM) |
|:-:|:-:|:-:|
| messaggio dati | N/D | validate_only |
| messaggio di notifica | titolo, corpo, android_channel_id, icona, suono, tag, colore, click_action, immagine, ticker, fisso, visibilità, notification_priority, notification_count <br> | validate_only |


>[!NOTE]
>
>Una volta applicate queste modifiche a tutti i server, tutte le nuove consegne di notifiche push ai dispositivi Android utilizzano l’API HTTP v1. Le consegne push esistenti in un nuovo tentativo, in corso e in uso utilizzano ancora l’API HTTP (legacy).

### Qual è l’impatto sulle app Android? {#fcm-apps}

Non sono richieste modifiche specifiche al codice delle applicazioni Android Mobile e il comportamento di notifica non deve cambiare.

Tuttavia, con HTTP v1, puoi personalizzare ulteriormente la notifica push con **[!UICONTROL HTTPV1 additional options]**.

![](assets/android-push-additional-options.png)

Puoi eseguire le seguenti azioni:

* Utilizza il **[!UICONTROL Ticker]** per impostare il testo del ticker della notifica.
* Utilizza il **[!UICONTROL Image]** per impostare l’URL dell’immagine da visualizzare nella notifica.
* Utilizza il **[!UICONTROL Notification Count]** per impostare il numero di nuove informazioni da visualizzare direttamente sull&#39;icona dell&#39;applicazione.
* Imposta il **[!UICONTROL Sticky]** su false in modo che la notifica venga automaticamente ignorata quando l’utente fa clic su di essa. Se impostato su true, la notifica viene comunque visualizzata anche quando l’utente fa clic su di essa.
* Imposta il **[!UICONTROL Notification Priority]** livello di notifica predefinito, minimo, minimo o massimo.
* Imposta il **[!UICONTROL Visibility]** livello della notifica a pubblico, privato o segreto.

Per ulteriori informazioni su **[!UICONTROL HTTP v1 additional options]** e come compilare questi campi, consulta [Documentazione FCM](https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages#androidnotification){target="_blank"}.

