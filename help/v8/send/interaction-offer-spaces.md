---
title: Aree di offerta di interazione campagna
description: Scopri come creare spazi di offerta
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 3%

---

# Creazione di spazi di offerta{#creating-offer-spaces}

Il contenuto del catalogo delle offerte è configurato negli spazi delle offerte. Per impostazione predefinita, il contenuto può includere i campi seguenti: **[!UICONTROL Title]**, **[!UICONTROL Destination URL]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** e **[!UICONTROL Text content]**. La sequenza di campi è configurata nello spazio di offerta.

In qualità di **amministratore tecnico**, puoi creare spazi di offerta nell’ambiente di progettazione. Devi avere accesso alla sottocartella spazio offerta . Una volta creati, questi spazi di offerta vengono automaticamente duplicati nell’ambiente Live durante l’approvazione dell’offerta.

Il rendering HTML viene creato tramite una funzione di rendering. La sequenza dei campi definiti nella funzione di rendering deve essere identica alla sequenza configurata nel contenuto.

![](assets/offer_space_create_009.png)

Per creare un nuovo spazio di offerta, effettua le seguenti operazioni:

1. Nell’elenco degli spazi di offerta, fai clic su **[!UICONTROL New]**.

   ![](assets/offer_space_create_001.png)

1. Seleziona il canale da utilizzare e modifica l’etichetta dello spazio di offerta.

   ![](assets/offer_space_create_002.png)

1. Controlla l&#39;opzione **[!UICONTROL Enable unitary mode]**

1. Vai alla finestra **[!UICONTROL Content field]** e fai clic su **[!UICONTROL Add]**.

   ![](assets/offer_space_create_003.png)

1. Vai al nodo **[!UICONTROL Content]** e seleziona i campi nel seguente ordine: **[!UICONTROL Title]**, quindi **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]**, quindi **[!UICONTROL Destination URL]**.

   ![](assets/offer_space_create_004.png)

1. Seleziona l’opzione **[!UICONTROL Required]** per rendere obbligatorio ogni campo.

   >[!NOTE]
   >
   >Questa opzione viene utilizzata nell’anteprima e rende gli spazi di offerta non validi durante la pubblicazione se nell’offerta manca uno dei campi obbligatori. Tuttavia, se un’offerta è già attiva in uno spazio di offerta, questi criteri non vengono presi in considerazione.

   ![](assets/offer_space_create_005.png)

1. Fai clic su **[!UICONTROL Edit functions]** per creare una funzione di rendering.

   Queste funzioni vengono utilizzate per generare rappresentazioni di offerte su uno spazio di offerta. Esistono diversi formati possibili: HTML o testo.

   **Nota** : il formato XML è limitato alle interazioni in entrata non disponibili in questa versione del prodotto. [Ulteriori informazioni](../start/capability-matrix.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. Vai alla scheda **[!UICONTROL HTML rendering]** e seleziona **[!UICONTROL Overload the HTML rendering function]**.
1. Inserisci la funzione di rendering.

   ![](assets/offer_space_create_007.png)

## Stato delle proposte di offerta {#offer-proposition-statuses}

Lo stato della proposta di offerta varia a seconda delle interazioni con la popolazione target. Il modulo di interazione della campagna viene fornito con un set di valori che possono essere applicati alla proposta di offerta per tutto il suo ciclo di vita. Devi configurare la piattaforma in modo che lo stato cambi quando la proposta di offerta viene creata e accettata.

>[!NOTE]
>
>L&#39;aggiornamento dello stato è un processo **asincrono**. Viene eseguito dal flusso di lavoro di tracciamento che viene attivato ogni ora.

### Elenco dello stato dell’offerta {#status-list}

Gli stati di offerta disponibili sono:

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

Questi valori non vengono applicati per impostazione predefinita: devono essere configurate.

>[!NOTE]
>
>Lo stato di una proposta di offerta viene automaticamente modificato in &quot;Presentato&quot; se l’offerta è collegata a una consegna con lo stato &quot;Inviato&quot;.

### Stato dell’offerta al momento della creazione della proposta {#configuring-the-status-when-the-proposition-is-created}

Quando una proposta di offerta viene **creata**, il suo stato viene aggiornato.

Nell’ambiente **[!UICONTROL Design]**, per ogni spazio di offerta, configura lo stato da applicare al momento della creazione di una proposta, in base alle informazioni da visualizzare nei rapporti di offerta.

Per farlo, segui la procedura indicata di seguito:

1. Passa alla scheda **[!UICONTROL Storage]** dello spazio desiderato.
1. Selezionare lo stato da applicare alla proposta al momento della creazione.

   ![](assets/offer_update_status_001.png)

### Stato dell’offerta quando la proposta viene accettata {#configuring-the-status-when-the-proposition-is-accepted}

Una volta che una proposta di offerta è stata **accettata**, utilizza uno dei valori forniti per impostazione predefinita per configurare il nuovo stato della proposta. L’aggiornamento viene applicato quando un destinatario fa clic su un collegamento nell’offerta.

Per farlo, segui la procedura indicata di seguito:

1. Passa alla scheda **[!UICONTROL Storage]** dello spazio desiderato.
1. Selezionare lo stato da applicare alla proposta quando viene accettata.

   ![](assets/offer_update_status_002.png)

<!--
**Inbound interaction**

The **[!UICONTROL Storage]** tab lets you define statuses for **proposed** and **accepted** offer propositions only. For inbound interaction, the status of offer propositions should be specified directly in the URL for calling the offer engine, rather than through the interface. This way, you will be able to specify which status to apply in other cases, for example if an offer proposition is rejected.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

For instance, the proposition (identifier **40004**) that matches the **Home insurance** offer displayed on the **Neobank** site contains the following URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

As soon as a visitor clicks the offer, and therefore the URL, the **[!UICONTROL Accepted]** status (value **3**) is applied to the proposition and the visitor is redirected to a new page of the **Neobank** site to take out the insurance contract.

>[!NOTE]
>
>If you want to specify another status in the url (for example if an offer proposition is rejected), use the value corresponding to the desired status. Example: **[!UICONTROL Rejected]** = "5", **[!UICONTROL Presented]** = "1" and so on.
>
>Statuses and their values can be retrieved in the **[!UICONTROL Offer propositions (nms)]** data schema. For more on this, refer to [this page](../../configuration/using/data-schemas.md).

**Outbound interaction**
-->

Puoi applicare automaticamente lo stato **[!UICONTROL Interested]** a una proposta di offerta quando la consegna contiene un collegamento. Aggiungi semplicemente il valore **_urlType=&quot;11&quot;** al collegamento:

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## Anteprima offerta per spazio {#offer-preview-per-space}

Nella scheda **[!UICONTROL Preview]** puoi visualizzare le offerte per le quali il destinatario è idoneo tramite un metodo scelto. Nell’esempio seguente, il destinatario può ricevere tre proposte di offerta per posta.

![](assets/offer_space_overview_002.png)

Se un destinatario non è idoneo per alcuna offerta, questa viene visualizzata nell’anteprima.

![](assets/offer_space_overview_001.png)

<!--
The preview can ignore contexts when they are restricted to a space. This is the case when the interaction schema has been extended to add fields referenced in a space using an inbound channel (for more on this, refer to Extension example.
-->
