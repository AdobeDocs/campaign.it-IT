---
product: campaign
title: Prossime modifiche del canale di notifica push
description: Prossime modifiche del canale di notifica push
feature: Push
role: Admin
level: Experienced
badge-v7: label="v7" type="Informative" tooltip="Applicabile anche a Campaign Classic v7"
badge-v8: label="v8" type="Positive" tooltip="Applicabile a Campaign v8"
exl-id: 45ac6f8f-eb2a-4599-a930-1c1fcaa3095b
source-git-commit: c81744fdf4a4fc47820c077f69288a0ea66fa5e4
workflow-type: tm+mt
source-wordcount: '1352'
ht-degree: 1%

---

# Modifiche al canale di notifica push {#push-upgrade}

Puoi utilizzare Campaign per inviare notifiche push su dispositivi iOS e Android. Per eseguire questa operazione, Campaign si basa sui servizi di abbonamento alle app mobili.

Alcune modifiche importanti al servizio Android Firebase Cloud Messaging (FCM) sono state rilasciate nel 2024 e potrebbero influire sull’implementazione di Adobe Campaign. Per supportare questa modifica, potrebbe essere necessario aggiornare la configurazione dei servizi di abbonamento per i messaggi push Android.

Inoltre, Adobe consiglia vivamente di passare alla connessione basata su token ai numeri APN anziché a una connessione basata su certificati, che è più sicura e scalabile.

## Servizio Google Android Firebase Cloud Messaging (FCM) {#fcm-push-upgrade}

### Cosa è cambiato? {#fcm-changes}

