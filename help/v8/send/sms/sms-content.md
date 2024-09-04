---
title: Gli SMS definiscono il contenuto
description: Scopri come impostare il contenuto di una consegna SMS
feature: SMS
role: User
level: Beginner, Intermediate
badge: label="Disponibilità limitata" type="Informative"
source-git-commit: a184a29301f2bd739bc3fd1373fc8cfad58f0393
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 1%

---


# Contenuto SMS {#sms-content}

Per configurare il contenuto della consegna SMS:

1. Immettere il contenuto del messaggio nella procedura guidata **[!UICONTROL Text content]**

   ![](assets/sms_content.png){zoomable="yes"}

1. Puoi personalizzare il messaggio inserendo campi di personalizzazione (ad esempio, aggiungendo il nome) o blocchi di personalizzazione predefiniti (ad esempio, aggiungendo i saluti). Puoi fare clic sul pulsante di personalizzazione per aggiungere questi:

   ![](assets/sms_perso.png){zoomable="yes"}

   Dopo aver fatto clic su **[!UICONTROL Recipient]** > **[!UICONTROL First name]**, la personalizzazione sarà simile alla seguente:

   ![](assets/sms_perso_recipient.png){zoomable="yes"}

1. Per visualizzare l&#39;anteprima della consegna, andare nella scheda **[!UICONTROL Preview]**, fare clic sull&#39;elenco a discesa **[!UICONTROL Test personalization]** e scegliere un destinatario nella tabella **[!UICONTROL Recipient]**.

   ![](assets/sms_preview.png){zoomable="yes"}

   Avrai l’anteprima del tuo SMS con la personalizzazione:

   ![](assets/sms_preview_phone.png){zoomable="yes"}

>[!NOTE]
>
>* I messaggi SMS sono limitati a una lunghezza di 160 caratteri se viene utilizzata la tabella codici Latin-1 (ISO-8859-1). Se il messaggio è scritto in Unicode, non deve superare i 70 caratteri. Alcuni caratteri speciali possono influenzare la lunghezza del messaggio. Per ulteriori informazioni sulla lunghezza del messaggio, consulta la sezione [Traslitterazione caratteri SMS](smpp-external-account.md#smpp-channel-settings).
>
>* Quando sono presenti campi di personalizzazione o campi di contenuto condizionale, la dimensione del messaggio varia da un destinatario all’altro. La lunghezza del messaggio deve essere valutata una volta eseguita la personalizzazione.
>
>*Quando si avvia l&#39;analisi, viene controllata la lunghezza dei messaggi e viene visualizzato un avviso in caso di overflow.

Dopo aver creato il contenuto della consegna, puoi [selezionare il pubblico](sms-audience.md).