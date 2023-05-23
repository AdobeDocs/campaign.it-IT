---
title: Spazi dell’offerta di interazione campagna
description: Scopri come creare spazi dell’offerta
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '838'
ht-degree: 3%

---

# Creare spazi dell’offerta{#creating-offer-spaces}

Il contenuto del catalogo delle offerte è configurato negli spazi dell’offerta. Per impostazione predefinita, il contenuto può includere i campi seguenti: **[!UICONTROL Title]**, **[!UICONTROL Destination URL]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** e **[!UICONTROL Text content]**. La sequenza di campi viene configurata nello spazio dell’offerta.

As a **amministratore tecnico**, puoi creare spazi dell’offerta nell’ambiente di progettazione. Devi avere accesso alla sottocartella dello spazio delle offerte. Una volta creati, questi spazi di offerta vengono duplicati automaticamente nell’ambiente Live durante l’approvazione dell’offerta.

Il rendering HTML viene creato tramite una funzione di rendering. La sequenza dei campi definiti nella funzione di rendering deve essere identica alla sequenza configurata nel contenuto.

![](assets/offer_space_create_009.png)

Per creare un nuovo spazio dell’offerta, effettua le seguenti operazioni:

1. Nell’elenco degli spazi dell’offerta, fai clic su **[!UICONTROL New]**.

   ![](assets/offer_space_create_001.png)

1. Seleziona il canale da utilizzare e cambia l’etichetta dello spazio dell’offerta.

   ![](assets/offer_space_create_002.png)

1. Controlla la **[!UICONTROL Enable unitary mode]** opzione

1. Vai a **[!UICONTROL Content field]** e fai clic su **[!UICONTROL Add]**.

   ![](assets/offer_space_create_003.png)

1. Vai a **[!UICONTROL Content]** e selezionare i campi nell&#39;ordine seguente: **[!UICONTROL Title]**, quindi **[!UICONTROL Image URL]**, quindi **[!UICONTROL HTML content]**, quindi **[!UICONTROL Destination URL]**.

   ![](assets/offer_space_create_004.png)

1. Controlla la **[!UICONTROL Required]** opzione per rendere obbligatorio ogni campo.

   >[!NOTE]
   >
   >Questa opzione viene utilizzata nell’anteprima e rende non validi gli spazi dell’offerta durante la pubblicazione se manca uno dei campi obbligatori nell’offerta. Tuttavia, se un’offerta è già live in uno spazio dell’offerta, questi criteri non vengono presi in considerazione.

   ![](assets/offer_space_create_005.png)