Come parte del continuo sforzo di Google per migliorare i suoi servizi, le API FCM legacy saranno interrotte il **20 giugno 2024**. Ulteriori informazioni sul protocollo HTTP Firebase Cloud Messaging in [Documentazione di Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Adobe Campaign Classic v7 e Adobe Campaign v8 supportano già le API più recenti per l’invio di messaggi di notifica push. Tuttavia, alcune implementazioni precedenti si basano ancora sulle API legacy. Queste implementazioni devono essere aggiornate.

### Sei interessato? {#fcm-impact}

Se l’implementazione corrente supporta i servizi di abbonamento che si connettono a FCM utilizzando le API legacy, sei interessato. Per evitare distrazioni di servizio, è necessario eseguire la migrazione alle API più recenti. In tal caso, i team di Adobi ti contatteranno.

Per verificare se sei interessato, puoi filtrare il **Servizi e abbonamenti** secondo il filtro seguente:

![](assets/filter-services-fcm.png)


* Se uno dei servizi di notifica push attivi utilizza **HTTP (legacy)** API, la configurazione sarà direttamente interessata da questa modifica. È necessario rivedere le configurazioni correnti e migrare alle API più recenti come descritto di seguito.

* Se la configurazione utilizza esclusivamente **HTTP v1** API per notifiche push Android, sei già conforme e non saranno necessarie ulteriori azioni da parte tua.

### Come effettuare la migrazione? {#fcm-migration-procedure}

#### Prerequisiti {#fcm-migration-prerequisites}

* Per Campaign Classic v7, il supporto di HTTP v1 è stato aggiunto nella versione 20.3.1. Se l’ambiente è in esecuzione su una versione precedente, un prerequisito per la migrazione a HTTP v1 è aggiornare l’ambiente a [build Campaign Classic più recente](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Per Campaign v8, HTTP v1 è supportato da tutte le versioni e non è necessario alcun aggiornamento.

* Il file JSON dell&#39;account del servizio Admin SDK per Android Firebase è necessario per spostare l&#39;app mobile su HTTP v1. Scopri come ottenere questo file in [Documentazione di Google Firebase](https://firebase.google.com/docs/admin/setup#initialize-sdk){target="_blank"}.

* Per le distribuzioni ibride, in hosting e Managed Services, oltre alla procedura di migrazione seguente, contatta l’Adobe per aggiornare il server di esecuzione in tempo reale (RT). Il server Mid-Sourcing non è interessato.

* In qualità di utente on-premise di Campaign Classic v7, devi aggiornare sia il server di esecuzione Marketing che il server di esecuzione in tempo reale. Il server Mid-Sourcing non è interessato.

#### Procedura di migrazione {#fcm-migration-steps}

Per migrare l’ambiente a HTTP v1, effettua le seguenti operazioni:

1. Sfoglia l’elenco di **Servizi e abbonamenti**.
1. Elencare tutte le applicazioni mobili utilizzando **HTTP (legacy)** Versione API.
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




## Servizio Apple iOS Push Notification (APNs) {#apns-push-upgrade}

### Cosa è cambiato? {#ios-changes}

Come consigliato da Apple, è necessario proteggere le comunicazioni con il servizio APN (Apple Push Notification Service) utilizzando token di autenticazione senza stato.

L’autenticazione basata su token offre un modo senza stato di comunicare con i numeri APN. La comunicazione senza stato è più veloce della comunicazione basata su certificato perché non richiede che APN ricerchi il certificato o altre informazioni correlate al server provider. L’utilizzo dell’autenticazione basata su token presenta altri vantaggi:

* È possibile utilizzare lo stesso token da più server provider.

* Puoi utilizzare un token per distribuire le notifiche per tutte le app della tua azienda.

Ulteriori informazioni sulle connessioni basate su token ai numeri APN in [Documentazione per gli sviluppatori di Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

Adobe Campaign Classic v7 e Adobe Campaign v8 supportano connessioni sia basate su token che basate su certificati. Se l’implementazione si basa su una connessione basata su certificato, Adobe consiglia vivamente di aggiornarla a una connessione basata su token.

### Sei interessato? {#ios-impact}

L’implementazione corrente è interessata se si basa su richieste basate su certificati per la connessione ad APN. Si consiglia di eseguire la migrazione a una connessione basata su token.

Per verificare se sei interessato, puoi filtrare il **Servizi e abbonamenti** secondo il filtro seguente:

![](assets/filter-services-ios.png)


* Se uno dei servizi di notifica push attivi utilizza **Autenticazione basata su certificato** , le implementazioni correnti devono essere riviste e spostate in una **Autenticazione basata su token** come descritto di seguito.

* Se la configurazione utilizza esclusivamente **Autenticazione basata su token** per le notifiche push di iOS, l’implementazione è già aggiornata e non sarà necessaria alcuna ulteriore azione da parte tua.

### Come effettuare la migrazione? {#ios-migration-procedure}

#### Prerequisiti {#ios-migration-prerequisites}

* Per Campaign Classic v7, il supporto di **Autenticazione basata su token** è stata aggiunta nella versione 20.2. Se l’ambiente è in esecuzione su una versione precedente, un prerequisito per questa modifica è aggiornare l’ambiente a [build Campaign Classic più recente](https://experienceleague.adobe.com/docs/campaign-classic/using/release-notes/latest-release.html){target="_blank"}. Per Campaign v8, **Autenticazione basata su token** La modalità è supportata da tutte le versioni e non è necessario alcun aggiornamento.

* Per generare i token utilizzati dal server è necessaria una chiave di firma del token di autenticazione APNs. Richiedi questa chiave al tuo account sviluppatore Apple, come spiegato in [Documentazione per gli sviluppatori di Apple](https://developer.apple.com/documentation/usernotifications/establishing-a-token-based-connection-to-apns){target="_blank"}.

* Per le distribuzioni ibride, in hosting e Managed Services, oltre alla procedura di migrazione seguente, contatta l’Adobe per aggiornare il server di esecuzione in tempo reale (RT). Il server Mid-Sourcing non è interessato.

* In qualità di utente on-premise di Campaign Classic v7, devi aggiornare sia il server di esecuzione Marketing che il server di esecuzione in tempo reale. Il server Mid-Sourcing non è interessato.

#### Procedura di migrazione {#ios-migration-steps}

Per migrare le app mobili iOS alla modalità di autenticazione basata su token, effettua le seguenti operazioni:

1. Sfoglia l’elenco di **Servizi e abbonamenti**.
1. Elencare tutte le applicazioni mobili utilizzando **Autenticazione basata su certificato** modalità.
1. Modifica ciascuna di queste applicazioni mobili e passa alla **Certificato/chiave privata** scheda.
1. Dalla sezione **Modalità di autenticazione** a discesa, seleziona **Autenticazione basata su token**.
1. Inserisci le impostazioni di connessione APNs **[!UICONTROL Key Id]**, **[!UICONTROL Team Id]** e **[!UICONTROL Bundle Id]** quindi seleziona il certificato p8 facendo clic su **[!UICONTROL Enter the private key...]**.

   ![](assets/token-based-certif.png)

1. Clic **[!UICONTROL Test the connection]** per verificare che la configurazione sia corretta e che il server abbia accesso ai numeri APN. Tieni presente che per le distribuzioni Mid-Sourcing, il **[!UICONTROL Test connection]** non può verificare se il server ha accesso ai numeri APN.
1. Clic **[!UICONTROL Next]** per iniziare a configurare l’applicazione di produzione e seguire gli stessi passaggi descritti in precedenza.
1. Fai clic su **[!UICONTROL Finish]**, quindi su **[!UICONTROL Save]**.

L’applicazione iOS viene ora spostata nella modalità di autenticazione basata su token.
