---
title: Aggiungere un collegamento alla pagina mirror
description: Scopri come aggiungere e gestire il collegamento alla pagina mirror
feature: Email
role: User
level: Beginner
exl-id: 7bf3937c-484d-4404-8a9b-de7a10f5455a
source-git-commit: b333db04dd10cc28956959a446f6567e2a89b2d4
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 57%

---

# Collegamento a una pagina mirror {#mirror-page}

## Informazioni sulla pagina mirror {#about-mirror-page}

La pagina mirror è una versione online della tua e-mail.

Mentre la maggior parte dei client e-mail esegue il rendering delle immagini senza alcun problema, alcuni predefiniti possono evitare la visualizzazione delle immagini per motivi di sicurezza. Gli utenti possono passare alla pagina mirror di un’e-mail, ad esempio se riscontrano problemi di rendering o immagini interrotte quando tentano di visualizzarla nella casella in entrata. Si consiglia inoltre di fornire una versione online per motivi di accessibilità o di incoraggiare la condivisione social.

La pagina mirror generata da Adobe Campaign contiene tutti i dati di personalizzazione.

![esempio di collegamento mirror](assets/mirror-page-link.png){width="600" align="left"}

## Aggiungere un collegamento alla pagina mirror {#link-to-mirror-page}

È buona prassi inserire un collegamento alla pagina mirror. Questo link può essere ad esempio “Visualizza questa e-mail nel tuo browser” o “Leggi online”. Spesso si trova nell’intestazione o nel piè di pagina dell’e-mail.

In Adobe Campaign, puoi inserire un collegamento alla pagina mirror nel contenuto dell’e-mail utilizzando il **blocco di personalizzazione** dedicato. Il blocco di personalizzazione incorporato **Collegamento a una pagina mirror** inserisce il seguente codice nel contenuto dell’e-mail: `<%@ include view='MirrorPage' %>`.

![](assets/mirror-page-insert.png){width="800" align="left"}


Per ulteriori informazioni sull’inserimento di blocchi di contenuto di personalizzazione, consulta [Blocchi di personalizzazione](personalization-blocks.md).

## Gestire la generazione della pagina speculare {#mirror-page-generation}

Per impostazione predefinita, la pagina mirror viene generata automaticamente da Adobe Campaign se il contenuto dell’e-mail non è vuoto e se contiene un collegamento alla pagina mirror (detto anche collegamento mirror).

Puoi controllare la modalità di generazione della pagina mirror dell’e-mail. Le opzioni sono disponibili nelle proprietà di consegna. Per accedere a queste opzioni:

1. Accedi a **[!UICONTROL Validity]** delle proprietà e-mail.
1. In **Gestione delle pagine mirror** sezione, controlla la **[!UICONTROL Mode]** elenco a discesa.

![](assets/mirror-page-generation.png){width="800" align="left"}

Oltre alla modalità predefinita, sono disponibili le seguenti opzioni:

* **[!UICONTROL Force the generation of the mirror page]**: utilizza questa modalità per generare la pagina speculare anche se nella consegna non è inserito alcun collegamento alla pagina speculare.
* **[!UICONTROL Do not generate the mirror page]**: utilizza questa modalità per evitare di generare una pagina speculare, anche se il collegamento è presente nella consegna.
* **[!UICONTROL Generates a mirror page accessible using only the message identifier]**: quando il collegamento alla pagina speculare non è presente nel contenuto dell’e-mail, utilizza questa opzione per abilitare l’accesso al contenuto della pagina speculare, nella finestra del registro di consegna, come descritto di seguito.

## Controlla la pagina mirror di un destinatario {#mirror-page-access}

Puoi accedere al contenuto della pagina speculare per un destinatario specifico di una consegna, con i dati di personalizzazione.

Per accedere a questa pagina mirror:

1. Una volta inviata la consegna, aprila e naviga fino alla **[!UICONTROL Delivery]** scheda.

1. Seleziona un destinatario e fai clic su **[!UICONTROL Display the mirror page for this message...]** collegamento.

   ![](assets/mirror-page-display.png){width="800" align="left"}

   La pagina speculare viene visualizzata in una schermata dedicata, con i dati di personalizzazione per il destinatario selezionato.
