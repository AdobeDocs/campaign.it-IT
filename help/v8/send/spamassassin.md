---
product: campaign
title: SpamAssassin
description: Scopri come impostare il rilevamento di posta indesiderata con SpamAssassin
feature: Email, Deliverability
role: User
version: Campaign v8, Campaign Classic v7
exl-id: 8be6836d-f7dc-4199-b2b2-b6a9cac9d162
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: 50d1fd2e-0fc9-5627-bbc9-02dbc9d15e08
    internal-label: Email
  - id: 63876777-85c3-57e1-a2da-81f02956c63c
    internal-label: Deliverability
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%
---
# SpamAssassin{#spamassassin}

Adobe Campaign può essere configurato per funzionare con [SpamAssassin](https://spamassassin.apache.org){target="_blank"}, un servizio di terze parti utilizzato per il filtro della posta indesiderata. Ciò ti consente di valutare le e-mail per determinare se un messaggio corre il rischio di essere considerato come spam dagli strumenti anti-spam utilizzati al momento della ricezione.

SpamAssassin sfrutta una varietà di tecniche di rilevamento spam, tra cui:

* Rilevamento di spam basato su DNS e su checksum fuzzy
* Filtro bayesiano
* Programmi esterni
* Inserisce nell&#39;elenco Bloccati
* Database online

>[!NOTE]
>
>SpamAssassin deve essere installato e configurato nel server applicazioni Adobe Campaign. Per ulteriori informazioni, contatta il tuo rappresentante Adobe.
>
>Le regole che determinano se un elemento è spam o meno vengono gestite tramite SpamAssassin e possono essere modificate da un amministratore con privilegi.

## Utilizzare SpamAssassin in Campaign {#using-spamassassin}

Dopo aver creato la consegna e-mail e averne definito il contenuto, segui i passaggi indicati di seguito per valutare i rischi.

Per ulteriori informazioni sulla creazione e la progettazione di una consegna, consulta questa [pagina](defining-the-email-content.md).


1. Vai alla scheda **[!UICONTROL Preview]**.
1. Seleziona un destinatario per visualizzare l’anteprima della consegna.

   ![](assets/s_tn_del_preview_spamassassin_recipient.png)

   >[!NOTE]
   >
   >Se non selezioni un destinatario, non è possibile eseguire il controllo anti-spam.

1. Un messaggio di avvertenza fornisce il risultato del test. Se viene rilevato un livello di rischio elevato, viene visualizzato il seguente messaggio di avvertenza:

   ![](assets/s_tn_del_preview_spamassassin_ko.png)

1. Fare clic sul collegamento **[!UICONTROL More...]** accanto all&#39;avviso.
1. Seleziona la scheda **[!UICONTROL Anti-spam checking]**.
1. Andare alla sezione **[!UICONTROL Points / Rule / Description]** per visualizzare i motivi di questo rischio.

   ![](assets/s_tn_del_msg_spamassassin_ko.png)

>[!NOTE]
>
>Ogni volta che si fa clic su **[!UICONTROL Anti-spam checking]**, viene chiamato il servizio SpamAssassin e il messaggio viene nuovamente analizzato per rilevare la posta indesiderata. Assicurati di aver modificato il contenuto prima di eseguire di nuovo l’analisi anti-spam.
