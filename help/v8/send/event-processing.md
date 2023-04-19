---
title: Raccolta ed elaborazione di eventi
description: Scopri come la messaggistica transazionale di Campaign raccoglie ed elabora gli eventi
feature: Transactional Messaging
role: User
level: Beginner, Intermediate
exl-id: c1deb0a1-aeba-4813-b674-a6a164b98b02
source-git-commit: c044b391c900e8ff82147f2682e2e4f91845780c
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---

# Elaborazione di eventi {#event-processing}

Nel contesto della messaggistica transazionale, un evento viene generato da un sistema di informazioni esterno e inviato ad Adobe Campaign tramite il **[!UICONTROL PushEvent]** e **[!UICONTROL PushEvents]** metodi. Questi metodi sono descritti in [questa sezione](event-description.md).

Questo evento contiene dati collegati all&#39;evento, ad esempio:

* i [type](transactional.md#create-event-types): conferma dell’ordine, creazione dell’account su un sito web, ecc.,
* l&#39;indirizzo e-mail o il numero di telefono,
* qualsiasi altra informazione per arricchire e personalizzare il messaggio transazionale prima della consegna: informazioni di contatto del cliente, lingua del messaggio, formato e-mail, ecc.

Esempio di dati evento:

![](assets/mc-event-request.png)

Per elaborare gli eventi di messaggistica transazionale, i seguenti passaggi vengono applicati alle istanze di esecuzione:

1. [Raccolta di eventi](#event-collection)
1. [Trasferimento di eventi a un modello di messaggio](#routing-towards-a-template)
1. Arricchimento degli eventi con dati di personalizzazione
1. [Esecuzione della consegna](delivery-execution.md)
1. [Riciclo degli eventi](#event-recycling) la cui consegna collegata non è riuscita (tramite un flusso di lavoro Adobe Campaign)

Una volta completati tutti i passaggi, ogni destinatario con targeting riceve un messaggio personalizzato.

## Raccogliere eventi {#event-collection}

Gli eventi generati dal sistema di informazione possono essere raccolti utilizzando due modalità:

* Le chiamate ai metodi SOAP consentono di inviare eventi in push in Adobe Campaign: il metodo PushEvent consente di inviare un evento alla volta, il metodo PushEvents consente di inviare diversi eventi contemporaneamente. [Ulteriori informazioni](event-description.md).

* La creazione di un flusso di lavoro consente di recuperare gli eventi importando i file o tramite un gateway SQL, con [Federated Data Access](../connect/fda.md) modulo .

Una volta raccolti, gli eventi vengono suddivisi per flussi di lavoro tecnici tra code in tempo reale e batch delle istanze di esecuzione, in attesa di essere collegati a un [modello di messaggio](transactional-template.md).

![](assets/mc-event-queues.png)

>[!NOTE]
>
>Nelle istanze di esecuzione, la **[!UICONTROL Real time events]** o **[!UICONTROL Batch events]** le cartelle non devono essere impostate come visualizzazioni, in quanto ciò potrebbe causare problemi di accesso ai diritti. Per ulteriori informazioni sull’impostazione di una cartella come visualizzazione, consulta [questa sezione](../audiences/folders-and-views.md#turn-a-folder-to-a-view).

## Trasferire un evento in un modello {#event-to-template}

Una volta pubblicato il modello di messaggio sulle istanze di esecuzione, vengono generati automaticamente due modelli: da collegare a un evento in tempo reale e da collegare a un evento batch.

La fase di indirizzamento consiste nel collegare un evento al modello di messaggio appropriato, in base a:

* Il tipo di evento specificato nelle proprietà dell&#39;evento stesso:

   ![](assets/event-type-sample.png)

* Il tipo di evento specificato nelle proprietà del modello di messaggio:

   ![](assets/event-type-select.png)

Per impostazione predefinita, il ciclo di produzione si basa sulle seguenti informazioni:

* Il tipo di evento
* Il canale da utilizzare (per impostazione predefinita: e-mail)
* Il modello di consegna più recente, in base alla data di pubblicazione

## Verifica lo stato dell’evento {#event-statuses}

Tutti gli eventi elaborati sono raggruppati in un’unica visualizzazione, nel **Cronologia eventi** o la cartella Explorer. Possono essere suddivisi per tipo di evento o per **status**.

Gli stati possibili sono:

* **In sospeso**

   * Un evento in sospeso può essere un evento appena raccolto e non ancora elaborato. La **[!UICONTROL Number of errors]** mostra il valore 0. Il modello e-mail non è ancora stato collegato.
   * Un evento in sospeso può anche essere un evento elaborato ma la cui conferma è errata. La **[!UICONTROL Number of errors]** mostra un valore diverso da 0. Per sapere quando questo evento verrà elaborato di nuovo, consulta la **[!UICONTROL Process requested on]** colonna.

* **Consegna in sospeso**
L’evento è stato elaborato e il modello di consegna è collegato. L’e-mail è in attesa di consegna e viene applicato il processo di consegna classico . Per ulteriori informazioni, puoi aprire la consegna.
* **Inviato**, **Ignorato** e **Errore di consegna**
Questi stati di consegna vengono recuperati tramite 
**updateEventsStatus** workflow. Per ulteriori informazioni, puoi aprire la consegna pertinente.
* **Evento non coperto**
La fase di indirizzamento della messaggistica transazionale non è riuscita. Ad esempio, Adobe Campaign non ha trovato l’e-mail che funge da modello per l’evento.
* **Evento scaduto**
È stato raggiunto il numero massimo di tentativi di invio. L&#39;evento è considerato nullo.

## Riciclare gli eventi {#event-recycling}

Se la consegna di un messaggio su un canale specifico non riesce, Adobe Campaign può inviare nuovamente il messaggio utilizzando un canale diverso. Ad esempio, se una consegna sul canale SMS non riesce, il messaggio viene inviato nuovamente utilizzando il canale e-mail.

A questo scopo, devi configurare un flusso di lavoro che ricrea tutti gli eventi con il **Errore di consegna** e assegna loro un canale diverso.

>[!CAUTION]
>
>Questo passaggio può essere eseguito solo utilizzando un flusso di lavoro ed è pertanto riservato agli utenti esperti. Per ulteriori informazioni, contatta il tuo responsabile dell&#39;account di Adobe.
