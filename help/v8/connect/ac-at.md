---
title: Utilizzare Campaign e Adobe Target
description: Scopri come utilizzare Campaign e Adobe Target
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 891a9a87-f3a4-405a-87ed-a7703be90a67
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '988'
ht-degree: 1%

---

# Utilizzare Campaign e Adobe Target

Collega Campaign e Target per includere un’offerta da Adobe Target in una consegna e-mail di Adobe Campaign.

Questa integrazione consente di implementare i casi di utilizzo come segue: quando un destinatario apre un’e-mail inviata tramite Adobe Campaign, una chiamata ad Adobe Target ti consente di visualizzare una versione dinamica del contenuto. Questa versione dinamica viene calcolata a seconda delle regole precedentemente specificate durante la creazione dell’e-mail.

>[!NOTE]
>L’integrazione supporta solo immagini statiche. Gli altri tipi di contenuto non possono essere personalizzati.

![](../assets/do-not-localize/speech.png)  Come utente di Cloud Services gestiti, [Adobe di contatto](../start/campaign-faq.md#support) per implementare trigger di Experience Cloud con Campaign.

Adobe Target può utilizzare i seguenti tipi di dati:

* Dati dal database Adobe Campaign
* Segmenti collegati all’ID visitatore in Adobe Target, solo se i dati utilizzati non sono soggetti a limitazioni legali
* Dati Adobe Target: agente utente, indirizzo IP, dati di geolocalizzazione

## Inserire un contenuto dinamico

Nell’esempio seguente, scoprirai come integrare **un’offerta dinamica** da Adobe Target a un’e-mail Adobe Campaign.

Desideriamo creare un messaggio con un’immagine che cambierà dinamicamente in base al paese del destinatario. I dati vengono inviati con ogni richiesta mbox e dipendono dall’indirizzo IP del visitatore.

In questa e-mail, vogliamo che una delle immagini possa variare dinamicamente in base alle seguenti esperienze utente:

* L&#39;e-mail viene aperta in Francia.
* L’e-mail viene aperta negli Stati Uniti.
* Se non si applica nessuna di queste condizioni, viene visualizzata un&#39;immagine predefinita.

![](assets/target_4.png)

In Adobe Campaign e Adobe Target è necessario effettuare le seguenti operazioni:

1. [Inserire l’offerta dinamica in un messaggio e-mail](#inserting-dynamic-offer)
1. [Creare offerte di reindirizzamento](#create-redirect-offers)
1. [Creare tipi di pubblico](#audiences-target)
1. [Creare un’attività Targeting esperienze](#creating-targeting-activity)
1. [Anteprima e invio del messaggio](#preview-send-email)

### Inserire l’offerta dinamica in un messaggio e-mail {#inserting-dynamic-offer}

In Adobe Campaign, definisci il target e il contenuto dell’e-mail. Puoi inserire un’immagine dinamica da Adobe Target.

A questo scopo, specifica l’URL dell’immagine predefinita, il nome della posizione e i campi da trasferire ad Adobe Target.

In Adobe Campaign, esistono due modi per inserire un’immagine dinamica da Target in un messaggio e-mail:

* Se utilizzi l’editor di contenuti digitali, scegli un’immagine esistente e seleziona **[!UICONTROL Insert]** > **[!UICONTROL Dynamic image served by Adobe Target]** dalla barra degli strumenti.

   ![](assets/target_5.png)

* Se utilizzi l’editor standard, posiziona il cursore nel punto in cui desideri inserire l’immagine e seleziona **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target...]** dal menu a discesa personalizzazione .

   ![](assets/target_12.png)

Puoi quindi definire i parametri dell’immagine:

* La **[!UICONTROL Default image]** L’URL di è l’immagine che verrà visualizzata quando non viene soddisfatta alcuna condizione. Puoi anche selezionare un’immagine dalla libreria Risorse.
* La **[!UICONTROL Target location]** è il nome della posizione dell’offerta dinamica. Dovrai selezionare questa posizione nell’attività Adobe Target.
* La **[!UICONTROL Landing Page]** consente di reindirizzare l’immagine predefinita a una pagina di destinazione predefinita. Questo URL si applica solo quando l’immagine predefinita viene visualizzata nell’e-mail finale. È facoltativo.
* La **[!UICONTROL Additional decision parameters]**  definisce la mappatura tra i campi definiti nei segmenti Adobe Target e i campi Adobe Campaign. I campi Adobe Campaign utilizzati devono essere stati specificati nella rawbox. Nel nostro esempio, è stato aggiunto il campo Paese .

Se utilizzi le autorizzazioni Enterprise nelle impostazioni di Adobe Target, aggiungi la proprietà corrispondente in questo campo. Ulteriori informazioni sulle autorizzazioni di Target Enterprise in [questa pagina](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=en#administer).

![](assets/target_13.png)

### Creare offerte di reindirizzamento {#create-redirect-offers}

In Adobe Target puoi creare diverse versioni dell’offerta. A seconda di ogni esperienza utente, è possibile creare un’offerta di reindirizzamento e specificare l’immagine da visualizzare.

Nel nostro caso, sono necessarie due offerte di reindirizzamento, la terza (quella predefinita) deve essere definita in Adobe Campaign.

1. Per creare una nuova offerta di reindirizzamento in Target Standard, dal **[!UICONTROL Content]** scheda , fai clic su **[!UICONTROL Code offers]**.

1. Fai clic su **[!UICONTROL Create]**, quindi su **[!UICONTROL Redirect Offer]**.

   ![](assets/target_9.png)

1. Immetti un nome per l’offerta e l’URL dell’immagine.

   ![](assets/target_6.png)

1. Segui la stessa procedura per l’offerta di reindirizzamento rimanente. Per ulteriori informazioni, consulta questa [pagina](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=en#experiences).

### Creare tipi di pubblico {#audiences-target}

In Adobe Target, devi creare i due tipi di pubblico in cui le persone che visitano la tua offerta verranno categorizzate per i diversi contenuti da consegnare. Per ogni pubblico, aggiungi una regola per definire chi potrà visualizzare l’offerta.

1. Per creare un nuovo pubblico in Target, dal **[!UICONTROL Audiences]** scheda , fai clic su **[!UICONTROL Create Audience]**.

   ![](assets/audiences_1.png)

1. Aggiungi un nome al pubblico.

   ![](assets/audiences_2.png)

1. Fai clic su **[!UICONTROL Add a rule]** e selezionare una categoria. La regola utilizza criteri specifici per il targeting dei visitatori. Puoi perfezionare le regole aggiungendo condizioni o creando nuove regole in altre categorie.

1. Segui la stessa procedura per i tipi di pubblico rimanenti.

### Creare un’attività Targeting esperienze {#creating-targeting-activity}

In Adobe Target, dobbiamo creare un’attività Targeting esperienze, definire le diverse esperienze e associarle alle offerte corrispondenti.

Innanzitutto devi definire il pubblico:

1. Per creare un’attività Targeting esperienze, dai **[!UICONTROL Activities]** scheda , fai clic su **[!UICONTROL Create Activity]** then **[!UICONTROL Experience Targeting]**.

   ![](assets/target_10.png)

1. Seleziona **[!UICONTROL Form]** come **[!UICONTROL Experience Composer]**.

1. Scegli un pubblico facendo clic sul pulsante **[!UICONTROL Change audience]** pulsante .

   ![](assets/target_10_2.png)

1. Seleziona il pubblico creato nei passaggi precedenti.

   ![](assets/target_10_3.png)

1. Crea un’altra esperienza facendo clic su **[!UICONTROL Add Experience Targeting]**.

Quindi aggiungi un contenuto per ogni pubblico:

1. Seleziona il nome della posizione scelto al momento dell’inserimento dell’offerta dinamica in Adobe Campaign.

   ![](assets/target_15.png)

1. Fai clic sul pulsante a discesa e seleziona **[!UICONTROL Change Redirect Offer]**.

   ![](assets/target_content.png)

1. Seleziona l’offerta di reindirizzamento creata in precedenza.

   ![](assets/target_content_2.png)

1. Segui gli stessi passaggi per la seconda esperienza.

La **[!UICONTROL Target]** viene riepilogata l’attività. Se necessario, puoi aggiungere altre esperienze.

![](assets/target_experience.png)

La **[!UICONTROL Goal & Settings]** La finestra ti consente di personalizzare l’attività impostando una priorità, un obiettivo o una durata.

La **[!UICONTROL Reporting Settings]** consente di selezionare un’azione e di modificare i parametri che determinano quando viene raggiunto l’obiettivo.

![](assets/target_experience_2.png)

## Anteprima e invio del messaggio {#preview-send-email}

In Adobe Campaign, ora puoi visualizzare l’anteprima del messaggio e-mail e testarne il rendering su destinatari diversi.

Noterai che l’immagine cambia in base alle diverse esperienze create.

Ora puoi inviare il tuo messaggio e-mail, inclusa un’offerta dinamica da Target.

![](assets/target_20.png)
