---
title: Messaggistica transazionale di Campaign
description: Introduzione alla messaggistica transazionale
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: 06fdb279-3776-433f-8d27-33d016473dee
TQID: https://experienceleague.adobe.com/BJSTLxMSilUemXKftd0YVYd5-6oBumTvihQWpeFWEJU
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 0%

---

# Introduzione alla messaggistica transazionale{#send-transactional-messages}

La messaggistica transazionale (Message Center) è un modulo di Campaign progettato per la gestione dei messaggi di attivazione. Queste notifiche sono generate da eventi attivati dai sistemi informativi e possono essere: fattura, conferma dell’ordine, conferma della spedizione, modifica della password, notifica di indisponibilità del prodotto, estratto conto, creazione di account sul sito web, ecc.

>[!NOTE]
>
>In qualità di utente di Managed Cloud Services, [contatta Adobe](../start/campaign-faq.md#support){target="_blank"} per configurare la messaggistica transazionale di Campaign nel tuo ambiente.

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
1. [Pubblica il modello di messaggio](transactional-template.md#publish-message-template).

Dopo aver progettato e pubblicato il modello di messaggio transazionale, se viene attivato un evento corrispondente, i dati rilevanti vengono inviati a Campaign tramite i [metodi SOAP](../send/event-description.md) PushEvent e PushEvents e la consegna viene inviata ai destinatari desiderati.

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
>Ulteriori informazioni sulle [enumerazioni](../config/enumerations.md).

Per il passaggio successivo, scopri come [creare e pubblicare il modello per la messaggistica transazionale](transactional-template.md).
