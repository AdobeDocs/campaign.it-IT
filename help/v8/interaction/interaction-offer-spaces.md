---
title: Spazi dell’offerta di interazione campagna
description: Scopri come creare spazi dell’offerta
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: c116d86a-d3e2-47e3-a641-e2d7c8cc575c
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 1%

---

# Creare spazi dell’offerta{#creating-offer-spaces}

Il contenuto del catalogo delle offerte è configurato negli spazi dell’offerta. Per impostazione predefinita, il contenuto può includere i campi seguenti: **[!UICONTROL Title]**, **[!UICONTROL Destination URL]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]** e **[!UICONTROL Text content]**. La sequenza di campi viene configurata nello spazio dell’offerta.

In qualità di **amministratore tecnico**, puoi creare spazi dell&#39;offerta nell&#39;ambiente di progettazione. Devi avere accesso alla sottocartella dello spazio delle offerte. Una volta creati, questi spazi di offerta vengono duplicati automaticamente nell’ambiente Live durante l’approvazione dell’offerta.

Il rendering HTML viene creato tramite una funzione di rendering. La sequenza dei campi definiti nella funzione di rendering deve essere identica alla sequenza configurata nel contenuto.

![](assets/offer_space_create_009.png)

Per creare un nuovo spazio dell’offerta, effettua le seguenti operazioni:

1. Nell&#39;elenco degli spazi dell&#39;offerta fare clic su **[!UICONTROL New]**.

   ![](assets/offer_space_create_001.png)

1. Seleziona il canale da utilizzare e cambia l’etichetta dello spazio dell’offerta.

   ![](assets/offer_space_create_002.png)

1. Seleziona l&#39;opzione **[!UICONTROL Enable unitary mode]**

1. Passare alla finestra **[!UICONTROL Content field]** e fare clic su **[!UICONTROL Add]**.

   ![](assets/offer_space_create_003.png)

1. Andare al nodo **[!UICONTROL Content]** e selezionare i campi nell&#39;ordine seguente: **[!UICONTROL Title]**, **[!UICONTROL Image URL]**, **[!UICONTROL HTML content]**, quindi **[!UICONTROL Destination URL]**.

   ![](assets/offer_space_create_004.png)

1. Selezionare l&#39;opzione **[!UICONTROL Required]** per rendere obbligatorio ogni campo.

   >[!NOTE]
   >
   >Questa opzione viene utilizzata nell’anteprima e rende non validi gli spazi dell’offerta durante la pubblicazione se manca uno dei campi obbligatori nell’offerta. Tuttavia, se un’offerta è già live in uno spazio dell’offerta, questi criteri non vengono presi in considerazione.

   ![](assets/offer_space_create_005.png)

