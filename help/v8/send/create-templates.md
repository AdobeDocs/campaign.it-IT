---
product: campaign
title: Utilizzare i modelli di consegna
description: Scopri come creare e utilizzare i modelli di consegna in Campaign
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: 34af97ae01f7dba418fd0a8c950fc549dfbbd98b
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 33%

---

# Utilizzare i modelli di consegna{#work-with-delivery-template}

Utilizza i modelli di consegna per uniformare l’aspetto creativo delle comunicazioni e velocizzare l’esecuzione e il lancio delle campagne.

Un modello può includere:

* Tipologie
* Indirizzi di invio e risposta
* Base [blocchi di personalizzazione](../send/personalization-blocks.md)
* Collegamenti a [pagine mirror](../send/mirror-page.md) e i collegamenti di annullamento dell’abbonamento
* Contenuto, logo dell’azienda o firma
* Altre proprietà di consegna, ad esempio validità della risorsa, parametri dei nuovi tentativi o impostazioni della quarantena.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#delivery-template-video)


## Creare un modello{#create-a-delivery-template}

Per creare un modello di consegna, è possibile duplicare un modello incorporato, convertire una consegna esistente in un modello o creare un modello di consegna da zero.

### Duplicare un modello esistente{#copy-an-existing-template}

Campaign è dotato di un set di modelli incorporati per ogni canale: e-mail, push, SMS, direct mail e altro ancora.

Il modo più semplice per creare un modello di consegna è consiste nel duplicare e personalizzare un modello incorporato.

Per duplicare un modello di consegna, segui la procedura seguente:

1. Sfoglia per **[!UICONTROL Resources > Templates > Delivery templates]** in Adobe Campaign explorer.
1. Seleziona un modello di consegna integrato. I modelli incorporati sono visualizzati in grassetto nell’elenco.
1. Fai clic con il pulsante destro del mouse e seleziona (Copia negli Appunti) **[!UICONTROL Duplicate]**.

   ![](assets/duplicate-built-in-template.png)

1. Definisci le impostazioni del modello e salva il nuovo modello.

   ![](assets/delivery-template-new.png)

Il modello viene aggiunto all’elenco dei modelli di consegna. Ora puoi selezionarlo durante la creazione di una nuova consegna.

![](assets/select-the-new-template.png)

### Convertire una consegna esistente in un modello {#convert-an-existing-delivery}

Una consegna può essere convertita in un modello per nuove azioni di consegna ripetute.

Per convertire una consegna in un modello, segui la procedura seguente:

1. Seleziona la consegna dall’elenco di consegna, accessibile tramite **[!UICONTROL Campaign management]** nodo di Campaign explorer.

1. Fai clic con il pulsante destro del mouse e seleziona (Copia negli Appunti) **[!UICONTROL Actions > Save as template...]**.

   ![](assets/save-as-template.png)

1. Modifica le proprietà di consegna e seleziona la cartella in cui salvare il nuovo modello (nel **[!UICONTROL Folder]** ) e la cartella in cui devono essere create le consegne basate su questo modello (nel **[!UICONTROL Execution folder]** ).

   ![](assets/template-select-folders.png)

### Creare un nuovo modello {#create-a-new-template}

>[!NOTE]
>
>Per evitare errori di configurazione, Adobe consiglia di [duplicare un modello incorporato](#copy-an-existing-template) e personalizzarne le proprietà anziché creare un nuovo modello.

Per configurare un modello di consegna da zero, segui la procedura seguente:

1. Accedi a **Risorse** in Esplora campagne e seleziona **Modelli** allora **Modelli di consegna**.
1. Clic **Nuovo** nella barra degli strumenti per creare un nuovo modello di consegna.
1. Imposta il **Etichetta** e **Nome interno** della cartella.
1. Salva il modello e riaprilo.
1. Dalla sezione **Proprietà** , adattare le impostazioni.
1. In **Generale** , confermare o modificare le posizioni selezionate nella scheda **Cartella di esecuzione**, **Cartella**, e **Indirizzamento** menu a discesa.
1. Completa il **Parametri e-mail** categoria con l’oggetto dell’e-mail e la popolazione target.
1. Aggiungi il **Contenuto HTML** per personalizzare il modello, puoi visualizzare una [collegamento pagina mirror](../send/mirror-page.md) e un collegamento per annullare l’abbonamento.
1. Seleziona la **Anteprima** scheda. In **Test personalizzazione** menu a discesa, seleziona **Destinatario** per visualizzare in anteprima il modello come profilo scelto.
1. Fai clic su **Salva**. Il modello è ora pronto per essere utilizzato in una consegna.


## Utilizzare i modelli{#use-a-delivery-template}

### Creare una consegna da un modello{#create-a-delivery-from-a-template}

Per creare una consegna basata su un modello esistente, seleziona il modello dall’elenco dei modelli di consegna disponibili.

![](assets/select-the-new-template.png)

Se non riesci a visualizzare il modello, fai clic su **[!UICONTROL Select link]** a destra del campo per sfogliare le cartelle di Campaign.

![](assets/browse-templates.png)

Seleziona la directory desiderata da **[!UICONTROL Folder]** o fai clic sul pulsante **[!UICONTROL Display sub-levels]** per visualizzare il contenuto delle directory nelle sottostrutture della directory corrente.

Seleziona il modello di consegna da utilizzare e fai clic su **[!UICONTROL Ok]**.

### Eseguire un modello {#execute-a-template}

Puoi avviare l’esecuzione di un modello direttamente dall’elenco dei modelli senza prima creare una consegna.

A questo scopo, seleziona il modello da eseguire e fai clic con il pulsante destro del mouse. Seleziona **[!UICONTROL Actions>Execute the delivery template...]**.

Puoi anche utilizzare **[!UICONTROL File>Actions>Execute the delivery template...]**.

![](assets/execute-delivery-template.png)

Inserisci i parametri di consegna e fai clic su **[!UICONTROL Send]**.

Questa azione genera una consegna nella cartella associata al modello. Il nome di questa consegna è il nome del modello di consegna da cui è stata creata.


## Video tutorial {#delivery-template-video}

### Come configurare un modello di consegna

Il video seguente illustra come configurare un modello per una consegna ad hoc.

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### Impostare le proprietà dei modelli di consegna

Il video seguente mostra come impostare le proprietà del modello di consegna e spiega in dettaglio ciascuna proprietà.

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### Come distribuire un modello di consegna ad hoc

Questo video spiega come distribuire un modello di consegna e-mail ad hoc e la differenza tra una consegna e-mail e un flusso di lavoro di consegna.

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

Sono disponibili altri video dimostrativi di Campaign [qui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
