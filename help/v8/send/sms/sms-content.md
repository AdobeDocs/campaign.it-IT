---
title: Definire e personalizzare il contenuto degli SMS
description: Scopri come definire e personalizzare il contenuto di una consegna SMS
feature: SMS
role: User
level: Beginner, Intermediate
version: Campaign v8, Campaign Classic v7
exl-id: 71d9376c-86e8-41ec-92dc-863455d40c7a
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 1%

---

# Definire il contenuto dell’SMS {#sms-content}

Per configurare il contenuto della consegna SMS:

1. Immettere il contenuto del messaggio nella scheda **[!UICONTROL Text content]**.

   ![](assets/sms_content.png){zoomable="yes"}

1. Puoi personalizzare il messaggio inserendo campi di personalizzazione (ad esempio, aggiungendo il nome) o blocchi di personalizzazione predefiniti (ad esempio, aggiungendo i saluti). Fai clic sul pulsante di personalizzazione per aggiungere questi:

   ![](assets/sms_perso.png){zoomable="yes"}

   Ad esempio, dopo aver fatto clic su **[!UICONTROL Recipient]** > **[!UICONTROL First name]**, il contenuto dell&#39;SMS viene aggiornato con il campo di personalizzazione, come segue:

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

   Ulteriori informazioni sulla personalizzazione in Adobe Campaign in [questa sezione](../personalize.md).

1. È possibile visualizzare in anteprima il contenuto della consegna dalla scheda **[!UICONTROL Preview]**. Per verificare le impostazioni di personalizzazione, fare clic sull&#39;elenco a discesa **[!UICONTROL Test personalization]** e selezionare un destinatario.

   ![](assets/sms_preview.png){zoomable="yes"}

   Puoi controllare l’anteprima del tuo SMS con la personalizzazione:

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* I messaggi SMS sono limitati a una lunghezza di 160 caratteri se viene utilizzata la tabella codici Latin-1 (ISO-8859-1). Se il messaggio è scritto in Unicode, non deve superare i 70 caratteri. Alcuni caratteri speciali possono influenzare la lunghezza del messaggio. Per ulteriori informazioni sulla lunghezza del messaggio, consulta la sezione [Traslitterazione caratteri SMS](smpp-external-account.md#smpp-channel-settings).
>
>* Quando sono presenti campi di personalizzazione o campi di contenuto condizionale, la dimensione del messaggio varia da un destinatario all’altro. La lunghezza del messaggio deve essere valutata una volta eseguita la personalizzazione.
>
>*Quando si avvia l&#39;analisi, viene controllata la lunghezza dei messaggi e viene visualizzato un avviso in caso di overflow.

Dopo aver creato il contenuto della consegna, puoi [selezionare il pubblico](sms-audience.md).
