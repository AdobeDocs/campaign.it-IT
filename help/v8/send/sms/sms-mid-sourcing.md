---
title: SMS in un’infrastruttura mid-sourcing
description: Scopri come configurare una consegna SMS in un’infrastruttura mid-sourcing
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: b5eb9eaa-0ca8-478c-9ed5-e5006e9b5609
TQID: 'https://experienceleague.adobe.com/JMj3tFG6i-bWXlEGyvFzlNpAj4fZoqZC4mdej5N3Qcw'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: c4f3ffbf421621fa15b1b4d56480bd0ff9304254
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 0%
---
# SMS in un’infrastruttura mid-sourcing {#sms-mid}

L’invio di consegne SMS con un’infrastruttura mid-sourcing richiede:

1. Un operatore SMS sul mid-server. [Scopri come crearlo qui](#sms-operator-mid)
1. Un account esterno SMS sul server Marketing che utilizzerà l’operatore creato in precedenza. [Scopri come crearlo qui](#sms-external-account)
1. Un account esterno SMPP sul server Mid, che specifica la modalità di consegna Canale e Mid-sourcing. [Scopri come crearlo qui](#smpp-external-account-mid)
1. Un modello di consegna che fa riferimento all’account esterno per semplificare il processo di invio. [Scopri come crearlo qui](#sms-delivery-template)

## Creare l’operatore SMS sul server mid {#sms-operator-mid}

Innanzitutto, devi creare un operatore SMS sul Mid-server, che verrà utilizzato dall’account esterno SMS sul server di marketing.

Per creare il tuo operatore SMS, segui i passaggi seguenti:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Access management]** > **[!UICONTROL Operators]**, fai clic su **[!UICONTROL New]** e compila il modulo nella nuova finestra aperta.

   * **[!UICONTROL Name (login)]** e **[!UICONTROL Label]** sono obbligatori.
   * La password non è obbligatoria, ma è altamente consigliata per la sicurezza.

   In seguito verrà utilizzato il nome (accesso) per denominare l’account esterno SMPP nel mid-server.

   ![Nuovo modulo per l&#39;operatore SMS sul server mid con nome (accesso), password ed etichetta e il pulsante Aggiungi per i diritti](assets/smsoperator_mid.png){zoomable="yes"}

1. Nella parte **[!UICONTROL Groups and named rights]**, fare clic sul pulsante **[!UICONTROL Add]**.
Nella nuova finestra aperta, scegliere **[!UICONTROL Named rights]** nell&#39;elenco **[!UICONTROL Folder]** e selezionare **[!UICONTROL ADMINISTRATION]** nell&#39;elenco a destra.

1. Fare clic sul pulsante **[!UICONTROL Ok]**.

   ![Finestra di dialogo per l&#39;aggiunta di gruppi o diritti denominati con l&#39;opzione Amministrazione denominata selezionata](assets/smsoperator_rights.png){zoomable="yes"}

1. Fai clic sul pulsante **[!UICONTROL Save]** per finalizzare la creazione dell&#39;operatore SMS.

   ![Modulo per l&#39;operatore SMS con aggiunta del diritto ADMINISTRATION ed evidenziazione del pulsante Save](assets/smsoperator_save.png){zoomable="yes"}

Ora è possibile visualizzarlo nell&#39;elenco degli operatori.

![Elenco operatori che mostra il nuovo operatore sms mid (smsOperator)](assets/smsoperator_list.png){zoomable="yes"}

## Creare un account esterno SMS sul server di marketing {#sms-external-account}

In un’infrastruttura mid, devi creare un account SMS esterno sul server Marketing come indicato di seguito

>[!IMPORTANT]
>
>L’utilizzo dello stesso account e della stessa password per più account SMS esterni può causare conflitti e sovrapposizioni tra gli account. Ulteriori informazioni sulla [pagina per la risoluzione dei problemi SMS](smpp-connection.md#sms-troubleshooting).

1. In **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]**, fare clic sull&#39;icona **[!UICONTROL New]**

   ![Elenco account esterni in Amministrazione > Piattaforma con l&#39;icona Nuovo evidenziata](assets/sms_extaccount.png){zoomable="yes"}

1. Configura **[!UICONTROL Label]** e **[!UICONTROL Internal name]** dell&#39;account esterno. Definisci il tipo di account come **[!UICONTROL Routing]**, seleziona la casella **[!UICONTROL Enabled]**, seleziona **[!UICONTROL Mobile (SMS)]** per il canale e **[!UICONTROL Mid-sourcing]** per la modalità di consegna.

   ![Scheda Generale account esterno: tipo di routing, abilitato, canale mobile (SMS) e modalità di consegna mid-sourcing](assets/mid_smsextaccount.png){zoomable="yes"}

1. Nella scheda **[!UICONTROL Mid-sourcing]**, compila il modulo con l’URL del server di mid-sourcing e l’operatore SMS creato in precedenza sul server mid.

   Confermare la connessione facendo clic sul pulsante **[!UICONTROL Test the connection]**.

   ![Scheda mid-sourcing con URL del server, account dell&#39;operatore SMS, password e pulsante Prova connessione](assets/midtab_smsextaccount.png){zoomable="yes"}

1. Fai clic su **[!UICONTROL Save]**.

## Creare un account esterno SMPP sul mid-server {#smpp-external-account-mid}

>[!IMPORTANT]
>
>L’utilizzo dello stesso account e della stessa password per più account SMS esterni può causare conflitti e sovrapposizioni tra gli account. Consulta la [pagina per la risoluzione dei problemi SMS](smpp-connection.md#sms-troubleshooting).

L’obiettivo ora è stabilire l’account esterno SMPP sul mid-server.

A questo scopo, segui la procedura indicata di seguito:

1. In **[!UICONTROL Administration]** > **[!UICONTROL Platform]** > **[!UICONTROL External Accounts]** del Mid-server, fai clic sull&#39;icona **[!UICONTROL New]**

1. Configura **[!UICONTROL Label]** e **[!UICONTROL Internal name]** dell&#39;account esterno.

   >[!WARNING]
   >
   >Quando si assegna un nome interno, assicurarsi di seguire la convenzione di denominazione specificata: `SMS Operator Name_Internal Name of the Marketing SMS external account`.
   >

   Definisci il tipo di account come **[!UICONTROL Routing]**, seleziona la casella **[!UICONTROL Enabled]**, seleziona **[!UICONTROL Mobile (SMS)]** per il canale e **[!UICONTROL Bulk delivery]** per la modalità di consegna.
   ![Scheda Generale dell&#39;account esterno mid-server: tipo di routing, abilitato, canale mobile (SMS) e modalità di consegna in blocco](assets/mid_extaccount.png){zoomable="yes"}

1. Nella scheda **[!UICONTROL Mobile]**, mantenere **[!UICONTROL Extended generic SMPP]** nell&#39;elenco a discesa **[!UICONTROL Connector]**.

   La casella **[!UICONTROL Send messages through a dedicated process]** è selezionata per impostazione predefinita.

   ![Scheda Mobile con il connettore SMPP generico esteso e invio di messaggi tramite un processo dedicato selezionato](assets/sms_extaccount_connector.png){zoomable="yes"}

   Per impostare la connessione, è necessario compilare le schede di questo modulo. Per ulteriori informazioni sull&#39;account esterno SMPP[&#128279;](smpp-external-account.md#smpp-connection-settings), vedere .

## Configurare il modello di consegna {#sms-delivery-template}

Per facilitare la creazione della consegna SMS, crea un modello di consegna SMS in cui si fa riferimento a tutte le impostazioni.

In **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** sul server Marketing, fare clic con il pulsante destro del mouse sul modello di consegna Mobile esistente e scegliere **[!UICONTROL Duplicate]**.

![Elenco modelli di consegna con duplicato selezionato nel menu di scelta rapida per il modello Mobile (SMS)](assets/sms_template_duplicate.png){zoomable="yes"}

Modifica **[!UICONTROL Label]** e **[!UICONTROL Internal name]** del modello per riconoscerlo facilmente e fai clic sul pulsante **[!UICONTROL Properties]**.

![Modello di consegna duplicato con i campi Etichetta e Nome interno ed evidenziato il pulsante Proprietà](assets/sms_template_name.png){zoomable="yes"}

Nella scheda **[!UICONTROL General]**, in **[!UICONTROL Routing]**, seleziona l’account esterno SMPP.

![Scheda Generale delle proprietà di consegna con il campo Indirizzamento impostato sull&#39;account esterno SMPP](assets/mid_template.png){zoomable="yes"}

Nella scheda **[!UICONTROL SMS]** è possibile aggiungere parametri facoltativi al modello.

![Scheda SMS delle proprietà di consegna con parametri generali e parametri SMPP (TLV) facoltativi](assets/sms_template_properties.png){zoomable="yes"}

[Ulteriori informazioni sulla configurazione della scheda SMS](sms-delivery-settings.md).
