---
title: Utilizzare Campaign e Adobe Target
description: Scopri come utilizzare Campaign e Adobe Target
feature: Target Integration
role: Admin, User
level: Beginner, Intermediate
exl-id: 891a9a87-f3a4-405a-87ed-a7703be90a67
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '970'
ht-degree: 0%

---

# Utilizzare Campaign e Adobe Target

Connetti Campaign e Target per includere un’offerta da Adobe Target in una consegna e-mail di Adobe Campaign.

Questa integrazione consente di implementare i casi d’uso come segue: quando un destinatario apre un’e-mail inviata tramite Adobe Campaign, una chiamata ad Adobe Target consente di visualizzare una versione dinamica del contenuto. Questa versione dinamica viene calcolata in base alle regole specificate in precedenza durante la creazione dell’e-mail.

>[!NOTE]
>* L’integrazione supporta solo immagini statiche. Gli altri tipi di contenuto non possono essere personalizzati.
>
>* In qualità di utente di Managed Cloud Services, [contatta Adobe](../start/campaign-faq.md#support) per implementare i trigger di Experience Cloud con Campaign.

Adobe Target può utilizzare i seguenti tipi di dati:

* Dati dal database di Adobe Campaign
* Segmenti collegati all’ID visitatore in Adobe Target, solo se i dati utilizzati non sono soggetti a limitazioni legali
* Dati Adobe Target: agente utente, indirizzo IP, dati di geolocalizzazione

## Inserire un contenuto dinamico

Nell&#39;esempio seguente verrà illustrato come integrare **un&#39;offerta dinamica** da Adobe Target in un messaggio e-mail di Adobe Campaign.

Vogliamo creare un messaggio con un’immagine che cambia dinamicamente in base al paese del destinatario. I dati vengono inviati con ogni richiesta mbox e dipendono dall’indirizzo IP del visitatore.

In questa e-mail, vogliamo che una delle immagini vari in modo dinamico in base alle seguenti esperienze utente:

* L’e-mail è stata aperta in Francia.
* L’e-mail viene aperta negli Stati Uniti.
* Se nessuna di queste condizioni è applicabile, viene visualizzata un&#39;immagine predefinita.

![](assets/target_4.png)

In Adobe Campaign e Adobe Target è necessario eseguire i seguenti passaggi:

1. [Inserire l’offerta dinamica in un messaggio e-mail](#inserting-dynamic-offer)
1. [Creare offerte di reindirizzamento](#create-redirect-offers)
1. [Creare tipi di pubblico](#audiences-target)
1. [Creare un’attività Targeting esperienze](#creating-targeting-activity)
1. [Anteprima e invio del messaggio](#preview-send-email)

### Inserire l’offerta dinamica in un messaggio e-mail {#inserting-dynamic-offer}

In Adobe Campaign, definisci il target e il contenuto dell’e-mail. È possibile inserire un’immagine dinamica da Adobe Target.

A questo scopo, specifica l’URL dell’immagine predefinita, il nome della posizione e i campi da trasferire in Adobe Target.

In Adobe Campaign, esistono due modi per inserire un’immagine dinamica da Target in un messaggio e-mail:

* Se utilizzi l&#39;editor di contenuti digitali, scegli un&#39;immagine esistente e seleziona **[!UICONTROL Insert]** > **[!UICONTROL Dynamic image served by Adobe Target]** dalla barra degli strumenti.

  ![](assets/target_5.png)

* Se si utilizza l&#39;editor standard, posizionare il cursore nel punto in cui si desidera inserire l&#39;immagine e selezionare **[!UICONTROL Include]** > **[!UICONTROL Dynamic image served by Adobe Target...]** dal menu a discesa di personalizzazione.

  ![](assets/target_12.png)

Puoi quindi definire i parametri dell’immagine:

* L&#39;URL di **[!UICONTROL Default image]** è l&#39;immagine che verrà visualizzata quando non viene soddisfatta alcuna delle condizioni. Puoi anche selezionare un’immagine dalla libreria Assets.
* **[!UICONTROL Target location]** è il nome della posizione dell&#39;offerta dinamica. Dovrai selezionare questa posizione nell’attività di Adobe Target.
* **[!UICONTROL Landing Page]** consente di reindirizzare l&#39;immagine predefinita a una pagina di destinazione predefinita. Questo URL si applica solo quando l’immagine predefinita viene visualizzata nell’e-mail finale. È opzionale.
* **[!UICONTROL Additional decision parameters]** definisce il mapping tra i campi definiti nei segmenti Adobe Target e i campi Adobe Campaign. I campi Adobe Campaign utilizzati devono essere stati specificati nella rawbox. Nel nostro esempio, abbiamo aggiunto il campo Paese.

Se utilizzi le autorizzazioni Enterprise nelle impostazioni di Adobe Target, aggiungi la proprietà corrispondente in questo campo. Per ulteriori informazioni sulle autorizzazioni Enterprise per Target, consulta la [documentazione di Adobe Target](https://experienceleague.adobe.com/it/docs/target/using/administer/manage-users/enterprise/properties-overview#administer){target="_blank"}.

![](assets/target_13.png)

### Creare offerte di reindirizzamento {#create-redirect-offers}

In Adobe Target puoi creare diverse versioni dell’offerta. A seconda di ogni esperienza utente, è possibile creare un’offerta di reindirizzamento e specificare l’immagine da visualizzare.

Nel nostro caso, abbiamo bisogno di due offerte di reindirizzamento, la terza (quella predefinita) deve essere definita in Adobe Campaign.

1. Per creare una nuova offerta di reindirizzamento in Target Standard, dalla scheda **[!UICONTROL Content]**, fare clic su **[!UICONTROL Code offers]**.

1. Fai clic su **[!UICONTROL Create]**, quindi su **[!UICONTROL Redirect Offer]**.

   ![](assets/target_9.png)

1. Immetti un nome per l’offerta e l’URL dell’immagine.

   ![](assets/target_6.png)

1. Segui la stessa procedura per l’offerta di reindirizzamento rimanente. Per ulteriori informazioni, consulta questa [documentazione di Adobe Target](https://experienceleague.adobe.com/docs/target/using/experiences/offers/offer-redirect.html?lang=it#experiences){target="_blank"}.

### Creare tipi di pubblico {#audiences-target}

In Adobe Target, devi creare i due tipi di pubblico in cui le persone che visitano la tua offerta verranno categorizzate per i diversi contenuti da distribuire. Per ogni pubblico, aggiungi una regola per definire chi sarà in grado di visualizzare l’offerta.

1. Per creare un nuovo pubblico in Target, dalla scheda **[!UICONTROL Audiences]**, fai clic su **[!UICONTROL Create Audience]**.

   ![](assets/audiences_1.png)

1. Aggiungi un nome al pubblico.

   ![](assets/audiences_2.png)

1. Fare clic su **[!UICONTROL Add a rule]** e selezionare una categoria. La regola utilizza criteri specifici per eseguire il targeting dei visitatori. Puoi perfezionare le regole aggiungendo condizioni o creando nuove regole in altre categorie.

1. Segui la stessa procedura per i tipi di pubblico rimanenti.

### Creare un’attività Targeting esperienze {#creating-targeting-activity}

In Adobe Target, è necessario creare un’attività Targeting esperienza, definire le diverse esperienze e associarle alle offerte corrispondenti.

Innanzitutto devi definire il pubblico:

1. Per creare un&#39;attività Targeting esperienze, dalla scheda **[!UICONTROL Activities]**, fai clic su **[!UICONTROL Create Activity]** e quindi su **[!UICONTROL Experience Targeting]**.

   ![](assets/target_10.png)

1. Seleziona **[!UICONTROL Form]** come **[!UICONTROL Experience Composer]**.

1. Scegliere un pubblico facendo clic sul pulsante **[!UICONTROL Change audience]**.

   ![](assets/target_10_2.png)

1. Seleziona il pubblico creato nei passaggi precedenti.

   ![](assets/target_10_3.png)

1. Creare un&#39;altra esperienza facendo clic su **[!UICONTROL Add Experience Targeting]**.

Quindi aggiungi un contenuto per ogni pubblico:

1. Seleziona il nome della posizione scelto al momento dell’inserimento dell’offerta dinamica in Adobe Campaign.

   ![](assets/target_15.png)

1. Fare clic sul pulsante a discesa e selezionare **[!UICONTROL Change Redirect Offer]**.

   ![](assets/target_content.png)

1. Seleziona l’offerta di reindirizzamento creata in precedenza.

   ![](assets/target_content_2.png)

1. Segui gli stessi passaggi per la seconda esperienza.

La finestra **[!UICONTROL Target]** riepiloga l&#39;attività. Se necessario, puoi aggiungere altre esperienze.

![](assets/target_experience.png)

La finestra **[!UICONTROL Goal & Settings]** consente di personalizzare l&#39;attività impostando una priorità, un obiettivo o una durata.

La sezione **[!UICONTROL Reporting Settings]** consente di selezionare un&#39;azione e modificare i parametri che determineranno quando l&#39;obiettivo verrà raggiunto.

![](assets/target_experience_2.png)

## Anteprima e invio del messaggio {#preview-send-email}

In Adobe Campaign, ora puoi visualizzare in anteprima il messaggio e-mail e testarne il rendering su destinatari diversi.

Noterai che l’immagine cambia in base alle diverse esperienze create.

Ora puoi inviare la tua e-mail contenente un’offerta dinamica di Target.

![](assets/target_20.png)
