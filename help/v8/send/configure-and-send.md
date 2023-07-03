---
title: Configurare le e-mail con Adobe Campaign
description: Scopri come configurare le e-mail in Adobe Campaign.
feature: Email
role: User
level: Beginner
source-git-commit: 44f30f753e3ed75b7e56caf7bd8cdfa7cbee5c35
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 7%

---

# Configurare e inviare la consegna {#configure-delivery}

## Imposta parametri aggiuntivi {#delivery-additional-parameters}

Prima di inviare la consegna, puoi definirne i parametri nelle relative proprietà tramite **[!UICONTROL Delivery]** scheda.

![](assets/delivery-properties-delivery.png)

* **[!UICONTROL Delivery priority]**: utilizza questa opzione per modificare l’ordine di invio delle consegne impostandone il livello di priorità, da **[!UICONTROL Very low]** a **[!UICONTROL Very high]** (il valore predefinito è **[!UICONTROL Normal]**).

* **[!UICONTROL Message batch quantity]**: utilizza questa opzione per definire il numero di messaggi raggruppati nello stesso pacchetto di consegna XML. Se il parametro è impostato su 0, i messaggi vengono raggruppati automaticamente. La dimensione del pacchetto è definita dal calcolo `<delivery size>/1024`, con un minimo di 8 e un massimo di 256 messaggi per pacchetto.

  >[!IMPORTANT]
  >
  >Quando la consegna viene creata duplicandone una esistente, questo parametro viene reimpostato.

