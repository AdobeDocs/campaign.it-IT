---
title: Introduzione alla personalizzazione
description: Scopri come personalizzare il contenuto dei messaggi
feature: Personalization
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 1da45746-4d69-415b-a793-9a08ce80091d
source-git-commit: 25ee55d5327e0ba7f2192f7b462853269c8cbf46
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 48%

---

# Introduzione alla personalizzazione {#personalize-content}

Per ottenere il massimo da ogni campagna di marketing, Adobe Campaign offre un modo per fornire contenuti personalizzati che parlano ai clienti a loro livello. In base ai dati del profilo, funzionalità di personalizzazione per creare un’esperienza personalizzata per diversi gruppi e singoli utenti: puoi adattare i messaggi a ogni destinatario specifico sfruttando i dati e le informazioni di cui disponi su di essi. Può essere il nome, gli interessi, dove vivono, cosa hanno comprato, e molto altro.

Adobe Campaign semplifica la personalizzazione: puoi visualizzare diversi tipi di contenuto personalizzati per ogni destinatario utilizzando un singolo [modello di messaggio](create-templates.md). Nei messaggi transazionali, ad esempio e-mail di conferma dell’acquisto o di abbandono del carrello, includi informazioni sugli elenchi dei prodotti per ogni individuo all’interno di un singolo modello e-mail.


## Strategie Personalization {#personalization-strategy}

Utilizza Campaign per creare contenuti dinamici e inviare messaggi personalizzati. Le funzionalità di personalizzazione possono essere combinate per migliorare i messaggi e creare un’esperienza utente personalizzata.

Puoi personalizzare il contenuto del messaggio in diversi modi:

* Inserendo **campi di personalizzazione** dinamici

  I campi di personalizzazione vengono utilizzati per la personalizzazione di primo livello dei messaggi. Puoi selezionare qualsiasi campo disponibile nel database dall’editor di personalizzazione. Per una consegna, puoi selezionare qualsiasi campo correlato al destinatario, al messaggio o alla consegna. Questi attributi di personalizzazione possono essere inseriti nella riga dell’oggetto o nel corpo dei messaggi. [Ulteriori informazioni](personalization-fields.md).

  Per inserire nel contenuto la città del destinatario, utilizza la seguente sintassi: &lt;%= recipient.location.city %>.

* Inserimento di **blocchi di contenuto** predefiniti

  Campaign viene fornito con un set di blocchi di personalizzazione contenenti un rendering specifico da inserire nelle consegne. Ad esempio, puoi aggiungere un logo, un messaggio di auguri o un collegamento alla pagina mirror del messaggio. I blocchi di contenuto sono disponibili da una voce dedicata nell’editor di personalizzazione. [Ulteriori informazioni](personalization-blocks.md).

* Creare **contenuto condizionale**

  Configura il contenuto condizionale per aggiungere la personalizzazione dinamica, ad esempio in base al profilo del destinatario. I blocchi di testo e/o le immagini vengono inseriti quando viene soddisfatta una particolare condizione. [Ulteriori informazioni](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Guardrail e raccomandazioni{#perso-guardrails}

### Timeout di Personalization {#perso-timeout}

Per migliorare la protezione della consegna, puoi impostare un periodo di timeout per la fase di personalizzazione.

Nella scheda **[!UICONTROL Delivery]** di **[!UICONTROL Delivery properties]**, selezionare un valore massimo in secondi per l&#39;opzione **[!UICONTROL Maximum personalization run time]**.

Durante l’anteprima o l’invio, se la fase di personalizzazione supera il tempo massimo impostato in questo campo, il processo viene interrotto con un messaggio di errore e la consegna non riesce.

Il valore predefinito è 5 secondi.

Se imposti questa opzione su 0, non ci sarà alcun limite di tempo per la fase di personalizzazione.


### Variabili interne{#internal-variables}

Le seguenti variabili sono variabili interne che possono essere utilizzate per la personalizzazione ma che non devono essere modificate: **delivery**, **message**, **dataSource**, **targetData**, **provider**, **coupon**, **couponValue**, **proposition**.


## Video tutorial {#personalization-video}

Scopri i diversi tipi di contenuti dinamici e come creare e applicare blocchi di personalizzazione e istruzioni condizionali a una consegna.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)