1. Clic **[!UICONTROL Edit functions]** per creare una funzione di rendering.

   Queste funzioni vengono utilizzate per generare rappresentazioni di offerta in uno spazio dell’offerta. Esistono diversi formati possibili: HTML o testo.

   **Nota** : il formato XML è limitato alle interazioni in entrata non disponibili in questa versione del prodotto. [Ulteriori informazioni](../start/v7-to-v8.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. Vai a **[!UICONTROL HTML rendering]** e seleziona **[!UICONTROL Overload the HTML rendering function]**.
1. Inserire la funzione di rendering.

   ![](assets/offer_space_create_007.png)

## Stati delle proposte di offerta {#offer-proposition-statuses}

Lo stato della proposta di offerta varia a seconda delle interazioni con la popolazione target. Il modulo di interazione della campagna è dotato di un set di valori che possono essere applicati alla proposta di offerta durante il suo ciclo di vita. Devi configurare la piattaforma in modo che lo stato cambi quando la proposta di offerta viene creata e accettata.

>[!NOTE]
>
>L&#39;aggiornamento dello stato è un **asincrono** processo. Viene eseguito dal flusso di lavoro di tracciamento che viene attivato ogni ora.

### Elenco stato offerta {#status-list}

Gli stati di offerta disponibili sono:

* **[!UICONTROL Accepted]**
* **[!UICONTROL Scheduled]**
* **[!UICONTROL Generated]**
* **[!UICONTROL Interested]**
* **[!UICONTROL Presented]**
* **[!UICONTROL Rejected]**

Questi valori non vengono applicati per impostazione predefinita: devono essere configurati.

>[!NOTE]
>
>Lo stato di una proposta di offerta verrà automaticamente modificato in &quot;Presentata&quot; se l’offerta è collegata a una consegna con lo stato &quot;Inviata&quot;.

### Stato dell’offerta al momento della creazione della proposta {#configuring-the-status-when-the-proposition-is-created}

Quando una proposta di offerta è **creato**, il suo stato viene aggiornato.

In **[!UICONTROL Design]** in ogni spazio dell’offerta, configura lo stato da applicare al momento della creazione di una proposta, in base alle informazioni da visualizzare nei rapporti dell’offerta.

A tale scopo, segui la procedura indicata di seguito:

1. Vai a **[!UICONTROL Storage]** dello spazio desiderato.
1. Seleziona lo stato da applicare alla proposta al momento della sua creazione.

   ![](assets/offer_update_status_001.png)

### Stato dell’offerta quando la proposta viene accettata {#configuring-the-status-when-the-proposition-is-accepted}

Una volta proposta un’offerta **accettato**, utilizza uno dei valori forniti per impostazione predefinita per configurare il nuovo stato della proposta. L’aggiornamento viene applicato quando un destinatario fa clic su un collegamento nell’offerta.

A tale scopo, segui la procedura indicata di seguito:

1. Vai a **[!UICONTROL Storage]** dello spazio desiderato.
1. Seleziona lo stato da applicare alla proposta quando viene accettata.

   ![](assets/offer_update_status_002.png)


**Interazione in entrata**

Il **[!UICONTROL Storage]** consente di definire gli stati per **proposto** e **accettato** solo proposte di offerta. Per l’interazione in entrata, lo stato delle proposte di offerta deve essere specificato direttamente nell’URL per la chiamata al motore di offerta, anziché tramite l’interfaccia. In questo modo, potrai specificare lo stato da applicare in altri casi, ad esempio se una proposta di offerta viene rifiutata.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

Ad esempio, la proposta (identificatore) **40004**) che corrisponde al **Assicurazione sulla casa** offerta visualizzata sul **Neobank** Il sito contiene il seguente URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

Non appena un visitatore fa clic sull’offerta, e quindi sull’URL, **[!UICONTROL Accepted]** stato (valore) **3**) viene applicata alla proposta e il visitatore viene reindirizzato a una nuova pagina della **Neobank** per stipulare il contratto di assicurazione.

>[!NOTE]
>
>Se desideri specificare un altro stato nell’URL (ad esempio se una proposta di offerta viene rifiutata), utilizza il valore corrispondente allo stato desiderato. Esempio: **[!UICONTROL Rejected]** = &quot;5&quot; **[!UICONTROL Presented]** = &quot;1&quot; ecc.
>
>Gli stati e i relativi valori possono essere recuperati in **[!UICONTROL Offer propositions (nms)]** schema dati. Per ulteriori informazioni, consulta [questa pagina](../dev/create-schema.md).

**Interazione in uscita**

Puoi applicare automaticamente il **[!UICONTROL Interested]** lo stato di una proposta di offerta quando la consegna contiene un collegamento. Aggiungi semplicemente il **_urlType=&quot;11&quot;** valore per il collegamento:

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## Anteprima offerta per spazio {#offer-preview-per-space}

In **[!UICONTROL Preview]** , è possibile visualizzare le offerte per le quali il destinatario è idoneo tramite un metodo scelto. Nell’esempio che segue, il destinatario può presentare tre proposte di offerta per posta.

![](assets/offer_space_overview_002.png)

Se un destinatario non è idoneo per nessuna offerta, ciò viene mostrato nell’anteprima.

![](assets/offer_space_overview_001.png)


L’anteprima può ignorare i contesti quando sono limitati a uno spazio. Ciò si verifica quando lo schema di interazione è stato esteso per aggiungere campi a cui si fa riferimento in uno spazio utilizzando un canale in entrata.

![](../assets/do-not-localize/book.png)  Per ulteriori informazioni, consulta questo esempio in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/advanced-parameters/extension-example.html){target="_blank"}.