* **[!UICONTROL Send using multiple waves]**: utilizza questa opzione per inviare i messaggi in batch anziché all’intero pubblico contemporaneamente. [Ulteriori informazioni](#sending-using-multiple-waves).

* **[!UICONTROL Test SMTP delivery]**: utilizza questa opzione per verificare l’invio tramite SMTP. La consegna viene elaborata fino alla connessione al server SMTP, ma non viene inviata: per ogni destinatario della consegna, Campaign si connette al server del provider SMTP, esegue il comando SMTP RCPT TO e chiude la connessione prima del comando SMTP DATA.

  >[!NOTE]
  >
  >* Questa opzione non deve essere impostata nel mid-sourcing.
  >
  >* Ulteriori informazioni sulla configurazione del server SMTP in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/additional-configurations/configure-delivery-settings.html#smtp-relay){target="_blank"}.

* **[!UICONTROL Email BCC]**: utilizza questa opzione per memorizzare le e-mail su un sistema esterno tramite Ccn semplicemente aggiungendo un indirizzo e-mail Ccn alla destinazione del messaggio. [Ulteriori informazioni](email-parameters.md).

## Invia in più scaglioni {#sending-using-multiple-waves}

Per bilanciare il carico, puoi dividere le consegne in più batch. Configura il numero di batch e la loro proporzione rispetto all’intera consegna.

>[!NOTE]
>
>Puoi definire solo la dimensione e il ritardo tra due scaglioni consecutivi. Non è possibile configurare i criteri di selezione dei destinatari per ogni ondata.

1. Apri la finestra delle proprietà di consegna e fai clic su **[!UICONTROL Delivery]** scheda.
1. Seleziona la **[!UICONTROL Send using multiple waves]** e fare clic sul pulsante **[!UICONTROL Define waves...]** collegamento.

   ![](assets/delivery-define-waves.png)

1. Per configurare le ondate, puoi effettuare le seguenti operazioni:

   * Definite le dimensioni per ogni scaglione. Ad esempio, se si immette **[!UICONTROL 30%]** nel campo corrispondente, ogni ondata rappresenterà il 30% dei messaggi inclusi nella consegna, ad eccezione dell’ultimo, che rappresenterà il 10% dei messaggi.

     In **[!UICONTROL Period]** , specificare il ritardo tra l&#39;inizio di due scaglioni consecutivi. Ad esempio, se si immette **[!UICONTROL 2d]**, la prima ondata comincerà immediatamente, la seconda fra due giorni, la terza fra quattro giorni e così via.

     ![](assets/delivery-waves-size.png)

   * Definisci un calendario per l&#39;invio di ogni scaglione.

     In **[!UICONTROL Start]** , specificare il ritardo tra l&#39;inizio di due ondate consecutive. In **[!UICONTROL Size]** , immettere un numero fisso o una percentuale.

     Nell’esempio seguente, la prima ondata rappresenta il 25% del numero totale di messaggi inclusi nella consegna e inizierà immediatamente. Le due fasi successive completano la consegna e sono impostate per iniziare a intervalli di sei ore.

     ![](assets/delivery-waves-calendar.png)

   Una regola di tipologia specifica, **[!UICONTROL Wave scheduling check]**, assicura che l’ultimo scaglione sia pianificato prima del limite di validità della consegna. Le tipologie di campagne e le relative regole, configurate in **[!UICONTROL Typology]** delle proprietà di consegna, sono presentate in [questa sezione](../../automation/campaign-opt/campaign-typologies.md#typology-rules)<!--ref TBC-->.

   >[!IMPORTANT]
   >
   >Assicurati che gli ultimi scaglioni non superino la scadenza di consegna, definita nella sezione **[!UICONTROL Validity]** scheda. In caso contrario, alcuni messaggi potrebbero non essere inviati.
   >
   >È inoltre necessario concedere tempo sufficiente per i nuovi tentativi durante la configurazione degli ultimi scaglioni. <!--See [this section]().-->

1. Per monitorare gli invii, passa ai registri di consegna. Consulta [questa pagina](send.md)<!--ref TBC-->.

   Puoi visualizzare le consegne già inviate negli scaglioni elaborati (**[!UICONTROL Sent]** stato) e le consegne da inviare negli scaglioni rimanenti (**[!UICONTROL Pending]** stato).

I due esempi seguenti sono i casi d’uso più comuni per l’utilizzo di più scaglioni.

* **Durante il processo di incremento**

  Quando le e-mail vengono inviate utilizzando una nuova piattaforma, i provider di servizi Internet (ISP) sospettano che gli indirizzi IP non siano riconosciuti. Se grandi quantità di e-mail vengono inviate improvvisamente, gli ISP spesso le contrassegnano come spam.

  Per evitare di essere contrassegnati come spam, puoi aumentare progressivamente il volume inviato scaglionando. Ciò dovrebbe garantire un regolare sviluppo della fase di avvio e consentirti di ridurre il tasso complessivo di indirizzi non validi.

  A tale scopo, utilizza **[!UICONTROL Schedule waves according to a calendar]** opzione. Ad esempio, imposta la prima ondata su 10%, la seconda su 15% e così via.

  ![](assets/delivery-waves-ex-ramp-up.png)

* **Campagne che coinvolgono un call center**

  Quando gestisci una campagna fedeltà telefonica, la tua organizzazione ha una capacità limitata di elaborare il numero di chiamate per contattare gli abbonati.

  Utilizzando le ondate, è possibile limitare il numero di messaggi a 20 al giorno, che rappresenta la capacità di elaborazione giornaliera di un call center.

  A questo scopo, seleziona la **[!UICONTROL Schedule multiple waves of the same size]** opzione. Invio **[!UICONTROL 20]** come la dimensione dell&#39;onda e **[!UICONTROL 1d]** nel **[!UICONTROL Period]** campo.

  ![](assets/delivery-waves-ex-call-center.png)

<!--
## Adjust delivery failure management {#delivery-failure-management}

### Configure retries {#configure-retries}

Temporarily undelivered messages due to a **Soft** or **Ignored** error are subject to an automatic retry. The delivery failure types and reasons are presented in this [section](../../delivery/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

>[!IMPORTANT]
>
>For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the retry settings in the delivery are no longer used by Campaign. Soft bounce retries and the length of time between them are determined by the Enhanced MTA based on the type and severity of the bounce responses coming back from the message's email domain.

For on-premise installations and hosted/hybrid installations using the legacy Campaign MTA, the central section of the **[!UICONTROL Delivery]** tab for delivery parameters indicates how many retries should be performed the day after the delivery and the minimum delay between retries.

![](assets/s_ncs_user_wizard_retry_param.png)

By default, five retries are scheduled for the first day of the delivery with a minimum interval of one hour spread out over the 24 hours of the day. One retry per day is programmed after that and until the delivery deadline, which is defined in the **[!UICONTROL Validity]** tab (see [Defining validity period](#defining-validity-period)).

### Define the validity period {#define-validity-period}

When the delivery has been launched, the messages (and any retries) can be sent until the delivery deadline. This is indicated in the delivery properties, via the **[!UICONTROL Validity]** tab.

![](assets/s_ncs_user_email_del_valid_period.png)

* The **[!UICONTROL Delivery duration]** field lets you enter the limit for global delivery retries. This means that Adobe Campaign sends the messages beginning on the start date, and then, for messages returning an error only, regular, configurable retries are performed until the validity limit is reached.

  You can also choose to specify dates. To do this, select **[!UICONTROL Explicitly set validity dates]**. In this case, the delivery and validity limit dates also let you specify the time. The current time is used by default, but you can modify this directly in the input field.

  >[!IMPORTANT]
  >
  >For hosted or hybrid installations, if you have upgraded to the [Enhanced MTA](../../delivery/using/sending-with-enhanced-mta.md), the **[!UICONTROL Delivery duration]** setting in your Campaign email deliveries will be used only if set to **3.5 days or less**. If you define a value higher than 3.5 days, it will not be taken into account.

* **Validity limit of resources**: The **[!UICONTROL Validity limit]** field is used for uploaded resources, mainly for the mirror page and images. The resources on this page are valid for a limited time (to save disk space).

  The values in this field can be expressed in the units listed in [this section](../../platform/using/adobe-campaign-workspace.md#default-units).

## Confirm the delivery {#confirm-delivery}

When the delivery is configured and ready to be sent, make sure you have run the delivery analysis.

To do this, click **[!UICONTROL Send]**, select the desired action and click **[!UICONTROL Analyze]**. For more on this, see [Launching the analysis](../../delivery/using/steps-validating-the-delivery.md#analyzing-the-delivery).

![](assets/s_ncs_user_email_del_send.png)

Once done, click **[!UICONTROL Confirm delivery]** to launch the delivery of messages.

You can then close the delivery wizard and track the execution of the delivery from the **[!UICONTROL Delivery]** tab, accessible via the detail of this delivery or via the list of deliveries.

After sending messages, you can monitor and track your deliveries. For more on this, refer to these sections:

* [Monitoring a delivery](send.md)
* [Understanding delivery failures](delivery-failures.md)
* [About message tracking]

## Schedule the delivery sending {#schedule-delivery-sending}

You can defer the delivery of messages in order to schedule the delivery or to manage sales pressure and avoid over-soliciting a population.

1. Click the **[!UICONTROL Send]** button and select the **[!UICONTROL Postpone delivery]** option.

1. Specify a start date in the **[!UICONTROL Contact date]** field.

  ![](assets/)

1. You can then start the delivery analysis, then confirm the delivery sending. However, the delivery sending will not start until the date given in the **[!UICONTROL Contact date]** field.

  >[!IMPORTANT]
  >
  >Once you have started the analysis, the contact date that you defined is fixed. If you modify this date, you will have to restart the analysis so that your modifications are taken into account.

  ![](assets/)

In the delivery list, the delivery will appear with **[!UICONTROL Pending]** status.

![](assets/send-schedule-pending-status.png)

Scheduling can also be configured upstream via the **[!UICONTROL Scheduling]** button of the delivery.

![](assets/send-scheduling-button.png)

It lets you defer the delivery to a later date or save the delivery in the provisional calendar.

* The **[!UICONTROL Schedule delivery (no automatic execution)]** option lets you schedule a provisional analysis of the delivery.

  When this configuration is saved, the delivery changes to **[!UICONTROL Targeting pending]** status. The analysis will be launched on the specified date.

* The **[!UICONTROL Schedule delivery (automatic execution on planned date)]** option lets you specify the delivery date.

  Click **[!UICONTROL Send]** and select **[!UICONTROL Postpone delivery]** then launch the analysis and confirm delivery. When the analysis is complete, the delivery target is ready and messages will automatically be sent on the specified date.

Dates and times are expressed in the time zone of the current operator. The **[!UICONTROL Time zone]** drop-down list located below the contact date input field lets you automatically convert the entered date and time into the selected time zone.

For instance, if you schedule a delivery to be executed automatically at 8 o'clock London time, the time is automatically converted into the selected time zone:

![](assets/send-schedule-time-zone.png)

-->