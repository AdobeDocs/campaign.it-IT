---
title: Aggiungere un collegamento alla pagina speculare
description: Scopri come aggiungere e gestire il collegamento alla pagina speculare
feature: Email
role: User
level: Beginner
source-git-commit: d8ceefe1dd56aecb810878d99395ac900f889c2e
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Collegamento alla pagina speculare{#mirror-page}

## Informazioni sulla pagina speculare{#about-mirror-page}

La pagina speculare è una versione online della tua e-mail.

Mentre la maggior parte dei client e-mail esegue il rendering delle immagini senza alcun problema, alcuni predefiniti possono evitare la visualizzazione delle immagini per motivi di sicurezza. Gli utenti possono passare alla pagina speculare di un’e-mail, ad esempio se riscontrano problemi di rendering o immagini interrotte quando tentano di visualizzarla nella casella in entrata. Si consiglia inoltre di fornire una versione online per motivi di accessibilità o di incoraggiare la condivisione social network.

La pagina speculare generata da Adobe Campaign contiene tutti i dati di personalizzazione.

![](assets/mirror-page-link.png)


## Aggiungere un collegamento alla pagina speculare{#link-to-mirror-page}

È buona prassi inserire un collegamento alla pagina speculare. Questo link può essere ad esempio &#39;Visualizza questa e-mail nel tuo browser&#39; o &#39;Leggi questo online&#39;. Spesso si trova nell’intestazione o nel piè di pagina dell’e-mail.

In Adobe Campaign, puoi inserire un collegamento alla pagina speculare nel contenuto dell’e-mail utilizzando l’ **blocco di personalizzazione**. Incorporato **Collegamento a una pagina speculare** nel contenuto dell’e-mail viene inserito il seguente codice: `<%@ include view='MirrorPage' %>`.

<!--For more on personalization blocks insertion, refer to [Personalization blocks](personalization-blocks.md).-->

## Generazione di pagine mirror{#mirror-page-generation}

Per impostazione predefinita, la pagina speculare viene generata automaticamente da Adobe Campaign se il contenuto dell’e-mail non è vuoto e se contiene un collegamento alla pagina speculare (aka Mirror link).

Puoi controllare la modalità di generazione della pagina speculare e-mail. Le opzioni sono disponibili nelle proprietà di consegna. Per accedere a queste opzioni:

1. Sfoglia il **[!UICONTROL Validity]** scheda delle proprietà e-mail.
1. In **Gestione pagina speculare** nella sezione **[!UICONTROL Mode]** elenco a discesa.

![](assets/mirror-page-generation.png)

Oltre alla modalità predefinita, sono disponibili le seguenti opzioni:

* **[!UICONTROL Force the generation of the mirror page]**: utilizza questa modalità per generare la pagina speculare anche se nella consegna non è inserito alcun collegamento alla pagina speculare.
* **[!UICONTROL Do not generate the mirror page]**: utilizza questa modalità per evitare di generare una pagina speculare, anche se il collegamento è presente nella consegna.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: utilizza questa opzione per abilitare l’accesso al contenuto della pagina speculare, con i dati di personalizzazione, nella finestra del registro di consegna. Per accedere a questa pagina speculare: una volta inviata la consegna, aprila e sfoglia fino alla **[!UICONTROL Delivery]** scheda . Seleziona un destinatario e fai clic sul pulsante **[!UICONTROL Display the mirror page for this message...]** link. La pagina speculare viene visualizzata in una nuova scheda.

