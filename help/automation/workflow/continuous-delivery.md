---
product: campaign
title: Consegna continua
description: Consegna continua
feature: Workflows, Channels Activity
exl-id: e3ad6d92-8d53-4098-90fd-cfed29f2e56e
source-git-commit: edb099b3e882d857752af76798012ccd1c5a99be
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 9%

---

# Consegna continua{#continuous-delivery}



A **Consegna continua** l’azione di tipo ti consente di aggiungere nuovi destinatari a una consegna esistente. Questo tipo di consegna evita di dover creare ogni volta una nuova consegna: questa modalità è spesso più efficiente, in particolare per gli avvisi o le notifiche di basso volume inviate come e quando necessario.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#continuous-delivery-video)

A livello di modello di consegna, puoi specificare uno script per calcolare l’etichetta (e la cartella della campagna) della consegna associata. Se lo script calcola una consegna che non esiste ancora, viene creato al volo.

![](assets/edit_diffusion_fil.png)

Il **[!UICONTROL Process errors]** visualizza una particolare transizione che verrà attivata se viene generato un errore. In questo caso, il flusso di lavoro non entra in modalità di errore e continua con l’esecuzione.

Gli errori presi in considerazione sono errori del file system (file non spostabile, directory non accessibile, ecc.).

Questa opzione non elabora gli errori relativi alla configurazione dell’attività, ovvero valori non validi.

## Parametri di input {#input-parameters}

* tableName
* schema

Ogni evento in entrata deve specificare una destinazione definita da questi parametri.

Solo quando **[!UICONTROL Specified by the inbound event]** è selezionata.

## Parametri di output {#output-parameters}

* tableName
* schema
* recCount

Questo set di tre valori identifica il target risultante dalla consegna immediata. **[!UICONTROL tableName]** è il nome della tabella che memorizza gli identificatori dell&#39;oggetto, **[!UICONTROL schema]** è lo schema della popolazione (in genere nms:recipient) e **[!UICONTROL recCount]** è il numero di elementi nella tabella.

La transizione associata al complemento ha gli stessi parametri.

## Come impostare una consegna continua

Questa sezione spiega come impostare una consegna continua.

Il **consegna continua** consente di aggiungere nuovi destinatari a una consegna esistente ed evita di dover crearne una nuova ogni volta che viene aggiunto un destinatario. Puoi aggiornare il contenuto creativo direttamente nel flusso di lavoro della campagna, mentre il modello verrà aggiornato nella cartella Risorse del modello di consegna.

Una consegna continua creerà un SINGOLO registro di consegna e consegna (broadLog) e registri di tracciamento che fanno riferimento a tale consegna aggiunti ogni volta che viene eseguita.

![Consegna continua](assets/delivery_continuous.jpg)

## Video tutorial {#continuous-delivery-video}

Questo video mostra come configurare una consegna continua con una query incrementale.

>[!VIDEO](https://video.tv.adobe.com/v/25039?quality=12)

Sono disponibili altri video dimostrativi di Campaign [qui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html){target="_blank"}.
