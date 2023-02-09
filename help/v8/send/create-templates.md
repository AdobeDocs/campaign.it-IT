---
product: campaign
title: Utilizzare i modelli di consegna
description: Scopri come creare e utilizzare modelli di consegna in Campaign
feature: Email, Push, SMS, Direct Mail, Cross Channel Orchestration
role: User
level: Beginner
exl-id: 3a4de36e-ba24-49ec-8113-f32f12c8ecdd
source-git-commit: 77ec01aaba1e50676bed57f503a9e4e8bb1fe54c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 8%

---

# Utilizzare il modello di consegna{#work-with-delivery-template}

Utilizza i modelli di consegna per standardizzare l’aspetto creativo e l’aspetto, al fine di velocizzare l’esecuzione e l’avvio delle campagne.

Un modello può includere sistematicamente:

* Tipologie
* Indirizzi di invio e risposta
* Blocchi di personalizzazione di base
* Collegamenti a pagine mirror e annullamento dell’abbonamento collegamenti
* Contenuto, logo aziendale o firma
* Altre proprietà di consegna, ad esempio la validità della risorsa, i parametri dei nuovi tentativi o le impostazioni di quarantena.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#delivery-template-video)


## Creare un modello{#create-a-delivery-template}

Per creare un modello di consegna, puoi duplicare un modello incorporato, convertire una consegna esistente in un modello o creare un modello di consegna da zero.

### Duplicare un modello esistente{#copy-an-existing-template}

Campaign viene fornito con un set di modelli incorporati per ciascun canale: e-mail, push, SMS, direct mailing e altro ancora.

Il modo più semplice per creare un modello di consegna è quello di duplicare e personalizzare un modello incorporato.

Per duplicare un modello di consegna, segui i passaggi seguenti:

1. Sfoglia per **[!UICONTROL Resources > Templates > Delivery templates]** in Adobe Campaign explorer.
1. Seleziona un modello di consegna integrato. I modelli incorporati sono inseriti in un elenco.
1. Fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Duplicate]**.

   ![](assets/duplicate-built-in-template.png)

1. Definisci le impostazioni del modello e salva il nuovo modello.

   ![](assets/delivery-template-new.png)

Il modello viene aggiunto all’elenco dei modelli di consegna. Ora puoi selezionarlo quando crei una nuova consegna.

![](assets/select-the-new-template.png)

### Convertire una consegna esistente in un modello {#convert-an-existing-delivery}

Una consegna può essere convertita in un modello per nuove azioni di consegna ripetute.

Per convertire una consegna in un modello, segui la procedura seguente:

1. Seleziona la consegna dall’elenco di consegna, accessibile tramite il **[!UICONTROL Campaign management]** nodo di Campaign explorer.

1. Fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Actions > Save as template...]**.

   ![](assets/save-as-template.png)

1. Modifica le proprietà di consegna e seleziona la cartella in cui deve essere salvato il nuovo modello (nel **[!UICONTROL Folder]** e la cartella in cui devono essere create le consegne create in base a questo modello (nel **[!UICONTROL Execution folder]** (campo).

   ![](assets/template-select-folders.png)

### Creare un nuovo modello {#create-a-new-template}

>[!NOTE]
>
>Per evitare errori di configurazione, l’Adobe consiglia di [duplicare un modello incorporato](#copy-an-existing-template) e personalizzane le proprietà anziché creare un nuovo modello.

Per configurare un modello di consegna da zero, segui i passaggi seguenti:

1. Sfoglia il **Risorse** in Esplora risorse di Campaign e seleziona **Modelli** then **Modelli di consegna**.
1. Fai clic su **Nuovo** nella barra degli strumenti per creare un nuovo modello di consegna.
1. Imposta la **Etichetta** e **Nome interno** della cartella.
1. Salva il modello e riaprilo.
1. Da **Proprietà** , adatta le impostazioni.
1. In **Generale** , confermare o modificare le posizioni selezionate nella **Cartella di esecuzione**, **Cartella** e **Indirizzamento** menu a discesa.
1. Completa il **Parametri e-mail** categoria con l’oggetto dell’e-mail e la popolazione target.
1. Aggiungi il tuo **Contenuto HTML** per personalizzare il modello, puoi visualizzare un collegamento a una pagina speculare e un collegamento di annullamento all’abbonamento.
1. Seleziona la **Anteprima** scheda . In **Personalizzazione dei test** menu a discesa, seleziona **Destinatario** per visualizzare in anteprima il modello come profilo scelto.
1. Fai clic su **Salva**. Il modello è ora pronto per essere utilizzato in una consegna.


## Utilizzare i modelli{#use-a-delivery-template}

### Creare una consegna da un modello{#create-a-delivery-from-a-template}

Per creare una consegna basata su un modello esistente, seleziona il modello dall’elenco dei modelli di consegna disponibili.

![](assets/select-the-new-template.png)

Se non riesci a visualizzare il modello, fai clic sul pulsante **[!UICONTROL Select link]** a destra del campo per sfogliare le cartelle di Campaign.

![](assets/browse-templates.png)

Seleziona la directory desiderata dal **[!UICONTROL Folder]** oppure fai clic sul campo **[!UICONTROL Display sub-levels]** per visualizzare il contenuto delle directory nelle sottostrutture della directory corrente.

Seleziona il modello di consegna da utilizzare e fai clic su **[!UICONTROL Ok]**.

### Eseguire un modello {#execute-a-template}

Puoi avviare l’esecuzione di un modello direttamente dall’elenco dei modelli senza prima creare una consegna.

A questo scopo, seleziona il modello da eseguire e fai clic con il pulsante destro del mouse sul modello da eseguire. Seleziona **[!UICONTROL Actions>Execute the delivery template...]**.

È inoltre possibile utilizzare **[!UICONTROL File>Actions>Execute the delivery template...]**.

![](assets/execute-delivery-template.png)

Immetti i parametri di consegna e fai clic su **[!UICONTROL Send]**.

Questa azione genera una consegna nella cartella associata al modello. Il nome di questa consegna è il nome del modello di consegna da cui è stata creata.


## Video tutorial {#delivery-template-video}

### Come configurare un modello di consegna

Il video seguente illustra come configurare un modello per una consegna ad hoc.

>[!VIDEO](https://video.tv.adobe.com/v/342082?quality=12)

### Come impostare le proprietà dei modelli di consegna

Il video seguente mostra come impostare le proprietà del modello di consegna e spiega in dettaglio ciascuna proprietà .

>[!VIDEO](https://video.tv.adobe.com/v/338969?quality=12)

### Come distribuire un modello di consegna ad hoc

Questo video spiega come distribuire un modello di consegna e-mail ad hoc e spiega la differenza tra una consegna e-mail e un flusso di lavoro di consegna.

>[!VIDEO](https://video.tv.adobe.com/v/338965?quality=12)

Sono disponibili ulteriori video dimostrativi su Campaign Classic [qui](https://experienceleague.adobe.com/docs/campaign-classic-learn/tutorials/overview.html?lang=it).
