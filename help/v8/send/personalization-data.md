---
title: Origini dati di Personalization
description: Scopri quali origini possono essere utilizzate per la personalizzazione
feature: Personalization
role: User
level: Beginner
exl-id: 711256e2-ab77-404a-b052-6793a85da193
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Origini dati di Personalization{#personalization-data}

I dati di Personalization possono essere recuperati da vari tipi di origini: origine dati del database di Campaign, origine dati di file esterno o origine dati del database esterno.

## Origine dati del database di Campaign

Nel caso più comune, i dati di personalizzazione vengono memorizzati nel database. Ad esempio, i &quot;campi di personalizzazione dei destinatari&quot; sono tutti i campi definiti nella tabella dei destinatari, i campi standard (in genere: cognome, nome, indirizzo, città, data di nascita e così via) o i campi personalizzati.

![Campi di personalizzazione della campagna in un messaggio e-mail](assets/perso-campaign-datasource.png)


## Origine dati file esterno

Puoi utilizzare un file esterno contenente tutti i campi definiti nelle colonne. Questo file viene utilizzato come input durante la definizione della consegna di un messaggio. Puoi scegliere se inserire o meno tali profili nel database.

Per selezionare il file da utilizzare come origine dati, passare al collegamento A nella finestra di creazione del messaggio e selezionare l&#39;opzione **Definito in un file esterno**. Una volta caricato il file, accedi ai dati dei destinatari nelle opzioni di personalizzazione dalla voce **Fields del file**.

![Dati Personalization da un file](assets/perso-from-file.png)


## Origine dati FDA

I dati Personalization possono essere estratti da una tabella esterna tramite [Federated Data Access](../connect/fda.md).  Se desideri eseguire la personalizzazione nelle consegne utilizzando i dati del database esterno, raccogli i dati da utilizzare in un flusso di lavoro per renderli disponibili in una tabella temporanea.

Per eseguire questa operazione, aggiungere un&#39;attività **Query** nel flusso di lavoro di targeting e utilizzare il collegamento **Aggiungi dati...** per selezionare il database esterno. Il processo dettagliato è disponibile in [questa sezione](../../automation/workflow/query.md#adding-data).

Quindi utilizza i dati della tabella temporanea per personalizzare la consegna. Una volta configurata l&#39;attività Query, accedi ai dati esterni nelle opzioni di personalizzazione dalla voce **Estensione Target**.

![Dati Personalization da un database esterno](assets/perso-external-db.png)

Quando si utilizzano dati esterni accessibili in FDA, si consiglia di pre-elaborare la personalizzazione dei messaggi in un flusso di lavoro dedicato utilizzando l&#39;opzione **Prepara i dati di personalizzazione con un flusso di lavoro** come descritto di seguito.

### Ottimizzare la personalizzazione {#optimize-personalization}

Puoi ottimizzare la personalizzazione utilizzando un&#39;opzione dedicata: **[!UICONTROL Prepare the personalization data with a workflow]**, disponibile nella scheda **[!UICONTROL Analysis]** delle proprietà di consegna.

Durante l’analisi della consegna, questa opzione crea ed esegue automaticamente un flusso di lavoro che memorizza tutti i dati collegati al target in una tabella temporanea, inclusi i dati di tabelle collegate in FDA.

Selezionando questa opzione è possibile migliorare notevolmente le prestazioni dell’analisi della consegna quando molti dati vengono elaborati, soprattutto se i dati di personalizzazione provengono da una tabella esterna tramite FDA. [Ulteriori informazioni](../connect/fda.md).

Per utilizzare questa opzione, effettua le seguenti operazioni:

1. Creare una campagna.
1. Nella scheda **[!UICONTROL Targeting and workflows]** della campagna, aggiungi un&#39;attività **Query** al flusso di lavoro.
1. Aggiungere un&#39;attività **[!UICONTROL Email delivery]** al flusso di lavoro e aprirla.
1. Passare alla scheda **[!UICONTROL Analysis]** di **[!UICONTROL Delivery properties]** e selezionare l&#39;opzione **[!UICONTROL Prepare the personalization data with a workflow]**.
1. Configura la consegna e avvia il flusso di lavoro per avviare l’analisi.

Al termine dell’analisi, i dati di personalizzazione vengono memorizzati in una tabella temporanea tramite un flusso di lavoro tecnico temporaneo creato al volo durante l’analisi.

Questo flusso di lavoro non è visibile nell’interfaccia di Adobe Campaign. Deve solo essere un mezzo tecnico per archiviare e gestire rapidamente i dati di personalizzazione.

Al termine dell&#39;analisi, passare al flusso di lavoro **[!UICONTROL Properties]** e selezionare la scheda **[!UICONTROL Variables]**. Qui è possibile visualizzare il nome della tabella temporanea che è possibile utilizzare per effettuare una chiamata SQL per visualizzare gli ID in essa contenuti.

## Dati Personalization in un flusso di lavoro

Quando una consegna viene creata nel contesto di un flusso di lavoro, puoi utilizzare i dati della tabella del flusso di lavoro temporaneo. I dati memorizzati nella tabella di lavoro temporanea del flusso di lavoro sono disponibili per le attività di personalizzazione. I dati possono essere utilizzati nei campi di personalizzazione.

Questi dati sono raggruppati nel menu **[!UICONTROL Target extension]**. Per ulteriori informazioni, consulta [questa sezione](../../automation/workflow/use-workflow-data.md#target-data).
