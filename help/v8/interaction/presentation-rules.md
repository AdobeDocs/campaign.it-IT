---
product: campaign
title: Regole di presentazione
description: Regole di presentazione
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: f9dd9ad6-48da-4a80-9405-109a433a1ed5
TQID: 'https://experienceleague.adobe.com/s2QV1BGLtUfyWg1BfYuryciF9STRK3HpIXNc6oQ0ATY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b6fcaf36-3bc4-4604-94f3-81b5d3f41ecf
    internal-label: Offer Management
  - id: 65702805-0026-5ca1-843a-144fa79f0883
    internal-label: Interaction
  - id: ea08db70-4682-59a2-9408-9aedd9548e07
    internal-label: Offers
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 0%
---
# Regole di presentazione{#presentation-rules}



## Creazione di una regola di presentazione {#creating-a-presentation-rule}

Nel nostro database, ci sono diverse offerte di viaggio per Europa, Africa, Stati Uniti e Canada. Vogliamo inviare offerte per un viaggio in Canada, ma se il destinatario rifiuta questo tipo di offerta, non vogliamo inviarle di nuovo.

Stiamo per configurare la nostra regola in modo che il viaggio in Canada venga offerto solo una volta per destinatario e non nuovamente se rifiutato.

1. Nella struttura Adobe Campaign, passa al nodo **[!UICONTROL Administration]** > **[!UICONTROL Campaign management]** > **[!UICONTROL Typology management]** > **[!UICONTROL Typology rules]**.
1. Crea una nuova regola di tipo **[!UICONTROL Offer presentation]**.

   ![Modulo di creazione regola di tipologia con l&#39;elenco dei tipi di regola aperto e la presentazione dell&#39;offerta selezionata](assets/offer_typology_example_001.png)

1. Se necessario, modifica l’etichetta e la descrizione.

   ![Scheda Generale della regola di tipologia con un&#39;etichetta, il tipo di presentazione dell&#39;offerta, il canale e-mail e una descrizione immessi](assets/offer_typology_example_002.png)

1. Scegliere l&#39;opzione **[!UICONTROL All channels]** per estendere la regola a tutti i canali.

   ![Elenco canali della regola di tipologia con tutti i canali selezionati](assets/offer_typology_example_003.png)

1. Fare clic sul collegamento **[!UICONTROL Edit expression]** e scegliere il nodo **[!UICONTROL Category]** come espressione.

   ![Finestra Query con la finestra di dialogo Seleziona un&#39;espressione aperta per scegliere il campo Categoria](assets/offer_typology_example_004.png)

1. Scegli la categoria corrispondente alla tua offerta di viaggio per il Canada e fai clic su **[!UICONTROL OK]** per chiudere la finestra della query.

   ![Query su categoria uguale a Canada, con la cartella Canada selezionata nell&#39;albero delle categorie dell&#39;offerta di viaggio](assets/offer_typology_example_005.png)

1. Nella scheda **[!UICONTROL Offer presentation]**, scegli le stesse dimensioni configurate nell&#39;ambiente.

   ![Scheda di presentazione delle offerte che mostra la dimensione di targeting e la dimensione di archiviazione, che corrispondono all&#39;ambiente](assets/offer_typology_example_006.png)

1. Specifica il periodo durante il quale la regola verrà applicata.

   ![Scheda Presentazione offerte con periodo scorrevole, campo Periodo considerato impostato su 10d](assets/offer_typology_example_007.png)

1. Limita la proposta a uno in modo che i destinatari che hanno già rifiutato un viaggio in Canada non ricevano un’altra offerta simile.

   ![Scheda Presentazione offerte con il campo Quantità massima di proposte impostato su 1](assets/offer_typology_example_008.png)

1. Selezionare il filtro **[!UICONTROL Offers for the same category]** per escludere tutte le offerte dalla categoria **Canada**.

   ![Elenco a discesa delle offerte nelle proposte da contare con offerte selezionate per la stessa categoria](assets/offer_typology_example_020.png)

1. Selezionare il filtro **[!UICONTROL Rejected propositions]** per tenere conto solo delle proposte rifiutate dal destinatario.

   ![Elenco a discesa dello stato della proposta in Proposte da contare con proposte rifiutate selezionate](assets/offer_typology_example_021.png)

1. Scegli i destinatari per i quali applicare questa regola.

   Nel nostro esempio, sceglieremo i **destinatari frequenti**.

   ![Modifica creazione guidata query filtro selezionando la cartella dei destinatari dei viaggiatori frequenti come destinazione della regola](assets/offer_typology_example_009.png)

1. Fai riferimento alla regola in una tipologia di offerta.

   ![Scheda Tipologie della regola con la finestra di dialogo Aggiungi tipologie in cui è elencata la tipologia Offerte selezionata](assets/offer_typology_example_013.png)

1. Vai all&#39;ambiente dell&#39;offerta (**Ambiente - Destinatario** in questo caso) e fai riferimento alla nuova tipologia appena creata utilizzando l&#39;elenco a discesa nella scheda **[!UICONTROL Eligibility]**.

   ![Scheda Idoneità dell&#39;ambiente delle offerte con l&#39;elenco della tipologia di presentazione delle offerte che mostra le offerte](assets/offer_typology_example_014.png)

## Applicazione della regola di presentazione {#applying-the-presentation-rule}

Esempio di applicazione della regola di tipologia creata in precedenza.

Desideriamo inviare una proposta di prima offerta appartenente alla categoria Canada. Se l’offerta viene rifiutata una volta da uno dei destinatari, non verrà più offerta loro.

1. Nella cartella dei destinatari **Viaggiatori frequenti**, scegli uno dei profili per verificare le offerte per le quali sono idonei: fai clic sulla scheda **[!UICONTROL Propositions]**, quindi sulla scheda **[!UICONTROL Preview]**.

   Nel nostro esempio, **Tim Ramsey** è idoneo per un&#39;offerta che fa parte della categoria **Americhe**.

   ![Scheda proposte destinatario, scheda secondaria Anteprima, elenco delle offerte idonee per la categoria Americhe](assets/offer_typology_example_015.png)

1. Inizia creando una consegna e-mail che eseguirà il targeting dei **destinatari frequenti** con le offerte.
1. Seleziona i parametri di richiamo del motore di offerta.

   Nel nostro esempio, viene scelta la categoria **Viaggi in America**, che contiene le sottocategorie **Canada** e **Stati Uniti**.

   ![Finestra di dialogo per la gestione delle offerte di una consegna e-mail con la categoria delle Americhe e 2 proposte per messaggio](assets/offer_typology_example_016.png)

1. Inserisci le offerte nel corpo del messaggio e invia la consegna. Per ulteriori informazioni, consulta [Informazioni sui canali in uscita](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/offers/interaction-send-offers){target="_blank"} (documentazione di Campaign v8).

   Il destinatario ha ricevuto l’offerta per la quale è idoneo.

1. Il destinatario ha rifiutato l’offerta canadese, come mostrato nella cronologia delle proposte.

   ![Cronologia delle proposte dei destinatari con l&#39;offerta snowmobile Canada nello stato Rifiutato](assets/offer_typology_example_018.png)

1. Controlla le offerte per le quali sono ora idonee.

   Possiamo vedere che non viene scelta alcuna offerta per il Canada.

   ![Scheda Anteprima destinatario con le offerte idonee a New York e Grand Canyon, senza offerta per il Canada](assets/offer_typology_example_019.png)
