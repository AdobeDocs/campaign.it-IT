---
product: campaign
title: Modifiche imminenti del canale di notifica push
description: Modifiche imminenti del canale di notifica push
hide: true
hidefromtoc: true
source-git-commit: 11330ed8e79ec256b158747914f178b8b6857a33
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 1%

---

# Modifiche imminenti del canale di notifica push {#push-upgrade}

Questa pagina descrive le prossime modifiche al canale di notifica push tramite Firebase Cloud Messaging in Adobe Campaign Classic.

Dove sono le modifiche importanti al servizio Firebase Cloud Messaging (FCM) che possono influire sull’implementazione di Adobe Campaign Classic.

Nell’ambito del continuo impegno di Google per migliorare i suoi servizi, le API FCM legacy cesseranno a giugno 2024 (protocollo HTTP Firebase Cloud Messaging: https://firebase.google.com/docs/cloud-messaging/http-server-ref)

Queste API sono attualmente integrate con Adobe Campaign Classic per l’invio di messaggi di notifica push. Sappiamo che molti dei nostri clienti, come te, si affidano a questi servizi per le tue campagne di marketing e le tue esigenze di comunicazione, in particolare per i dispositivi Android.

## Che Impatto Ha Su Di Lei?

* **Utenti API HTTP (legacy)**: se una delle campagne di notifica push attive utilizza l’API HTTP (legacy), la configurazione sarà direttamente interessata da questa modifica. Consigliamo vivamente di rivedere le configurazioni correnti e prepararsi per la migrazione alle API più recenti.

* **Buone notizie per gli utenti API di HTTP v1**: se la configurazione utilizza esclusivamente l’API HTTP v1 per le notifiche push Android, significa che la conformità è già garantita e che non sarà necessaria alcuna ulteriore azione da parte tua.

## Cosa Stiamo Facendo?

* **Piano di transizione**: il nostro team sta lavorando attivamente allo sviluppo di un piano di transizione completo. In questo modo, quando necessario, potrai aggiornare l’implementazione alle API FCM più recenti già disponibili nelle versioni recenti di Adobe Campaign, con il minimo impatto sulle campagne.

* **Istruzioni dettagliate**: forniremo una guida dettagliata e altre risorse per facilitare un processo di transizione senza problemi.

* **Supporto**: il nostro team di assistenza clienti sarà a tua disposizione per assisterti durante questa transizione. Possiamo anche ospitare webinar e sessioni di abilitazione per coprire gli aspetti tecnici e le best practice per la transizione.

## Che Impatto Ha Su Di Lei?

* **Resta informato**: controlla la tua casella in entrata per ricevere ulteriori comunicazioni, compreso il piano di transizione dettagliato.

* **Verifica configurazione corrente**: prendi questo tempo per rivedere la configurazione e la personalizzazione correnti in Adobe Campaign Classic in modo da essere preparato a apportare eventuali modifiche necessarie, se necessario.

* **Contattaci**: in caso di dubbi o domande immediate, non esitare a contattare il nostro team di supporto.

## Passaggi di implementazione

Nelle prossime settimane, condivideremo ulteriori dettagli sul piano di transizione per le API FCM legacy, incluse tempistiche e azioni. Il nostro obiettivo principale è quello di rendere questa transizione il più semplice possibile per te e il tuo team.

Apprezziamo il vostro business e vi ringraziamo per la vostra comprensione mentre ci adattiamo a questi cambiamenti. Il tuo successo è la nostra priorità principale e ci impegniamo a supportarti in ogni fase del processo.

Per anticipare la modifica, ecco i passaggi generali necessari per migrare la configurazione push dall’API HTTP (Legacy) all’API FCM HTTPv1.

### Aggiornamento della build

* Campaign Classic: il supporto di HTTPv1 è stato aggiunto nella versione AC7 20.3.1. Se utilizzi una versione precedente, devi prima eseguire l’aggiornamento alla build Campaign Classic più recente.

* Campaign v8: HTTPv1 è supportato da tutte le versioni di Campaign v8. Non è necessario alcun aggiornamento.

### Server di marketing

Le modifiche alla configurazione possono essere eseguite dal cliente/partner.

1. Innanzitutto, devi estrarre il file JSON. Per spostare l’app mobile su HTTPv1 è necessario il file JSON dell’account del servizio Firebase Admin SDK. Fai riferimento a questo [pagina](https://firebase.google.com/docs/admin/setup#initialize-sdk).

1. Passa all’elenco di **Servizi e abbonamenti**.

1. Individua tutte le app mobili utilizzando la versione API HTTP (legacy).

1. Per ciascuna di queste applicazioni mobili, imposta il **Versione API** a HTTPv1 e seguire le istruzioni di configurazione descritte nella [documentazione](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/sending-push-notifications/configure-the-mobile-app/configuring-the-mobile-application-android.html).

>[!NOTE]
>
>Il passaggio all’API HTTPv1 verrà preso in considerazione per le nuove consegne. Le consegne in un nuovo tentativo, in corso e in uso continueranno a utilizzare l’API HTTP (legacy).

### Server mid-sourcing

Non sono richieste modifiche.

### Server di esecuzione in tempo reale

A tale scopo, contatta il supporto Adobe Campaign. La procedura di migrazione è la stessa del server di marketing.

### Sistema operativo Android e applicazione mobile Android

Non sono richieste modifiche specifiche al codice delle applicazioni Android Mobile e il comportamento di notifica non deve cambiare.

Tuttavia, HTTPv1 sta introducendo tre nuovi elementi di payload:

| Nome | Valore predefinito |
|---|---|
| appiccicoso | False |
| priorità | Predefinito |
| visibilità | False |
| appiccicoso | Privato |
