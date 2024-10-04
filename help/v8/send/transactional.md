---
title: Messaggistica transazionale di Campaign
description: Introduzione alla messaggistica transazionale
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
source-git-commit: 253f3be945cbfa304fa7342c68f0c73b079e2870
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# Introduzione alla messaggistica transazionale{#send-transactional-messages}

La messaggistica transazionale (Message Center) è un modulo di Campaign progettato per la gestione dei messaggi di attivazione. Queste notifiche sono generate da eventi attivati dai sistemi informativi e possono essere: fattura, conferma dell’ordine, conferma della spedizione, modifica della password, notifica di indisponibilità del prodotto, estratto conto, creazione di account sul sito web, ecc.

>[!NOTE]
>
>In qualità di utente di Cloud Service gestiti, [contatta l&#39;Adobe](../start/campaign-faq.md#support){target="_blank"} per configurare la messaggistica transazionale di Campaign nel tuo ambiente.

I messaggi transazionali vengono utilizzati per inviare:

* notifiche, ad esempio conferme d’ordine o reimpostazioni della password
* una risposta individuale in tempo reale a un’azione del cliente
* contenuti non promozionali

Le impostazioni dei messaggi transazionali sono descritte in dettaglio in [questa sezione](../config/transactional-msg-settings.md).

Scopri l&#39;architettura della messaggistica transazionale in [questa pagina](../architecture/architecture.md#transac-msg-archi).

## Principio operativo della messaggistica transazionale {#transactional-messaging-operating-principle}

Il modulo di messaggistica transazionale di Adobe Campaign si integra in un sistema di informazioni che restituisce eventi da trasformare in messaggi transazionali personalizzati. Questi messaggi possono essere inviati singolarmente o in batch tramite e-mail, SMS o notifiche push.

Ad esempio, immagina di essere un’azienda con un sito web in cui i clienti possono acquistare prodotti.

Adobe Campaign consente di inviare un’e-mail di notifica ai clienti che hanno aggiunto prodotti al carrello. Quando uno di loro lascia il sito web senza procedere con gli acquisti (evento esterno che attiva un evento Campaign), riceve automaticamente un’e-mail di abbandono del carrello (consegna di messaggi transazionali).

Di seguito sono illustrate le fasi principali per l’attuazione di questa procedura:

1. [Crea un tipo di evento](#create-event-types).
1. [Creare e progettare il modello di messaggio](transactional-template.md#create-message-template). Collega un evento al messaggio durante questo passaggio.
1. [Verifica il messaggio](transactional-template.md#test-message-template).
1. [Publish il modello di messaggio](transactional-template.md#publish-message-template).

Dopo aver progettato e pubblicato il modello di messaggio transazionale, se viene attivato un evento corrispondente, i dati rilevanti vengono inviati a Campaign tramite i metodi [SOAP ](../send/event-description.md) PushEvent e PushEvents e la consegna viene inviata ai destinatari desiderati.

## Creare tipi di evento {#create-event-types}

Per assicurarsi che ogni evento possa essere modificato in un messaggio personalizzato, devi innanzitutto creare **tipi di evento**.

Quando [si crea un modello di messaggio](#create-message-template), verrà selezionato il tipo di evento corrispondente al messaggio che si desidera inviare.

>[!CAUTION]
>
>È necessario creare tipi di evento prima di poterli utilizzare nei modelli di messaggio.

Per creare tipi di evento che verranno elaborati da Adobe Campaign, segui questi passaggi:

1. Individua la cartella **[!UICONTROL Administration > Platform > Enumerations]** di Campaign Explorer.
1. Selezionare l&#39;enumerazione **[!UICONTROL Event type]** dall&#39;elenco.
1. Fare clic su **[!UICONTROL Add]** per creare un valore di enumerazione. Può trattarsi di una conferma d’ordine, di una modifica della password, di una modifica della consegna dell’ordine, ecc.

   ![](assets/messagecenter_eventtype_enum_001.png)

   >[!CAUTION]
   >
   >Ogni tipo di evento deve corrispondere a un valore nell&#39;enumerazione **[!UICONTROL Event type]**.

1. Una volta creati i valori dell’elenco dettagliati, disconnettiti e accedi di nuovo all’istanza per rendere effettiva la creazione.

>[!NOTE]
>
>Ulteriori informazioni sulle enumerazioni in [questa pagina](../../v8/config/ui-settings.md#enumerations).

Per il passaggio successivo, scopri come [creare e pubblicare il modello per la messaggistica transazionale](transactional-template.md).
