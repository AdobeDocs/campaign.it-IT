---
product: campaign
title: Risorse, documenti e linee di consegna della campagna di marketing
description: Ulteriori informazioni sui documenti e i profili di consegna delle campagne di marketing
feature: Campaigns
exl-id: 352f6cd5-777d-413d-af79-6f53444b336f
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 0%

---

# Gestione di risorse e documenti {#manage-assets-documents}

È possibile associare vari documenti a una campagna: rapporti, foto, pagine web, diagrammi, ecc. Questi documenti possono essere in qualsiasi formato.

In una campagna puoi anche fare riferimento ad altri articoli, come coupon promozionali, offerte speciali relative a uno specifico marchio o negozio, ecc. Quando questi elementi sono inclusi in una struttura, possono essere associati a una consegna direct mailing. [Ulteriori informazioni](#associating-and-structuring-resources-linked-via-a-delivery-outline).


>[!CAUTION]
>
>Questa funzionalità è progettata per le risorse e i documenti di piccole dimensioni.

<!--
>[!NOTE]
>
>If you are using Campaign Marketing Resource Management module, you can also manage a library of marketing resources that are available for several users for collaborative work. [Learn more](../../mrm/using/managing-marketing-resources.md).
-->

## Aggiungi documenti {#add-documents}

I documenti possono essere associati a livello di campagna (documenti contestuali) o a livello di programma (documenti generali).

Per una campagna, la **[!UICONTROL Documents]** la scheda contiene:

* Elenco di tutti i documenti richiesti per il contenuto (modello, immagini, ecc.) che possono essere scaricati localmente dagli operatori Adobe Campaign con diritti adeguati,
* Documenti contenenti informazioni relative al router, se presenti.

I documenti sono collegati al programma o alla campagna tramite il **[!UICONTROL Edit > Documents]** scheda .

![](assets/op_add_document.png)

Puoi anche aggiungere un documento a una campagna dal collegamento dedicato nel dashboard.

![](assets/add_a_document_in_op.png)

Fai clic sul pulsante **[!UICONTROL Detail...]** per visualizzare il contenuto di un file e aggiungere informazioni:

![](assets/add_document_details.png)

Nel dashboard, i documenti associati alla campagna sono raggruppati nel **[!UICONTROL Document(s)]** come nell’esempio seguente:

![](assets/edit_documents.png)

È inoltre possibile modificarli e modificarli da questa visualizzazione.

## Utilizzare i profili di consegna {#delivery-outlines}

Un profilo di consegna è un insieme strutturato di elementi (documenti, negozi, coupon promozionali, ecc.) creato dalla società e per una campagna particolare. Viene utilizzato nel contesto delle consegne di direct mailing.

Tali elementi sono raggruppati in profili di consegna e ogni profilo di consegna sarà associato a una consegna; nel file di estrazione inviato al **fornitore di servizi** da allegare alla consegna. Ad esempio, puoi creare un profilo di consegna che faccia riferimento a un’unità e alle brochure di marketing che utilizza.

Per una campagna, i profili di consegna ti consentono di strutturare elementi esterni da associare alla consegna in base a determinati criteri: unità collegata, offerta promozionale concessa, invito a un evento locale, ecc.

>[!CAUTION]
>
>I profili di consegna sono limitati alle campagne di direct mailing.

### Creare un profilo di consegna {#create-an-outline}

Per creare una struttura di consegna, fai clic sul pulsante **[!UICONTROL Delivery outlines]** sottoscheda in **[!UICONTROL Edit > Documents]** scheda della campagna interessata.

![](assets/add-a-delivery-outline.png)


>[!NOTE]
>
>Se non riesci a visualizzare questa scheda, questa funzionalità non è disponibile per questa campagna oppure la consegna della direct mailing non è abilitata nell’istanza. Fai riferimento a [configurazione del modello di campagna](marketing-campaign-templates.md#campaign-templates) o al contratto di licenza.

Quindi, fai clic su **[!UICONTROL Add a delivery outline]** e crea la gerarchia di profili per la campagna:

1. Fare clic con il pulsante destro del mouse sulla radice dell&#39;albero e selezionare **[!UICONTROL New > Delivery outlines]**.
1. Fai clic con il pulsante destro del mouse sul profilo appena creato e seleziona **[!UICONTROL New > Item]** o **[!UICONTROL New > Personalization fields]**.

![](assets/del-outline-add-new-item.png)

Una struttura può contenere elementi, campi di personalizzazione e offerte:

* Gli elementi possono essere documenti fisici, ad esempio, a cui viene fatto riferimento e descritto qui e che verranno allegati alla consegna.
* I campi di personalizzazione ti consentono di creare elementi di personalizzazione relativi alle consegne anziché ai destinatari. È quindi possibile creare valori da utilizzare nelle consegne per un target specifico (offerta di benvenuto, uno sconto, ecc.) Vengono creati in Adobe Campaign e importati nella struttura tramite il **[!UICONTROL Import personalization fields...]** link.

   ![](assets/del-outline-perso-field.png)

   È inoltre possibile crearli direttamente nel profilo facendo clic sul pulsante **[!UICONTROL Add]** a destra della zona elenco.

   ![](assets/add-del-outline-button.png)


### Selezionare una struttura {#select-an-outline}

Per ogni consegna, puoi selezionare il profilo da associare dalla sezione riservata al profilo di estrazione, come nell’esempio seguente:

![](assets/select-delivery-outline.png)

Il profilo selezionato viene quindi visualizzato nella sezione inferiore della finestra. Può essere modificato utilizzando l’icona a destra del campo o utilizzando l’elenco a discesa:

![](assets/delivery-outline-selected.png)

La **[!UICONTROL Summary]** La scheda della consegna visualizza anche queste informazioni:

![](assets/delivery-outline-in-dashboard.png)

### Risultato estrazione {#extraction-result}

Nel file estratto e inviato al fornitore di servizi, il nome del profilo e, se del caso, le sue caratteristiche (costo, descrizione, ecc.) vengono aggiunti al contenuto in base alle informazioni nel modello di esportazione associato al provider di servizi.

Nell’esempio seguente, l’etichetta, il costo stimato e la descrizione del profilo associato alla consegna verranno aggiunti al file di estrazione.

![](assets/campaign-export-template.png)

Il modello di esportazione deve essere associato al fornitore di servizi selezionato per la consegna in questione. Vedi [questa sezione](providers--stocks-and-budgets.md#creating-service-providers-and-their-cost-structures).
