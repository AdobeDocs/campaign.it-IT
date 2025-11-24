---
title: Parametri e-mail in Adobe Campaign
description: Scopri le opzioni e le impostazioni specifiche per la consegna delle e-mail in Adobe Campaign.
feature: Email
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: ad75f01e-2c6c-4607-b15a-8870d399002a
source-git-commit: 6b70ad987b828dc1c17bc4f0683046be4eff0408
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 8%

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

## Abilita annullamento iscrizione con un solo clic all’elenco {#one-click-list-unsubscribe}

L’URL per l’annullamento dell’iscrizione con un solo clic è un collegamento o un pulsante visualizzato accanto alle informazioni sul mittente dell’e-mail che consente ai destinatari di annullare immediatamente l’iscrizione alle mailing list con un solo clic. <!--[Learn more](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"}-->

Viene visualizzato come collegamento **Annulla sottoscrizione** nelle interfacce e-mail degli ISP. Ad esempio:

![](assets/email-list-unsubscribe-example.png)

L’aggiunta di un’intestazione SMTP denominata Annullamento iscrizione a mailing list è obbligatoria per garantire una gestione ottimale del recapito messaggi e può essere utilizzata in alternativa all’icona &quot;Report as SPAM&quot; (Report as SPAM). In effetti, l’utilizzo di questa funzionalità riduce la percentuale di reclami e contribuisce a proteggere la tua reputazione.

>[!IMPORTANT]
>
>Per visualizzare l’URL con un solo clic per l’annullamento dell’iscrizione nell’intestazione dell’e-mail, il client e-mail dei destinatari deve supportare questa funzione.

Per abilitare questa funzionalità, seleziona l&#39;opzione **[!UICONTROL Addition of One-click List-Unsubscription Header]** nella scheda **[!UICONTROL SMTP]** delle proprietà di consegna.

>[!NOTE]
>
>Questa opzione è abilitata per impostazione predefinita.

![](assets/email-smtp-list-unsubscribe.png)

<!--
>[!WARNING]
>
>If you uncheck this option in the delivery template, it will still be enabled by default in the deliveries created from this template. You need to enable the option again at the delivery level.-->

A seconda del client e-mail e del metodo utilizzato per eseguire la rinuncia, fare clic sul collegamento **Annulla iscrizione** nell&#39;intestazione e-mail può avere i seguenti effetti:

* Se il client di posta elettronica utilizza il metodo **One-Click** List-Unsubscribe, il destinatario viene direttamente escluso.

  >[!NOTE]
  >
  >Principali ISP come Google e Yahoo! richiede ai mittenti di rispettare **Annullamento iscrizione a mailing list con un solo clic**.

* Se il client di posta elettronica non supporta il metodo One-Click List-Unsubscribe, è comunque possibile utilizzare il metodo **&quot;mailto&quot;** List-Unsubscribe, che invia un&#39;e-mail precompilata all&#39;indirizzo di annullamento dell&#39;iscrizione specificato nell&#39;intestazione dell&#39;e-mail.

  È possibile impostare l&#39;indirizzo in modo esplicito nell&#39;intestazione o utilizzare un indirizzo dinamico, ad esempio utilizzando &lt;%=errorAddress%> o l&#39;opzione &#39;NmsEmail_DefaultErrorAddr&#39;, che può essere impostata tramite la procedura guidata di distribuzione.

>[!NOTE]
>
>È inoltre possibile impostare manualmente i metodi [Annullamento sottoscrizione a un solo clic](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#one-click-list-unsubscribe){target="_blank"} e [&quot;mailto&quot; Annullamento sottoscrizione a un elenco](https://experienceleague.adobe.com/en/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations?lang=en#mailto-list-unsubscribe){target="_blank"}. I passaggi dettagliati sono descritti nella [Guida alle best practice per il recapito messaggi](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/campaign/acc-technical-recommendations.html#list-unsubscribe){target="_blank"} di Experience Cloud.


## Aggiungi intestazioni SMTP {#adding-smtp-headers}

È possibile aggiungere intestazioni SMTP alle consegne. A questo scopo, utilizza la sezione pertinente della scheda **[!UICONTROL SMTP]** nella consegna.

Lo script immesso in questa finestra deve fare riferimento a un&#39;intestazione per riga nel seguente formato: **nome:value**.

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
