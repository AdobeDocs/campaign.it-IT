---
title: Aggiungere campi di personalizzazione
description: Scopri come inserire dati di personalizzazione nel contenuto del messaggio
feature: Personalization
role: User
level: Beginner
exl-id: 14a741dd-794e-4760-bfa3-bafbe993a3f7
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 4%

---

# Aggiungere campi di personalizzazione{#personalization-fields}

Utilizza i campi di personalizzazione per fornire contenuti personalizzati uno a uno, in base alle regole impostate per ogni destinatario.

Un campo di personalizzazione è un singolo riferimento a un campo dati utilizzato per personalizzare una consegna per un destinatario specifico. Il valore effettivo dei dati viene inserito durante la fase di analisi della consegna.

![esempio di personalizzazione del messaggio](assets/perso-name-sample.png)

## Sintassi

Un tag di personalizzazione utilizza sempre la sintassi seguente: `<%=table.field%>`.

Ad esempio, per inserire il nome del destinatario, memorizzato nella tabella dei destinatari, il campo di personalizzazione utilizza la sintassi `<%= recipient.lastName %>`.

>[!CAUTION]
>
>Il contenuto dei campi di personalizzazione non può superare i 1024 caratteri.

## Inserire un campo di personalizzazione {#insert-a-personalization-field}

Per inserire campi di personalizzazione, fai clic sull’icona a discesa accessibile da qualsiasi campo intestazione, oggetto o corpo del messaggio.

![inserisci un campo di personalizzazione](assets/perso-field-insert.png)

I campi di personalizzazione vengono inseriti e sono pronti per essere interpretati da Adobe Campaign: durante la preparazione dei messaggi, i campi vengono sostituiti dal loro valore per un determinato destinatario.

![campi di personalizzazione in un messaggio e-mail](assets/perso-fields-in-msg.png)

Questa sostituzione può quindi essere testata nella scheda **[!UICONTROL Preview]**.

<!--Learn more about message preview in [this page]().-->

## Caso d’uso: personalizzare l’oggetto dell’e-mail {#personalization-fields-uc}

Nel caso d’uso seguente, scopri come personalizzare un oggetto e un corpo dell’e-mail con i dati dei destinatari:

1. Crea una nuova consegna o apri una consegna e-mail esistente.
1. Passa al collegamento **[!UICONTROL Subject]** per modificare l&#39;oggetto del messaggio.
1. Immetti &quot; **Offerta speciale per**&quot; e utilizza il pulsante nella barra degli strumenti per inserire un campo di personalizzazione. Seleziona **[!UICONTROL Recipients>Title]**.
1. Ripetere l&#39;operazione per inserire il nome del destinatario. Inserisci spazi tra tutti i campi di personalizzazione.
1. Fai clic su **[!UICONTROL OK]** per confermare.
1. Inserisci la personalizzazione nel corpo del messaggio. A questo scopo, fai clic sul contenuto del messaggio e fai clic sul pulsante di inserimento del campo.
1. Seleziona **[!UICONTROL Recipient>Other...]**.
1. Selezionare il campo con le informazioni da visualizzare e fare clic su **[!UICONTROL OK]**.
1. Fare clic sulla scheda **[!UICONTROL Preview]** per visualizzare il risultato della personalizzazione. È necessario selezionare un destinatario per visualizzarne il messaggio.



## Video tutorial {#personalization-field-video}

Scopri come aggiungere un campo di personalizzazione alla riga dell’oggetto e il contenuto di una consegna e-mail nel video seguente.

>[!VIDEO](https://video.tv.adobe.com/v/24925?quality=12)
