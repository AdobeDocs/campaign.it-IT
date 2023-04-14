---
title: Origini dati di personalizzazione
description: Scopri quali fonti possono essere utilizzate per la personalizzazione
feature: Personalization
role: User
level: Beginner
exl-id: 711256e2-ab77-404a-b052-6793a85da193
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Origini dati di personalizzazione{#personalization-data}

I dati di personalizzazione possono essere recuperati da vari tipi di origini: Origine dati del database Campaign, origine dati file esterna o origine dati del database esterno.

## Origine dati del database Campaign

Nel caso più comune, i dati di personalizzazione vengono memorizzati nel database. Ad esempio, i &quot;campi di personalizzazione dei destinatari&quot; sono tutti i campi definiti nella tabella dei destinatari, i campi standard (in genere: cognome, nome, indirizzo, città, data di nascita, ecc.) o campi personalizzati.

![Campi di personalizzazione delle campagne in un messaggio e-mail](assets/perso-campaign-datasource.png)


## Origine dati file esterna

Puoi utilizzare un file esterno contenente tutti i campi definiti nelle colonne. Questo file viene utilizzato come input durante la definizione della consegna di un messaggio. Puoi scegliere di inserire o meno tali profili nel database.

Per selezionare il file da utilizzare come origine dati, passare al collegamento A nella finestra di creazione del messaggio e selezionare il pulsante **Definito in un file esterno** opzione . Una volta caricato il file, accedi ai dati dei destinatari nelle opzioni di personalizzazione dal **Campi del file** voce.

![Dati di personalizzazione da un file](assets/perso-from-file.png)


## Origine dati FDA

I dati di personalizzazione possono essere estratti da una tabella esterna tramite [Federated Data Access](../connect/fda.md).  Se desideri eseguire la personalizzazione nelle consegne utilizzando i dati del database esterno, raccogli i dati da utilizzare in un flusso di lavoro per renderli disponibili in una tabella temporanea.

Per eseguire questa operazione, aggiungi una **Query** nel flusso di lavoro di targeting e utilizza **Aggiungi dati...** collegamento per selezionare il database esterno. Il processo dettagliato è disponibile in [questa sezione](../../automation/workflow/query.md#adding-data).

Quindi utilizza i dati della tabella temporanea per personalizzare la consegna. Una volta configurata l’attività di query, accedi ai dati esterni nelle opzioni di personalizzazione dal **Estensione Target** voce.

![Dati di personalizzazione da un database esterno](assets/perso-external-db.png)

Quando utilizzi dati esterni a cui accedi in FDA, è consigliabile preelaborare la personalizzazione dei messaggi in un flusso di lavoro dedicato utilizzando **Preparare i dati di personalizzazione con un flusso di lavoro** come descritto di seguito.

### Ottimizzare la personalizzazione {#optimize-personalization}

Puoi ottimizzare la personalizzazione utilizzando un’opzione dedicata: **[!UICONTROL Prepare the personalization data with a workflow]**, disponibile nella **[!UICONTROL Analysis]** scheda delle proprietà di consegna.

Durante l’analisi della consegna, questa opzione crea ed esegue automaticamente un flusso di lavoro che memorizza in una tabella temporanea tutti i dati collegati alla destinazione, inclusi i dati provenienti da tabelle collegate in FDA.

La selezione di questa opzione può migliorare notevolmente le prestazioni dell’analisi della consegna quando vengono elaborati molti dati, soprattutto se i dati di personalizzazione provengono da una tabella esterna tramite FDA. [Ulteriori informazioni](../connect/fda.md).

Per utilizzare questa opzione, segui i passaggi seguenti:

1. Creare una campagna.
1. In **[!UICONTROL Targeting and workflows]** scheda della campagna, aggiungi una **Query** al flusso di lavoro.
1. Aggiungi un **[!UICONTROL Email delivery]** al flusso di lavoro e aprilo.
1. Vai a **[!UICONTROL Analysis]** della scheda **[!UICONTROL Delivery properties]** e seleziona la **[!UICONTROL Prepare the personalization data with a workflow]** opzione .
1. Configura la consegna e avvia il flusso di lavoro per avviare l’analisi.

Una volta effettuata l’analisi, i dati di personalizzazione vengono memorizzati in una tabella temporanea tramite un flusso di lavoro tecnico temporaneo creato al volo durante l’analisi.

Questo flusso di lavoro non è visibile nell’interfaccia di Adobe Campaign. Si tratta solo di uno strumento tecnico per archiviare e gestire rapidamente i dati di personalizzazione.

Al termine dell’analisi, passa al flusso di lavoro **[!UICONTROL Properties]** e seleziona la **[!UICONTROL Variables]** scheda . Qui puoi vedere il nome della tabella temporanea che puoi utilizzare per effettuare una chiamata SQL per visualizzare gli ID contenuti.

## Dati di personalizzazione in un flusso di lavoro

Quando una consegna viene creata nel contesto di un flusso di lavoro, puoi utilizzare i dati della tabella del flusso di lavoro temporaneo. I dati memorizzati nella tabella di lavoro temporaneo del flusso di lavoro sono disponibili per le attività di personalizzazione. I dati possono essere utilizzati nei campi di personalizzazione.

Questi dati sono raggruppati nel **[!UICONTROL Target extension]** menu. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automation/workflow/use-workflow-data.md#target-data).
