---
product: campaign
title: Consegna continua
description: Consegna continua
feature: Workflows, Channels Activity
role: User
version: Campaign v8, Campaign Classic v7
exl-id: e3ad6d92-8d53-4098-90fd-cfed29f2e56e
source-git-commit: 4cbccf1ad02af9133d51933e3e0d010b5c8c43bd
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 10%

---

# Consegna continua{#continuous-delivery}



Un&#39;azione di tipo **Consegna continua** consente di aggiungere nuovi destinatari a una consegna esistente. Questo tipo di consegna evita di dover creare ogni volta una nuova consegna: questa modalità è spesso più efficiente, in particolare per gli avvisi o le notifiche di basso volume inviate come e quando necessario.

![](assets/do-not-localize/how-to-video.png) [Guarda il video su questa funzione](#continuous-delivery-video)

A livello di modello di consegna, puoi specificare uno script per calcolare l’etichetta (e la cartella della campagna) della consegna associata. Se lo script calcola una consegna che non esiste ancora, viene creato al volo.

![](assets/edit_diffusion_fil.png)

L&#39;opzione **[!UICONTROL Process errors]** visualizza una transizione particolare che verrà attivata se viene generato un errore. In questo caso, il flusso di lavoro non entra in modalità di errore e continua con l’esecuzione.

Gli errori presi in considerazione sono errori del file system (file non spostabile, directory non accessibile, ecc.).

Questa opzione non elabora gli errori relativi alla configurazione dell’attività, ovvero valori non validi.

## Parametri di input {#input-parameters}

* tableName
* schema

Ogni evento in entrata deve specificare una destinazione definita da questi parametri.

Solo quando è selezionata l&#39;opzione **[!UICONTROL Specified by the inbound event]**.

## Parametri di output {#output-parameters}

* tableName
* schema
* recCount

Questo set di tre valori identifica il target risultante dalla consegna immediata. **[!UICONTROL tableName]** è il nome della tabella che memorizza gli identificatori della destinazione, **[!UICONTROL schema]** è lo schema della popolazione (in genere nms:recipient) e **[!UICONTROL recCount]** è il numero di elementi nella tabella.

La transizione associata al complemento ha gli stessi parametri.

## Come impostare una consegna continua

Questa sezione spiega come impostare una consegna continua.

La **consegna continua** ti consente di aggiungere nuovi destinatari a una consegna esistente ed evita di dover crearne una nuova ogni volta che viene aggiunto un nuovo destinatario. Puoi aggiornare il contenuto creativo direttamente nel flusso di lavoro della campagna, mentre il modello verrà aggiornato nella cartella Risorse del modello di consegna.

Una consegna continua creerà un SINGOLO registro di consegna e consegna (broadLog) e registri di tracciamento che fanno riferimento a tale consegna aggiunti ogni volta che viene eseguita.

![Consegna continua](assets/delivery_continuous.jpg)

## Video tutorial {#continuous-delivery-video}

Questo video mostra come configurare una consegna continua con una query incrementale.

>[!VIDEO](https://video.tv.adobe.com/v/25039?quality=12)

Ulteriori video dimostrativi di Campaign sono disponibili [qui](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/getting-started/introduction-to-adobe-campaign.html?lang=it){target="_blank"}.
