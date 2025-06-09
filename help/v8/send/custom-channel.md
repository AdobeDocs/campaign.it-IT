---
title: Introduzione ai canali esterni personalizzati
description: Scopri come creare e inviare consegne personalizzate di canali esterni con Adobe Campaign Web
role: User
level: Beginner, Intermediate
exl-id: d2d92de6-3974-41c5-a0fd-09bbf6cf0020
source-git-commit: f94074d954137c4db39b2ef9f85141b79fe3356b
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---

# Introduzione ai canali esterni personalizzati {#gs-custom-channel}

Adobe Campaign consente di creare canali esterni personalizzati integrati con terze parti. Puoi quindi orchestrare ed eseguire le consegne in base a questi canali.

La creazione e l’invio della consegna possono essere eseguiti sia nella console client che nell’interfaccia web. Tuttavia, il canale esterno personalizzato viene eseguito solo nella console client.

Per informazioni su come creare e inviare una consegna basata su un canale esterno personalizzato, consulta questa [pagina](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html).

Di seguito sono riportati i passaggi per creare un nuovo canale personalizzato esterno nella console client:

1. Configura lo schema, [ulteriori informazioni](#configure-schema)
1. Crea un nuovo account esterno, [ulteriori informazioni](#create-ext-account)
1. Crea un nuovo modello di consegna, [ulteriori informazioni](#create-template)

## Configurare lo schema{#configure-schema}

Innanzitutto, devi configurare lo schema per aggiungere il nuovo canale all’elenco dei canali disponibili.

1. Da Campaign Explorer, seleziona **Amministrazione** > **Configurazione** > **Schemi di dati**.

1. Crea un’estensione dello schema per estendere l’enumerazione messageType con il nuovo canale.

   Ad esempio:

   ```
   <enumeration basetype="byte" default="mail" label="Channel" name="messageType">
   <value desc="My Webpush" img="ncm:channels.png" label="My Webpush" name="webpush"
          value="122"/>
   </enumeration>
   ```

   ![](assets/cus-schema.png){zoomable="yes"}

## Crea un nuovo account esterno{#create-ext-account}

Quindi, devi creare un nuovo account esterno di indirizzamento.

1. Da Campaign Explorer, seleziona **Amministrazione** > **Piattaforma** > **Account esterni**.

1. Crea un nuovo account esterno.

1. Seleziona il canale e cambia la modalità di consegna in **External**.

   ![](assets/cus-ext-account.png){zoomable="yes"}

## Creare un nuovo modello di consegna{#create-template}

Ora creiamo il nuovo modello associato al nuovo canale.

1. Da Campaign Explorer, seleziona **Risorse** > **Modelli** > **Modelli di consegna**.

1. Crea un nuovo modello.

1. Fai clic su **Proprietà** e seleziona la cartella e il routing corretti.

   ![](assets/cus-template.png){zoomable="yes"}

Il nuovo canale è ora disponibile. Puoi creare ed eseguire consegne in base a questo canale.