1. Fare clic su **[!UICONTROL Edit functions]** per creare una funzione di rendering.

   Queste funzioni vengono utilizzate per generare rappresentazioni di offerta in uno spazio dell’offerta. Esistono diversi formati possibili: HTML o testo.

   **Nota** - Il formato XML è limitato alle interazioni in entrata non disponibili in questa versione del prodotto. [Ulteriori informazioni](../start/v7-to-v8.md#gs-unavailable-features)

   ![](assets/offer_space_create_006.png)_

1. Passare alla scheda **[!UICONTROL HTML rendering]** e selezionare **[!UICONTROL Overload the HTML rendering function]**.
1. Inserire la funzione di rendering.

   ![](assets/offer_space_create_007.png)

## Stati delle proposte di offerta {#offer-proposition-statuses}

Lo stato della proposta di offerta varia a seconda delle interazioni con la popolazione target. Il modulo di interazione della campagna è dotato di un set di valori che possono essere applicati alla proposta di offerta durante il suo ciclo di vita. Devi configurare la piattaforma in modo che lo stato cambi quando la proposta di offerta viene creata e accettata.

>[!NOTE]
>
>L&#39;aggiornamento dello stato è un processo **asincrono**. Viene eseguito dal flusso di lavoro di tracciamento che viene attivato ogni ora.

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

Quando una proposta di offerta viene **creata**, il relativo stato viene aggiornato.

Nell&#39;ambiente **[!UICONTROL Design]**, per ogni spazio delle offerte, configura lo stato da applicare quando viene creata una proposta, a seconda delle informazioni che desideri visualizzare nei rapporti delle offerte.

A questo scopo, segui la procedura indicata di seguito:

1. Passare alla scheda **[!UICONTROL Storage]** dello spazio desiderato.
1. Seleziona lo stato da applicare alla proposta al momento della sua creazione.

   ![](assets/offer_update_status_001.png)

### Stato dell’offerta quando la proposta viene accettata {#configuring-the-status-when-the-proposition-is-accepted}

Una volta che una proposta di offerta è stata **accettata**, utilizza uno dei valori forniti per impostazione predefinita per configurare il nuovo stato della proposta. L’aggiornamento viene applicato quando un destinatario fa clic su un collegamento nell’offerta.

A questo scopo, segui la procedura indicata di seguito:

1. Passare alla scheda **[!UICONTROL Storage]** dello spazio desiderato.
1. Seleziona lo stato da applicare alla proposta quando viene accettata.

   ![](assets/offer_update_status_002.png)


**Interazione in entrata**

La scheda **[!UICONTROL Storage]** ti consente di definire gli stati solo per le proposte di offerta **proposte** e **accettate**. Per l’interazione in entrata, lo stato delle proposte di offerta deve essere specificato direttamente nell’URL per la chiamata al motore di offerta, anziché tramite l’interfaccia. In questo modo, potrai specificare lo stato da applicare in altri casi, ad esempio se una proposta di offerta viene rifiutata.

```
<BASE_URL>?a=UpdateStatus&p=<PRIMARY_KEY_OF_THE_PROPOSITION>&st=<NEW_STATUS_OF_THE_PROPOSITION>&r=<REDIRECT_URL>
```

Ad esempio, la proposta (identificatore **40004**) che corrisponde all&#39;offerta **Assicurazione sulla casa** visualizzata nel sito **Neobank** contiene il seguente URL:

```
<BASE_URL>?a=UpdateStatus&p=<40004>&st=<3>&r=<"http://www.neobank.com/insurance/subscribe.html">
```

Non appena un visitatore fa clic sull&#39;offerta, e quindi sull&#39;URL, lo stato **[!UICONTROL Accepted]** (valore **3**) viene applicato alla proposta e il visitatore viene reindirizzato a una nuova pagina del sito **Neobank** per sottoscrivere il contratto di assicurazione.

>[!NOTE]
>
>Se desideri specificare un altro stato nell’URL (ad esempio se una proposta di offerta viene rifiutata), utilizza il valore corrispondente allo stato desiderato. Esempio: **[!UICONTROL Rejected]** = &quot;5&quot;, **[!UICONTROL Presented]** = &quot;1&quot; ecc.
>
>Gli stati e i relativi valori possono essere recuperati nello schema di dati **[!UICONTROL Offer propositions (nms)]**. Per ulteriori informazioni, consulta [questa pagina](../dev/create-schema.md).

**Interazione in uscita**

È possibile applicare automaticamente lo stato **[!UICONTROL Interested]** a una proposta di offerta quando la consegna contiene un collegamento. È sufficiente aggiungere il valore **_urlType=&quot;11&quot;** al collegamento:

```
<a _urlType="11" href="<DEST_URL>">Link inserted into the delivery</a>
```

## Anteprima offerta per spazio {#offer-preview-per-space}

Nella scheda **[!UICONTROL Preview]**, è possibile visualizzare le offerte per le quali il destinatario è idoneo tramite un metodo scelto. Nell’esempio che segue, il destinatario può presentare tre proposte di offerta per posta.

![](assets/offer_space_overview_002.png)

Se un destinatario non è idoneo per nessuna offerta, ciò viene mostrato nell’anteprima.

![](assets/offer_space_overview_001.png)


L’anteprima può ignorare i contesti quando sono limitati a uno spazio. Ciò si verifica quando lo schema di interazione è stato esteso per aggiungere campi a cui si fa riferimento in uno spazio utilizzando un canale in entrata.

Per ulteriori informazioni, consulta questo esempio nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/managing-offers/advanced-parameters/extension-example.html){target="_blank"}.