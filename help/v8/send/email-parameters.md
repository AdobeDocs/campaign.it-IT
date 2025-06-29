---
title: Parametri e-mail in Adobe Campaign
description: Scopri le opzioni e le impostazioni specifiche per la consegna delle e-mail in Adobe Campaign.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 10%

---

# Parametri e-mail {#email-parameters}

Questa sezione presenta le opzioni e i parametri disponibili nelle proprietà di consegna specifiche per la consegna e-mail.

## Usa Ccn e-mail {#email-bcc}

Puoi configurare Adobe Campaign per conservare una copia delle e-mail inviate dalla tua piattaforma. Questa opzione è descritta in [questa pagina](email-bcc.md).

## Seleziona i formati dei messaggi {#selecting-message-formats}

Puoi modificare il formato dei messaggi e-mail inviati. A tale scopo, modificare le proprietà di consegna e fare clic sulla scheda **[!UICONTROL Delivery]**.

![](assets/email-message-format.png)

Seleziona il formato dell’e-mail nella sezione inferiore della finestra:

* **[!UICONTROL Use recipient preferences]** (modalità predefinita)

  Il formato del messaggio è definito in base ai dati memorizzati nel profilo del destinatario e archiviato per impostazione predefinita nel campo **[!UICONTROL email format]** (@emailFormat). Se un destinatario desidera ricevere i messaggi in un determinato formato, questo sarà il formato inviato. Se il campo non è compilato, viene inviato un messaggio multipart-alternative (vedi sotto).

* **[!UICONTROL Let recipient mail client choose the most appropriate format]**

  Il messaggio contiene entrambi i formati: testo e HTML. Il formato visualizzato sulla ricezione dipende dalla configurazione del software di posta del destinatario (multipart-alternative).

  >[!IMPORTANT]
  >
  >Questa opzione include entrambe le versioni del documento. Di conseguenza, riduce la velocità effettiva di consegna, perché la dimensione del messaggio è maggiore.

* **[!UICONTROL Send all messages in text format]**

  Il messaggio viene inviato in formato testo. Il formato HTML non verrà inviato, ma utilizzato per la pagina speculare solo quando il destinatario fa clic sul messaggio.

<!--
>[!NOTE]
>
>For more on defining the email content, see [this section]().-->

## Imposta codifica caratteri {#character-encoding}

Nella scheda **[!UICONTROL SMTP]** dei parametri di consegna, la sezione **[!UICONTROL Character encoding]** ti consente di impostare una codifica specifica.

La codifica predefinita è UTF-8. Se alcuni provider di posta elettronica dei destinatari non supportano la codifica standard UTF-8, è possibile impostare una codifica specifica per visualizzare correttamente i caratteri speciali per i destinatari delle e-mail.

Ad esempio, desideri inviare un’e-mail contenente caratteri giapponesi. Per garantire che tutti i caratteri vengano visualizzati correttamente ai destinatari in Giappone, è possibile utilizzare una codifica che supporti i caratteri giapponesi anziché il formato UTF-8 standard.

A tale scopo, selezionare l&#39;opzione **[!UICONTROL Force the encoding used for messages]** nella sezione **[!UICONTROL Character encoding]** e scegliere una codifica dall&#39;elenco a discesa visualizzato.

![](assets/email-smtp-encoding.png)

## Gestire le e-mail non recapitate {#managing-bounce-emails}

La scheda **[!UICONTROL SMTP]** delle proprietà di consegna consente inoltre di configurare la gestione dei messaggi non recapitati.

* **[!UICONTROL Errors-to-address]**: per impostazione predefinita, le e-mail non consegnate vengono ricevute nella casella di errore predefinita della piattaforma, ma puoi definire un indirizzo di errore specifico per una consegna.

* **[!UICONTROL Bounce address]**: È inoltre possibile definire un altro indirizzo al quale vengono inoltrate le e-mail non elaborate non recapitate. Questo indirizzo consente di indagare i motivi di mancato recapito quando le e-mail non potevano essere qualificate automaticamente dall’applicazione.

Ognuno di questi campi può essere personalizzato utilizzando l’icona dedicata. Ulteriori informazioni sui campi di personalizzazione in [questa sezione](personalization-fields.md).

![](assets/email-smtp-bounce.png)

Per ulteriori informazioni sulla gestione della posta non recapitata, consulta [questa sezione](delivery-failures.md#bounce-mail-management).

## Aggiungi intestazioni SMTP {#adding-smtp-headers}

È possibile aggiungere intestazioni SMTP alle consegne. A questo scopo, utilizza la sezione pertinente della scheda **[!UICONTROL SMTP]** nella consegna.

Lo script immesso in questa finestra deve fare riferimento a un&#39;intestazione per riga nel seguente formato: **nome:valore**.

Se necessario, i valori vengono codificati automaticamente.

>[!IMPORTANT]
>
>L’aggiunta di uno script per l’inserimento di intestazioni SMTP aggiuntive è riservata agli utenti avanzati.
>
>La sintassi di questo script deve essere conforme ai requisiti di questo tipo di contenuto: nessuno spazio inutilizzato, nessuna linea vuota e così via.

![](assets/email-smtp-headers.png)


## Genera pagina mirror {#generating-mirror-page}

La pagina mirror è una pagina HTML accessibile online tramite un browser web. Il contenuto è identico a quello dell’e-mail. Può essere utile se i destinatari riscontrano problemi di rendering o immagini danneggiate quando tentano di visualizzare l’e-mail nella casella in entrata.

Scopri come inserire un collegamento alla pagina mirror in [questa sezione](mirror-page.md)
