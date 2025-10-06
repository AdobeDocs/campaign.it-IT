---
title: Introduzione ai canali personalizzati
description: Scopri come creare e inviare consegne di canale personalizzate con Adobe Campaign Web
role: User
level: Beginner, Intermediate
exl-id: d2d92de6-3974-41c5-a0fd-09bbf6cf0020
source-git-commit: f75b95faa570d7c3f59fd8fb15692d3c3cbe0d36
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 2%

---

# Introduzione ai canali personalizzati {#gs-custom-channel}

Adobe Campaign consente di creare canali personalizzati esterni o API integrati con terze parti. Puoi quindi orchestrare ed eseguire le consegne in base a questi canali.

La creazione e l’invio della consegna possono essere eseguiti sia nella console client che nell’interfaccia web. Tuttavia, la configurazione del canale personalizzata viene eseguita solo nella console client.

Per informazioni su come creare e inviare una consegna basata su un canale personalizzato, consulta questa [pagina](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/gs-custom-channel.html?lang=it){target="_blank"}.

Di seguito sono riportati i passaggi per configurare un nuovo canale personalizzato nella console client. Questi passaggi sono comuni ai canali esterni e API personalizzati:

1. Configura lo schema, [ulteriori informazioni](#configure-schema)
1. Crea un nuovo account esterno, [ulteriori informazioni](#create-ext-account)
1. Crea un nuovo modello di consegna, [ulteriori informazioni](#create-template)

I canali API personalizzati richiedono una configurazione aggiuntiva. [Ulteriori informazioni](#api-additional)

## Configurare lo schema{#configure-schema}

Innanzitutto, devi configurare lo schema per aggiungere il nuovo canale all’elenco dei canali disponibili.

1. Da Campaign Explorer, seleziona **Amministrazione** > **Configurazione** > **Schemi di dati**.

1. Crea un&#39;estensione dello schema per estendere **messageType** [enumeration](../config/enumerations.md) con il nuovo canale.

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

1. Seleziona il canale e cambia la modalità di consegna. Scegli **External** per i canali esterni personalizzati e **Bulk** per i canali API personalizzati.

   ![](assets/cus-ext-account.png){zoomable="yes"}

## Creare un nuovo modello di consegna{#create-template}

Ora creiamo il nuovo modello associato al nuovo canale.

1. Da Campaign Explorer, seleziona **Risorse** > **Modelli** > **Modelli di consegna**.

1. Crea un nuovo modello.

1. Fai clic su **Proprietà** e seleziona la cartella e il routing corretti.

   ![](assets/cus-template.png){zoomable="yes"}

Il nuovo canale è ora disponibile. Puoi creare ed eseguire consegne in base a questo canale.

## Configurazione aggiuntiva API personalizzata{#api-additional}

Di seguito sono riportati i passaggi aggiuntivi principali per configurare i canali API personalizzati.

### Estendere lo schema{#api-additional-schema}

Dalla console client, estendere lo schema **Delivery** con tutte le proprietà aggiuntive necessarie per il canale personalizzato.

Per ulteriori informazioni sull&#39;estensione dello schema, consulta questa [pagina](../dev/extend-schema.md).

### Impostare la definizione dello schermo personalizzato{#api-additional-screen}

Dall’interfaccia web di Campaign, imposta la definizione della schermata personalizzata:

1. Apri lo schema **Delivery** e fai clic su **Screen edition**.

   ![](assets/cus-schema2.png){zoomable="yes"}

1. Seleziona la scheda che corrisponde al canale e definisci come verranno visualizzati i campi nella schermata del contenuto della consegna. Per ulteriori informazioni sull&#39;edizione dello schermo, consulta questa [pagina](https://experienceleague.adobe.com/docs/campaign-web/v8/conf/schemas.html?lang=it#fields){target="_blank"}.

   ![](assets/cus-schema3.png){zoomable="yes"}

1. Nella sezione **Anteprima per simulare il contenuto**, seleziona il JSPP dedicato. Questo è facoltativo. L’anteprima viene attivata nella schermata di simulazione della consegna. [Ulteriori informazioni](#api-additional-preview)

### Configurare l’anteprima{#api-additional-preview}

Questa configurazione è facoltativa. Se desideri attivare l’anteprima nell’interfaccia utente web, nella schermata di simulazione della consegna devi configurare un JSSP dedicato nella console client.

Quando fai clic su **Apri anteprima** nella schermata di simulazione della consegna nell&#39;interfaccia utente Web, i seguenti parametri vengono passati nell&#39;URL:

`https://adobe.campaign.adobe.com/cus/webPushMessagePreview.jssp?deliveryId=%40ToPzTurO9aGzQxYcMArBbA%3D%3D&id=%40oF8Fi17txuLmtiOFj4OIjQ%3D%3D`

* `deliveryId`: identificatore della consegna
* `id`: identificatore del profilo

Nella console client, selezionare **Amministrazione** > **Configurazione** > **Pagine JavaScript dinamiche** e creare un nuovo JSSP. Ecco un esempio con i parametri che devono essere recuperati.

```
<%@ page import="xtk:shared/nl.js"
%><%
  NL.require("/nl/core/shared/core.js")
    .require('/nl/core/jsspcontext.js')
    .require('/nl/core/shared/dataTypes.js')
    .require('/nl/core/schema.js');
    
  //response.setContentType("text/plain");
  var parameters = request.parameters;
  var deliveryId = decryptString(parameters.deliveryId);
  var oldUserContext = logonEscalation("neolane")
  
   var delivery = xtk.queryDef.create(<queryDef schema="nms:delivery" operation="getIfExists">
                                         <select>
                                           <node expr="[WebpushParameters/@richMediaOptions]" alias="@richMediaOptions"/>
                                           <node expr="[WebpushParameters/@mediaUrlInfo]" alias="@mediaUrlInfo"/>
                                           <node expr="[WebpushParameters/@WebpushMessageType]"/>
                                         </select>
                                         <where>
                                           <condition expr={"@id = " + NL.XTK.toXTKString(deliveryId)}/>
                                         </where>
                                       </queryDef>).ExecuteQuery();

  // Restore previous context
  logonWithContext(oldUserContext)
%>

<!DOCTYPE html ...
```

### Implementazione tecnica{#api-additional-technical}

A seconda del canale personalizzato, dovrai configurare altre parti dell’applicazione, ad esempio: account esterni, mappatura del target, codice JavaScript per API e così via.

