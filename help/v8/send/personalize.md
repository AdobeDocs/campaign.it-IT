---
title: Introduzione alla personalizzazione
description: Scopri come personalizzare il contenuto dei messaggi
feature: Personalization
role: User
level: Beginner
source-git-commit: a8568e0c1e9af11b533b7d435691dc12cc0a2485
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 36%

---

# Introduzione alla personalizzazione {#personalize-content}

Per trarre il massimo da ogni campagna di marketing, Adobe Campaign offre un modo per distribuire contenuti personalizzati che parlano ai clienti a livello di . In base ai dati di profilo, le funzionalità di personalizzazione consentono di creare un’esperienza personalizzata per gruppi e singoli utenti diversi: puoi adattare i tuoi messaggi a ogni destinatario specifico sfruttando i dati e le informazioni disponibili su di essi. Può essere il loro nome, i loro interessi, dove vivono, quello che hanno comprato, e molto altro.

Adobe Campaign semplifica la personalizzazione: è possibile visualizzare diversi tipi di contenuto personalizzati per ciascun destinatario utilizzando un singolo [modello e-mail](create-templates.md). Nei messaggi transazionali, ad esempio e-mail di conferma dell’acquisto o di abbandono del carrello, includi le informazioni sugli elenchi dei prodotti per ogni individuo all’interno di un singolo modello e-mail.


## Strategie di personalizzazione {#personalization-strategy}

Utilizza Campaign per creare contenuti dinamici e inviare messaggi personalizzati. Le funzionalità di personalizzazione possono essere combinate per migliorare i messaggi e creare un’esperienza utente personalizzata.

Puoi personalizzare il contenuto del messaggio in diversi modi:

* Inserendo **campi di personalizzazione** dinamici

   I campi di personalizzazione vengono utilizzati per la personalizzazione di primo livello dei messaggi. Puoi selezionare qualsiasi campo disponibile nel database dall’editor di personalizzazione. Per una consegna, puoi selezionare qualsiasi campo correlato al destinatario, al messaggio o alla consegna. Questi attributi di personalizzazione possono essere inseriti nella riga dell’oggetto o nel corpo dei messaggi. [Ulteriori informazioni](personalization-fields.md).

   Per inserire nel contenuto la città del destinatario, utilizza la seguente sintassi: &lt;%= recipient.location.city %>.

* Inserimento di **blocchi di contenuto** predefiniti

   Campaign viene fornito con un set di blocchi di personalizzazione contenenti un rendering specifico da inserire nelle consegne. Ad esempio, puoi aggiungere un logo, un messaggio di auguri o un collegamento alla pagina mirror del messaggio. I blocchi di contenuto sono disponibili da una voce dedicata nell’editor per la personalizzazione. [Ulteriori informazioni](personalization-blocks.md).

* Crea **contenuto condizionale**

   Configura il contenuto condizionale per aggiungere la personalizzazione dinamica in base, ad esempio, al profilo del destinatario. I blocchi di testo e/o le immagini vengono inseriti quando una particolare condizione è vera. [Ulteriori informazioni](conditions.md).

<!--* Add **personalized offers**
    
    Insert personalized offers in your message content, depending on the recipient location, the current weather, or the last purchase order.
-->


## Guardrail e raccomandazioni{#perso-guardrails}

### Timeout personalizzazione{#perso-timeout}

Per migliorare la protezione della consegna, puoi impostare un periodo di timeout per la fase di personalizzazione.

In **[!UICONTROL Delivery]** della scheda **[!UICONTROL Delivery properties]**, seleziona un valore massimo in secondi per il **[!UICONTROL Maximum personalization run time]** opzione .

Durante l’anteprima o l’invio, se la fase di personalizzazione supera il tempo massimo impostato in questo campo, il processo verrà interrotto con un messaggio di errore e la consegna avrà esito negativo.

Il valore predefinito è 5 secondi.

Se imposti questa opzione su 0, non ci sarà alcun limite di tempo per la fase di personalizzazione.


### Variabili interne{#internal-variables}

Le seguenti variabili sono variabili interne che possono essere utilizzate per la personalizzazione ma che non devono essere modificate: **consegna**, **message**, **dataSource**, **targetData**, **fornitore**, **coupon**, **couponValue**, **proposta**.


## Video tutorial {#personalization-video}

Scopri i diversi tipi di contenuti dinamici e come creare e applicare blocchi di personalizzazione e istruzioni condizionali a una consegna.


>[!VIDEO](https://video.tv.adobe.com/v/335734?quality=12)