---
title: Blocchi di personalizzazione
description: Scopri come utilizzare i blocchi di personalizzazione incorporati nel contenuto del messaggio
feature: Personalization
role: User
level: Beginner
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 13%

---


# Blocchi di personalizzazione{#personalization-blocks}

I blocchi di personalizzazione sono contenuti dinamici che contengono un rendering specifico che puoi inserire nelle consegne. Ad esempio, puoi aggiungere un logo, un messaggio di auguri o un collegamento a una pagina speculare.

Per accedere ai blocchi di contenuto personalizzati, seleziona **[!UICONTROL Resources > Campaign Management > Personalization blocks]** nodo dell&#39;esploratore. I blocchi di personalizzazione incorporati sono elencati in [questa sezione](#ootb-personalization-blocks).

Puoi anche definire nuovi blocchi per ottimizzare la personalizzazione delle consegne. [Ulteriori informazioni](#create-custom-personalization-blocks).

## Inserire blocchi di personalizzazione {#insert-personalization-blocks}

Per inserire un blocco di personalizzazione in un messaggio, segui i passaggi seguenti:

1. Nell’editor dei contenuti della procedura guidata di consegna, fai clic sull’icona di personalizzazione e seleziona la **[!UICONTROL Include]** menu.
1. Seleziona un blocco di personalizzazione dall’elenco o fai clic sul pulsante **[!UICONTROL Other...]** per accedere all’elenco completo.

   ![](assets/perso-content-block.png)

1. Il blocco di personalizzazione viene quindi inserito come script. Viene automaticamente adattato al profilo del destinatario quando viene generata la personalizzazione.
1. Sfoglia il **[!UICONTROL Preview]** e seleziona un destinatario per visualizzare il contenuto di questo blocco per un destinatario specifico.

Puoi includere il codice sorgente di un blocco di personalizzazione nel contenuto della consegna. A questo scopo, seleziona **[!UICONTROL Include the HTML source code of the block]** quando lo selezioni.

## Blocchi di personalizzazione incorporati {#ootb-personalization-blocks}

I blocchi di personalizzazione incorporati sono:

* **[!UICONTROL Enabled by Adobe Campaign]**: inserisce il logo &quot;Abilitato da Adobe Campaign&quot;.
* **[!UICONTROL Formatting function for proper nouns]**: genera **[!UICONTROL toSmartCase]** Funzione Javascript, che cambia in maiuscolo la prima lettera di ogni parola.
* **[!UICONTROL Greetings]**: inserisce i saluti con il nome completo del destinatario, seguito da una virgola. Esempio: “Ciao John Doe,”
* **[!UICONTROL Insert logo]**: inserisce un logo definito nelle impostazioni dell’istanza.
* **[!UICONTROL Link to mirror page]**: inserisce un collegamento alla [pagina speculare](mirror-page.md). Il formato predefinito è: &quot;Se non riesci a visualizzare correttamente questo messaggio, fai clic qui&quot;.
* **[!UICONTROL Mirror page URL]**: inserisce l’URL della pagina speculare, consentendo a Progettazione consegne di controllare il collegamento.
* **[!UICONTROL Offer acceptance URL in unitary mode]**: inserisce un URL che consente di impostare un’offerta su **[!UICONTROL Accepted]**. (Questo blocco è disponibile se il modulo di interazione è abilitato)
* **[!UICONTROL Registration confirmation]**: inserisce un collegamento che consente di confermare l’abbonamento.
* **[!UICONTROL Registration link]**: inserisce un collegamento di abbonamento. Questo collegamento è definito nelle impostazioni dell’istanza. Il contenuto predefinito è: “Per registrarti, fai clic qui.”
* **[!UICONTROL Registration link (with referrer)]**: inserisce un collegamento di abbonamento, che consente di identificare il visitatore e la consegna. Questo collegamento è definito nelle impostazioni dell’istanza.
* **[!UICONTROL Registration page URL]**: inserisce un URL di abbonamento
* **[!UICONTROL Style of content emails]** e **[!UICONTROL Notification style]**: genera codice che formatta un’e-mail con stili di HTML predefiniti.
* **[!UICONTROL Unsubscription link]**: inserisce un collegamento che consente di annullare l’iscrizione a tutte le consegne (elenco Bloccati). Il contenuto associato predefinito è: “Hai ricevuto questo messaggio perché sei stato in contatto con ***nome organizzazione*** o una sua filiale. Per non ricevere più messaggi da ***nome organizzazione***, fai clic qui.”

## Creare blocchi di personalizzazione personalizzati {#create-custom-personalization-blocks}

Puoi definire nuovi blocchi di contenuto personalizzati da inserire dall’icona di personalizzazione.

Per creare un blocco di personalizzazione, segui i passaggi seguenti:

1. Sfoglia il **[!UICONTROL Resources > Campaign Management > Personalization blocks]** cartella di Campaign explorer.
1. Sopra l’elenco dei blocchi incorporati, fai clic su **[!UICONTROL New]**.

   ![](assets/perso-new-block.png)

1. Compila le impostazioni del blocco di personalizzazione:

   ![](assets/perso-custom-block.png)

   * Inserisci l’etichetta del blocco. Questa etichetta viene visualizzata nella finestra di inserimento del campo di personalizzazione.
   * Seleziona una **Consegna** tipo di contenuto.
   * Abilita la **[!UICONTROL Visible in the customization menus]** per rendere questo blocco accessibile dall’icona di inserimento del campo di personalizzazione.
   * Se necessario, abilita **[!UICONTROL The content of the personalization block depends upon the format]** per definire due blocchi diversi per le e-mail di HTML e testo.
   * Immetti il contenuto (in HTML, testo, JavaScript, ecc.) del blocco di personalizzazione e fai clic su **[!UICONTROL Save]**.

Una volta salvato, il nuovo blocco di personalizzazione è disponibile nell’editor di consegna.

## Video tutorial {#personalization-blocks-video}

Scopri come creare blocchi di contenuto dinamici e come utilizzarli per personalizzare il contenuto della consegna e-mail nel video seguente.

>[!VIDEO](https://video.tv.adobe.com/v/342088?quality=12)


