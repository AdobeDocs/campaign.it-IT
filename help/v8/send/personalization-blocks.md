---
title: Utilizzare i blocchi di personalizzazione
description: Scopri come utilizzare i blocchi di personalizzazione incorporati nel contenuto del messaggio
feature: Personalization
role: User
level: Beginner
exl-id: 214ad693-d456-47ec-a9c8-199ba23c3d9c
source-git-commit: c248dd899ea704e43873652545c6b945c2915b57
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 17%

---

# Utilizzare i blocchi di personalizzazione{#personalization-blocks}

I blocchi di personalizzazione sono contenuti dinamici che contengono un rendering specifico che puoi inserire nelle consegne. Ad esempio, puoi aggiungere un logo, un messaggio di saluto o un collegamento a una pagina speculare.

Per accedere ai blocchi di contenuto personalizzati, passa alla **[!UICONTROL Resources > Campaign Management > Personalization blocks]** nodo dell&#39;explorer. I blocchi di personalizzazione incorporati sono elencati in [questa sezione](#ootb-personalization-blocks).

Puoi anche definire nuovi blocchi per ottimizzare la personalizzazione delle consegne. [Ulteriori informazioni](#create-custom-personalization-blocks).

## Inserire blocchi di personalizzazione {#insert-personalization-blocks}

Per inserire un blocco di personalizzazione in un messaggio, effettua le seguenti operazioni:

1. Nell’editor dei contenuti della consegna guidata, fai clic sull’icona di personalizzazione e seleziona la **[!UICONTROL Include]** menu.
1. Seleziona un blocco di personalizzazione dall’elenco, oppure fai clic su **[!UICONTROL Other...]** per accedere all’elenco completo.

   ![](assets/perso-content-block.png)

1. Il blocco di personalizzazione viene quindi inserito come script. Viene adattato automaticamente al profilo del destinatario quando viene generata la personalizzazione.
1. Accedi a **[!UICONTROL Preview]** e seleziona un destinatario per visualizzare il contenuto di questo blocco per un destinatario specifico.

Puoi includere il codice sorgente di un blocco di personalizzazione nel contenuto della consegna. A questo scopo, seleziona **[!UICONTROL Include the HTML source code of the block]** quando la selezioni.

## Blocchi di personalizzazione incorporati {#ootb-personalization-blocks}

I blocchi di personalizzazione incorporati sono:

* **[!UICONTROL Enabled by Adobe Campaign]**: inserisce il logo &quot;Abilitato da Adobe Campaign&quot;.
* **[!UICONTROL Formatting function for proper nouns]**: genera il **[!UICONTROL toSmartCase]** Funzione JavaScript, che trasforma la prima lettera di ogni parola in maiuscolo.
* **[!UICONTROL Greetings]**: inserisce i saluti con il nome completo del destinatario, seguito da una virgola. Esempio: “Ciao John Doe,” 
* **[!UICONTROL Insert logo]**: inserisce un logo definito nelle impostazioni dell’istanza.
* **[!UICONTROL Link to mirror page]**: inserisce un collegamento al [pagina mirror](mirror-page.md). Il formato predefinito è: “Se non riesci a visualizzare correttamente questo messaggio, fai clic qui”.
* **[!UICONTROL Mirror page URL]**: inserisce l’URL della pagina speculare, consentendo ai designer della consegna di controllare il collegamento.
* **[!UICONTROL Offer acceptance URL in unitary mode]**: inserisce un URL che consente di impostare un’offerta su **[!UICONTROL Accepted]**. Questo blocco è disponibile se il modulo di interazione è abilitato
* **[!UICONTROL Registration confirmation]**: inserisce un collegamento che consente di confermare la sottoscrizione.
* **[!UICONTROL Registration link]**: inserisce un collegamento di abbonamento. Questo collegamento è definito nelle impostazioni dell’istanza. Il contenuto predefinito è: “Per registrarti, fai clic qui.”
* **[!UICONTROL Registration link (with referrer)]**: inserisce un collegamento di abbonamento, che consente di identificare il visitatore e la consegna. Questo collegamento è definito nelle impostazioni dell’istanza.
* **[!UICONTROL Registration page URL]**: inserisce un URL di abbonamento
* **[!UICONTROL Style of content emails]** e **[!UICONTROL Notification style]**: genera un codice che formatta un’e-mail con stili HTML predefiniti.
* **[!UICONTROL Unsubscription link]**: inserisce un collegamento che consente di annullare l’abbonamento a tutte le consegne (inserisco nell&#39;elenco Bloccati di annullamento dell’abbonamento). Il contenuto associato predefinito è: “Hai ricevuto questo messaggio perché sei stato in contatto con ***nome organizzazione*** o una sua filiale. Per non ricevere più messaggi da ***nome organizzazione***, fai clic qui.”

## Creare blocchi di personalizzazione personalizzati {#create-custom-personalization-blocks}

Puoi definire nuovi blocchi di contenuto personalizzati da inserire dall’icona di personalizzazione.

Per creare un blocco di personalizzazione, effettua le seguenti operazioni:

1. Accedi a **[!UICONTROL Resources > Campaign Management > Personalization blocks]** cartella di Campaign explorer.
1. Sopra l’elenco dei blocchi predefiniti, fai clic su **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. Compila le impostazioni del blocco di personalizzazione:

   ![](assets/perso-custom-block.png)

   * Inserisci l’etichetta del blocco. Questa etichetta viene visualizzata nella finestra di inserimento del campo di personalizzazione.
   * Seleziona un **Consegna** tipo di contenuto.
   * Abilita **[!UICONTROL Visible in the customization menus]** per rendere accessibile questo blocco dall’icona di inserimento del campo di personalizzazione.
   * Se necessario, abilita **[!UICONTROL The content of the personalization block depends upon the format]** , per definire due blocchi diversi per le e-mail HTML e Text.
   * Inserisci il contenuto (in HTML, testo, JavaScript, ecc.) del blocco di personalizzazione e fai clic su **[!UICONTROL Save]**.

Una volta salvato, il nuovo blocco di personalizzazione è disponibile nell’editor di consegna.

## Video tutorial {#personalization-blocks-video}

Scopri come creare blocchi di contenuto dinamici e come utilizzarli per personalizzare il contenuto della consegna e-mail nel video seguente.

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)
