---
product: campaign
title: Offerte su un canale in uscita
description: Offerte su un canale in uscita
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 77fee343-09d1-4d60-be43-efe02953a70c
TQID: 'https://experienceleague.adobe.com/WGoYaHNR13J47UVmKpHRSm9aw0T8ZrvHUl9zGXezQBU'
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
source-git-commit: 8bfb312d62f56f19899a83de6b0dd58c56e04ab2
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 1%
---
# Offerte su un canale in uscita{#offers-on-an-outbound-channel}



## Consegna delle offerte e-mail {#email-offer-delivery}

Nel nostro database, c&#39;è una categoria di offerte di viaggio in Africa. L’idoneità, i contesti e le rappresentazioni di ogni offerta sono stati configurati. Ora vogliamo creare una campagna per presentare le nostre offerte via e-mail.

1. Crea una campagna di marketing e un flusso di lavoro di targeting.

   ![Flusso di lavoro di targeting della campagna Viaggi in Africa: attività cartella, consegna, deduplicazione e due attività di aggiornamento elenco](assets/offer_delivery_example_001.png)

1. Modificare la consegna e-mail e fare clic sull&#39;icona **[!UICONTROL Offers]**.

   ![Consegna e-mail con l&#39;icona Offerte che apre la finestra Gestione offerte, le opzioni di selezione delle offerte e il campo Spazio offerte](assets/offer_delivery_example_002.png)

1. Scegli lo spazio e-mail per l’ambiente delle offerte che corrisponde alle festività.

   ![Finestra Gestione delle offerte con l&#39;elenco Spazio offerte che mostra gli spazi e-mail disponibili, inclusi i percorsi di abbonati](assets/offer_delivery_example_003.png)

1. Scegli la categoria che contiene le offerte di viaggio Africa.

   ![Finestra Gestione delle offerte con la struttura ad albero Categoria espansa in Catalogo offerte e Percorsi, categoria Africa evidenziata](assets/offer_delivery_example_004.png)

1. Imposta su due il numero di offerte nella consegna.

   ![Finestra di gestione delle offerte con categoria Africa e numero di proposte per messaggio impostato su 2](assets/offer_delivery_example_005.png)

1. Chiudi la finestra di gestione delle offerte e crea il contenuto della consegna.

   ![Editor di contenuti HTML per la consegna e-mail con viste di inclusione predefinite, pronto per le proposte di offerta](assets/offer_delivery_example_006.png)

1. Utilizza i menu per inserire una prima proposta di offerta e scegliere la funzione di rendering di HTML.

   ![Menu della barra degli strumenti del contenuto di HTML: Proposte, quindi Proposizione 1, Funzione di rendering e rendering di HTML](assets/offer_delivery_example_007.png)

1. Inserisci la seconda proposta di offerta.

   ![Invia per e-mail il contenuto di HTML con entrambe le proposte includi le righe utilizzando la visualizzazione di rendering/html, prima del collegamento di annullamento dell&#39;abbonamento](assets/offer_delivery_example_008.png)

1. Fai clic su **[!UICONTROL Preview]** per visualizzare l&#39;anteprima delle offerte nella consegna, quindi seleziona un destinatario per visualizzare l&#39;anteprima delle offerte così come verranno ricevute.

   ![Scheda Anteprima consegna che mostra l&#39;e-mail con il titolo, il testo e l&#39;immagine dell&#39;offerta Attraversamento del Sahara per un destinatario selezionato](assets/offer_delivery_example_009.png)

1. Salva la consegna e avvia il flusso di lavoro di targeting.
1. Apri la consegna e fai clic sulla scheda **[!UICONTROL Audit]** della consegna: puoi vedere che il motore di offerta ha selezionato le proposte da effettuare tra le varie offerte del catalogo.

   ![Scheda Audit della consegna Elenco delle proposte generate per offerta, ad esempio le offerte Piramidi e Sahara](assets/offer_delivery_example_010.png)

## Eseguire una simulazione di offerta {#perform-an-offer-simulation}

1. Nella scheda **[!UICONTROL Profiles and Targets]**, fai clic sul collegamento **[!UICONTROL Simulations]**, quindi sul pulsante **[!UICONTROL Create]**.

   ![Elenco simulazioni con il pulsante Crea che apre la finestra di dialogo Nuova simulazione offerta con modello, etichetta e cartella](assets/offer_simulation_001.png)

1. Scegli un’etichetta e specifica le impostazioni di esecuzione, se necessario.

   ![Finestra di dialogo per la simulazione delle nuove offerte con gli abbonati a 1 anno di etichetta, la cartella Simulazioni e le impostazioni di esecuzione](assets/offer_simulation_example_002.png)

1. Salva la simulazione. Viene quindi aperta in una nuova scheda.

   ![Dashboard di simulazione di abbonati di 1 anno con la scheda Modifica e un pulsante Avvia simulazione](assets/offer_simulation_example_003.png)

1. Fare clic sulla scheda **[!UICONTROL Edit]**, quindi su **[!UICONTROL Scope]**.

   ![Scheda Modifica simulazione, sezione Ambito, con ambiente o categoria, spazio dell&#39;offerta, temi, data di contatto e proposte](assets/offer_simulation_example_004.png)

1. Scegli la categoria per la quale vuoi simulare le offerte.

   ![Elenco di ambienti o categorie espanso in Offerte - progettazione e catalogo di offerte, con la categoria Viaggi selezionata](assets/offer_simulation_example_005.png)

1. Scegli lo spazio dell’offerta da utilizzare per la simulazione.

   ![Elenco spazi offerte nella categoria Viaggi che offre direct mailing e posta elettronica (ambiente - destinatario)](assets/offer_simulation_example_006.png)

1. Inserire le date di validità. Immettere almeno una data di inizio. Questo consente al motore di offerta di filtrare le offerte e scegliere quelle valide in una determinata data.
1. Se necessario, specifica uno o più temi per limitare il numero di offerte a quelle che contengono questa parola chiave nelle loro impostazioni.

   Nel nostro esempio, la categoria **Viaggi** contiene due sottocategorie con due temi separati. Eseguire una simulazione per le offerte con il tema **Clienti>1 anno**.

   ![Sezione ambito con il tema Cliente > 1 anno immesso nel campo Temi per la categoria Viaggi](assets/offer_simulation_example_007.png)

1. Scegli i destinatari di cui desideri eseguire il targeting.

   ![Selezione guidata filtro di selezione di destinazione scelta Elenco di destinatari, quindi Elenco viaggiatori frequenti](assets/offer_simulation_example_008.png)

1. Configura il numero di offerte da inviare a ciascun destinatario.

   Nel nostro esempio, il motore di offerta sceglierà le 3 offerte con il peso più alto per ogni destinatario.

   ![Sezione ambito con numero di proposte impostato su 3 e query di destinazione nell&#39;elenco Consegna offerte speciali](assets/offer_simulation_example_009.png)

1. Salva le impostazioni, quindi fai clic su **[!UICONTROL Start]** nella scheda **[!UICONTROL Dashboard]** per eseguire la simulazione.

   ![Finestra di dialogo per simulazione avvio dashboard in cui viene richiesta una conferma, con il pulsante OK evidenziato](assets/offer_simulation_example_010.png)

1. Al termine della simulazione, consultare **[!UICONTROL Results]** per una suddivisione dettagliata delle proposte per offerta.

   Nel nostro esempio, il motore di offerta ha basato il raggruppamento dell’offerta su 3 proposte.

   ![Scheda Risultati simulazione con suddivisione delle proposte per offerte: dimensione di popolazione 30, numero di proposte 30](assets/offer_simulation_example_011.png)

1. Visualizza **[!UICONTROL Breakdown of offers by rank]** per visualizzare l&#39;elenco delle offerte selezionate dal motore di offerta.

   ![Rapporto Analisi stratificata delle offerte per rango con tabella di classificazione delle offerte per Viaggi negli Stati Uniti e Scoprire la Francia e grafico a torta](assets/offer_simulation_example_012.png)

1. Se necessario, è possibile modificare le impostazioni dell&#39;ambito ed eseguire nuovamente la simulazione facendo clic su **[!UICONTROL Start simulation]**.

   ![Finestra di dialogo per simulazione avvio dashboard in cui viene richiesta una conferma, con il pulsante OK evidenziato](assets/offer_simulation_example_010.png)

1. Per salvare i dati della simulazione, utilizza la cronologia o le funzioni di esportazione disponibili nel rapporto.

   ![Rapporto Analisi stratificata delle offerte per classifica con il menu Esporta e l&#39;icona Salva evidenziata](assets/offer_simulation_example_013.png)
