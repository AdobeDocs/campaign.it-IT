---
product: campaign
title: Offerte su un canale in entrata
description: Offerte su un canale in entrata
feature: Interaction, Offers
version: Campaign v8, Campaign Classic v7
audience: interaction
content-type: reference
topic-tags: case-study
exl-id: 90afced3-465d-4370-8a33-51a7e4356135
TQID: 'https://experienceleague.adobe.com/HkXtRV9hn2hZSZyxx86o2muGafhdhWuLp-uYBe4xTaU'
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
source-wordcount: '2986'
ht-degree: 1%
---
# Offerte su un canale in entrata{#offers-on-an-inbound-channel}



## Presentazione di un’offerta a un visitatore anonimo {#presenting-an-offer-to-an-anonymous-visitor}

Il sito di Neobank vuole presentare sul proprio sito web un’offerta rivolta a visitatori non identificati che navigano nella pagina.

Per impostare questa interazione:

1. [Creare un ambiente anonimo](#creating-an-anonymous-environment)
1. [Creare spazi di offerta anonimi](#creating-anonymous-offer-spaces)
1. [Creare una categoria di offerta e un tema](#creating-an-offer-category-and-a-theme)
1. [Creare offerte anonime.](#creating-anonymous-offers)
1. [Configurare gli spazi dell’offerta web sul sito web](#configure-the-web-offer-space-on-the-website)

### Creazione di un ambiente anonimo {#creating-an-anonymous-environment}

Segui la procedura descritta in [Creazione di un ambiente di offerta](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/offers/interaction-settings/interaction-env#create-an-offer-environment){target="_blank"} (documentazione di Campaign v8) per creare l&#39;ambiente anonimo in base alle dimensioni di **Visitatori**.

Otterrai una struttura ad albero contenente il nuovo ambiente:

![Offre struttura struttura e ambiente - Proprietà dei visitatori, un ambiente per le interazioni anonime in ingresso](assets/offer_env_anonymous_003.png)

### Creazione di spazi di offerta anonimi {#creating-anonymous-offer-spaces}

1. Nell&#39;ambiente anonimo (**Visitatori**) passare al nodo **[!UICONTROL Administration]** > **[!UICONTROL Spaces]**.
1. Fare clic su **[!UICONTROL New]** per creare i canali di chiamata.

   ![Pulsante Nuovo nell&#39;elenco Spazi di offerta che apre la finestra di dialogo Nuovo spazio di offerta con la scheda Proprietà](assets/offer_inbound_anonymous_example_010.png)

   >[!NOTE]
   >
   >Lo spazio viene collegato automaticamente all’ambiente anonimo.

1. Cambia l&#39;etichetta e seleziona il canale **[!UICONTROL Inbound Web]**. Selezionare anche la casella **[!UICONTROL Enable unitary mode]**.

   ![Finestra di dialogo dello spazio delle offerte con l&#39;etichetta Offerta Anonimo Web Premium e il canale Web in entrata selezionato](assets/offer_inbound_anonymous_example_006.png)

1. Seleziona i campi di contenuto dell’offerta utilizzati per lo spazio e specificali come richiesto selezionando la casella pertinente.

   In questo modo, eventuali offerte a cui manca uno dei seguenti elementi non saranno idonee per questo spazio:

   * Titolo
   * Contenuto HTML
   * URL immagine
   * URL di destinazione

   ![Seleziona una finestra di dialogo di espressione con il campo Titolo scelto come campo del contenuto dell&#39;offerta dello spazio dell&#39;offerta](assets/offer_inbound_anonymous_example_030.png)

1. Modifica la funzione di rendering di HTML, ad esempio come segue:

   ```javascript
   function (imageUrl, targetUrl, shortContent, htmlSource){
         var html = "<p><b>" + shortContent + "</b></p>";
         html += "<p>" + htmlSource + "</p>";
         html += "<a _urlType='11' href='" + targetUrl + "'><img src='" + encodeURI(imageUrl) + "'/></a>";
         return html;
       }   
   ```

   >[!IMPORTANT]
   >
   >La funzione di rendering deve denominare i campi utilizzati per lo spazio nell’ordine in cui erano stati precedentemente selezionati in modo che le offerte vengano visualizzate correttamente.

   ![Collegamento Modifica funzioni che apre la scheda HTML per il rendering dello spazio delle offerte per sovraccaricare la funzione di rendering](assets/offer_inbound_anonymous_example_031.png)

1. Salva lo spazio dell’offerta.

### Creazione di una categoria di offerta e di un tema {#creating-an-offer-category-and-a-theme}

1. Passa al nodo **[!UICONTROL Offer catalog]** all&#39;interno dell&#39;ambiente appena creato.
1. Fare clic con il pulsante destro del mouse sul nodo **[!UICONTROL Offer catalog]** e selezionare **[!UICONTROL Create a new 'Offer category' folder]**.

   Denomina la nuova categoria, **Prodotti finanziari** ad esempio.

1. Vai alla scheda **[!UICONTROL Eligibility]** della categoria e immetti **finanziamento** come tema, quindi salva le modifiche.

   ![Scheda Idoneità categoria offerta con il campo Temi impostato su Finanziamento](assets/offer_inbound_anonymous_example_023.png)

### Creazione di offerte anonime {#creating-anonymous-offers}

1. Passa alla categoria appena creata.
1. Fai clic su **[!UICONTROL New]**.

   ![Nuovo pulsante nell&#39;elenco Offerte della categoria Prodotti finanziari che apre la finestra di dialogo Nuova offerta](assets/offer_inbound_anonymous_example_013.png)

1. Seleziona il modello di offerta anonimo predefinito o un modello creato in precedenza.

   ![Elenco modelli di offerta con nuova offerta anonima (emptyAnonOffer) e nuova offerta (emptyOfferVisitor)](assets/offer_inbound_anonymous_example_014.png)

1. Modifica l’etichetta e salva l’offerta.

   ![Finestra di dialogo per una nuova offerta anonima con etichetta Anonymous Premium Offer #1 prima del salvataggio](assets/offer_inbound_anonymous_example_015.png)

1. Passa alla scheda **[!UICONTROL Eligibility]** e specifica il peso delle offerte in base ai relativi contesti di applicazione.

   In questo esempio, l’offerta è configurata per essere visualizzata nella home page del sito come priorità fino alla fine dell’anno.

   ![Scheda Idoneità offerta con peso dell&#39;offerta e finestra di dialogo Peso limitata allo spazio anonimo dell&#39;offerta](assets/offer_inbound_anonymous_example_016.png)

1. Passa alla scheda **[!UICONTROL Content]** e definisci il contenuto dell&#39;offerta.

   >[!NOTE]
   >
   >È possibile selezionare **[!UICONTROL Content definitions]** per visualizzare l&#39;elenco degli elementi necessari per lo spazio Web.

   ![Scheda Contenuto offerta con titolo, URL di destinazione, URL immagine e contenuto HTML per la prima offerta anonima](assets/offer_inbound_anonymous_example_017.png)

1. Crea una seconda offerta.

   ![Scheda Contenuto della seconda offerta anonima con titolo, URL di destinazione e contenuto HTML](assets/offer_inbound_anonymous_example_018.png)

1. Passa alla scheda **[!UICONTROL Eligibility]** e applica lo stesso peso della prima offerta.
1. Esegui il ciclo di approvazione per ogni offerta per renderla disponibile nell’ambiente online, insieme ai relativi spazi dell’offerta approvati.

### Configurare lo spazio dell’offerta web sul sito web {#configure-the-web-offer-space-on-the-website}

Per rendere visibili sul sito web le offerte appena configurate, inserisci il codice JavaScript nella pagina HTML del sito per richiamare il motore di interazione (per ulteriori informazioni, consulta [Informazioni sui canali in entrata](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/offers/inbound/interaction-present-offers){target="_blank"} (documentazione di Campaign v8).

1. Vai alla pagina HTML e inserisci un attributo @id con un valore corrispondente al nome interno dello spazio delle offerte anonimo creato in precedenza (fai riferimento a [Creazione di spazi delle offerte anonimi](#creating-anonymous-offer-spaces)), preceduto da **i_**.

   ![Origine pagina HTML con div il cui ID è i_SPC3, il nome interno dello spazio dell&#39;offerta preceduto da i_](assets/offer_inbound_anonymous_example_019.png)

1. Inserisci l’URL della chiamata.

   ![Chiamata tramite script di HTML a interfaceProject.js con env=liveVisitor e th=parametri di finanziamento evidenziati](assets/offer_inbound_anonymous_example_020.png)

   Le caselle URL blu sopra corrispondono al nome dell&#39;istanza, al nome interno dell&#39;ambiente (fare riferimento a [Creazione di un ambiente anonimo](#creating-an-anonymous-environment)) e al tema collegato alla categoria ([Creazione di una categoria di offerta e di un tema](#creating-an-offer-category-and-a-theme)). Quest&#39;ultimo è facoltativo.

Quando un visitatore accede alla home page del sito Web, le offerte con il tema **finanziamento** vengono visualizzate come configurate nella pagina HTML.

![La home page di Neobank con il blocco Offerte speciali visualizza un&#39;offerta anonima nella barra laterale](assets/offer_inbound_anonymous_example_022.png)

Un utente che visita la pagina più volte visualizzerà una o più offerte della categoria, poiché a entrambe è stato assegnato lo stesso peso.

## Passaggio a un ambiente anonimo in caso di contatti non identificati {#switching-to-an-anonymous-environment-in-case-of-unidentified-contacts}

La società Neobank desidera creare offerte di marketing per due diversi target. Vuole mostrare offerte generiche per i suoi browser anonimi del sito web. Se uno di questi utenti risulta essere un cliente con gli identificatori forniti da Neobank, l’azienda desidera che ricevano offerte personalizzate non appena effettuano l’accesso.

Questo caso di studio si basa sullo scenario seguente:

1. Un visitatore naviga nel sito web di Neobank senza effettuare l’accesso.

   ![Home page di Neobank con il pannello di accesso visualizzato a un visitatore non connesso](assets/offer_inbound_fallback_example_050.png)

   Nella pagina vengono visualizzate tre offerte anonime: due **offerte migliori** per i prodotti Neobank e un&#39;offerta da un partner Neobank.

   ![Pagina Neobank con tre offerte anonime: due offerte di Proposta d&#39;acquisto e un&#39;offerta per i partner](assets/offer_inbound_fallback_example_051.png)

1. L’utente, un cliente di Neobank, accede con le proprie credenziali.

   ![Pannello di accesso Neobank con le credenziali immesse prima dell&#39;accesso dell&#39;utente](assets/offer_inbound_fallback_example_052.png)

   Vengono visualizzate tre offerte personalizzate.

   ![Pagina Neobank dopo l&#39;accesso con tre offerte personalizzate evidenziate nel blocco Offerte speciali](assets/offer_inbound_fallback_example_053.png)

Per implementare questo caso di studio, devi disporre di due ambienti di offerta: uno per le interazioni anonime e uno con le offerte configurate in modo specifico per i contatti identificati. L’ambiente dell’offerta identificato verrà configurato per passare automaticamente all’ambiente dell’offerta anonimo se il contatto non è connesso e quindi non è identificato.

Applica i seguenti passaggi:

* Crea un catalogo di offerte specifiche per le interazioni in entrata anonime seguendo i passaggi seguenti:

  1. [Creazione di un ambiente per i contatti anonimi](#creating-an-environment-for-anonymous-contacts)
  1. [Configurazione degli spazi di offerta per l’ambiente anonimo](#configuring-offer-spaces-for-the-anonymous-environment)
  1. [Creazione di categorie di offerta in un ambiente anonimo](#creating-offer-categories-in-an-anonymous-environment)
  1. [Creazione di offerte per visitatori anonimi](#creating-offers-for-anonymous-visitors)

* Crea un catalogo di offerte specifiche per le interazioni in entrata identificate seguendo la procedura riportata di seguito.

  1. [Configurare gli spazi dell’offerta nell’ambiente identificato](#configure-the-offer-spaces-in-the-identified-environment)
  1. [Creazione di categorie di offerta in un ambiente identificato](#creating-offer-categories-in-an-identified-environment)
  1. [Creazione di offerte personalizzate](#creating-personalized-offers)

* Configura la chiamata al motore di offerta:

  1. [Configurazione degli spazi dell’offerta sulla pagina web](#configuring-offer-spaces-on-the-web-page)
  1. [Specifica delle impostazioni avanzate degli spazi dell’offerta identificati](#specifying-the-advanced-settings-of-the-identified-offer-spaces)

### Creazione di un ambiente per i contatti anonimi {#creating-an-environment-for-anonymous-contacts}

1. Crea un ambiente di offerta per le interazioni in entrata anonime tramite l&#39;assistente per la mappatura della consegna (**Visitatore**). Per ulteriori informazioni, consulta [Creazione di un ambiente di offerta](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/offers/interaction-settings/interaction-env#create-an-offer-environment){target="_blank"} (documentazione di Campaign v8).

   ![Offre struttura struttura e ambiente - Proprietà dei visitatori, un ambiente per le interazioni anonime in ingresso](assets/offer_env_anonymous_003.png)

### Configurazione degli spazi di offerta per l’ambiente anonimo {#configuring-offer-spaces-for-the-anonymous-environment}

Le offerte che devono essere presentate sul sito Web appartengono a due diverse categorie: **Proposta d&#39;acquisto** e **Partner**. In questo esempio, creeremo uno spazio di offerta specifico per ogni categoria.

Per creare lo spazio dell&#39;offerta in modo che corrisponda alla categoria **Offerta migliore**, applica il seguente processo:

1. Nella struttura Adobe Campaign, vai all’ambiente anonimo appena creato e aggiungi uno spazio di offerta.

   ![Elenco spazi offerta nell&#39;ambiente - Ambiente di progettazione visitatori, con il pulsante Nuovo evidenziato](assets/offer_inbound_fallback_example_023.png)

1. Crea un nuovo spazio di tipo **[!UICONTROL Inbound web]**.

   ![Menu a discesa Canale nuovo spazio offerte con Web in entrata selezionato](assets/offer_inbound_fallback_example_024.png)

1. Immetti un&#39;etichetta per l&#39;offerta: **Migliore offerta anonima per il Web** per esempio.
1. Aggiungi i campi di contenuto dell’offerta utilizzati per questo spazio dell’offerta e configura le funzioni di rendering.

   ![Offerta anonima per il Web con canale Web in entrata, campi di contenuto e funzione di rendering di HTML](assets/offer_inbound_fallback_example_025.png)

   >[!IMPORTANT]
   >
   >La funzione di rendering deve denominare i campi utilizzati per lo spazio nell’ordine in cui erano stati precedentemente selezionati in modo che le offerte vengano visualizzate correttamente.

1. Utilizza lo stesso processo per creare uno spazio dell&#39;offerta del canale web in entrata corrispondente alla categoria **Partner**.

   ![Partner Web di Offer Space anonimo con canali Web in entrata, contenuti HTML e campi URL immagine](assets/offer_inbound_fallback_example_026.png)

### Creazione di categorie di offerta in un ambiente anonimo {#creating-offer-categories-in-an-anonymous-environment}

Inizia creando due categorie di offerta: la categoria **Proposta d&#39;acquisto** e la categoria **Partner**. Ogni categoria conterrà due offerte per i contatti anonimi.

1. Vai a **[!UICONTROL Offer catalog]** nell&#39;ambiente anonimo appena creato.
1. Aggiungi una cartella **[!UICONTROL Offer category]** con **Proposta d&#39;acquisto** come etichetta.

   ![Cartella delle categorie di offerte con etichetta Proposta d&#39;acquisto in Ambiente - Visitatori nella struttura ad albero della progettazione](assets/offer_inbound_fallback_example_027.png)

1. Crea una seconda categoria con **Partner** come etichetta.

   ![Partner della categoria di offerta creato accanto a Proposta d&#39;acquisto in Ambiente - Visitatore](assets/offer_inbound_fallback_example_028.png)

### Creazione di offerte per visitatori anonimi {#creating-offers-for-anonymous-visitors}

Ora creeremo due offerte in ciascuna delle categorie create in precedenza.

1. Vai alla categoria **Offerta migliore** e crea un&#39;offerta anonima.

   ![Finestra di dialogo per una nuova offerta anonima nella categoria Proposta d&#39;acquisto con etichetta Proposta d&#39;acquisto #1](assets/offer_inbound_fallback_example_029.png)

1. Passa alla scheda **[!UICONTROL Eligibility]** e specifica il peso delle offerte in base ai relativi contesti di applicazione.

   ![Scheda Idoneità dell&#39;offerta migliore #1 offerta anonima con pesi per la home page e il salvataggio della pagina](assets/offer_inbound_fallback_example_030.png)

1. Passa alla scheda **[!UICONTROL Content]** e definisci il contenuto dell&#39;offerta.

   ![Scheda Contenuto di una Proposta d&#39;acquisto anonima con titolo Conto bancario Neobank e contenuto HTML](assets/offer_inbound_fallback_example_032.png)

1. Crea una seconda offerta nella categoria **Proposta d&#39;acquisto**.

   ![Scheda Contenuto della seconda Proposta d&#39;acquisto con titolo Neobank Home Insurance and HTML content](assets/offer_inbound_fallback_example_031.png)

1. Vai alla categoria **Partner** e crea un&#39;offerta anonima.
1. Passa alla scheda **[!UICONTROL Content]** e definisci il contenuto dell&#39;offerta.

   ![Scheda Contenuto dell&#39;offerta partner anonima con titolo Neo Weekly e contenuto HTML](assets/offer_inbound_fallback_example_033.png)

1. Passa alla scheda **[!UICONTROL Eligibility]** e specifica il peso delle offerte in base ai relativi contesti di applicazione.

   ![Scheda Idoneità dell&#39;offerta multimediale Partner anonima con un peso di 3 per la homepage](assets/offer_inbound_fallback_example_034.png)

1. Crea una seconda offerta per la categoria **Partner**.

   ![Scheda Contenuto della seconda offerta partner anonima con titolo Escursione e contenuto HTML](assets/offer_inbound_fallback_example_035.png)

1. Passa alla scheda **[!UICONTROL Eligibility]** e applica lo stesso peso applicato alla prima offerta di questa categoria in modo che le offerte vengano visualizzate in successione sul sito Web.

   ![Scheda Idoneità della seconda offerta partner con un peso di 3 per la home page, uguale alla prima](assets/offer_inbound_fallback_example_036.png)

1. Esegui il ciclo di approvazione per ogni offerta per iniziare a renderla live. Quando approvi il contenuto, attiva lo spazio dell&#39;offerta **Partner** o **Proposta d&#39;acquisto**, in base all&#39;offerta.

### Configurare gli spazi dell’offerta nell’ambiente identificato {#configure-the-offer-spaces-in-the-identified-environment}

Le offerte che presenterai sul sito Web provengono da due diverse categorie: **Proposta d&#39;acquisto** e **Partner**. In questo esempio, vogliamo creare uno spazio specifico per ogni categoria.

Per creare i due spazi dell’offerta, applica la stessa procedura applicata agli spazi dell’offerta anonimi. Consulta [Configurazione degli spazi dell&#39;offerta per l&#39;ambiente anonimo](#configuring-offer-spaces-for-the-anonymous-environment).

1. Nella struttura Adobe Campaign, vai all&#39;ambiente appena creato e aggiungi **spazi di offerta migliore** e **spazi di offerta partner**.
1. Applica il processo descritto in [Configurazione degli spazi di offerta per l&#39;ambiente anonimo](#configuring-offer-spaces-for-the-anonymous-environment).

   ![Elenco degli spazi dell&#39;offerta dell&#39;ambiente - Ambiente di progettazione destinatari, con lo spazio identificato dal partner Web aperto](assets/offer_inbound_fallback_example_005.png)

1. Seleziona l’opzione **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]**.

   ![Ripristina un ambiente anonimo se non sono stati identificati singoli utenti, opzione selezionata nello spazio delle offerte](assets/offer_inbound_fallback_example_006.png)

1. Utilizzando l&#39;elenco a discesa, selezionare lo spazio delle offerte Web anonimo creato in precedenza (fare riferimento a [Configurazione degli spazi delle offerte per l&#39;ambiente anonimo](#configuring-offer-spaces-for-the-anonymous-environment)).

   ![Elenco a discesa degli spazi dell&#39;offerta anonima per lo spazio anonimo collegato, con Partner Web anonimo selezionato](assets/offer_inbound_fallback_example_007.png)

### Specifica delle impostazioni avanzate degli spazi dell’offerta identificati {#specifying-the-advanced-settings-of-the-identified-offer-spaces}

In questo esempio, l’identificazione dei contatti avviene tramite l’indirizzo e-mail nel database di Adobe Campaign. Per aggiungere l’e-mail del destinatario allo spazio, applica il seguente processo:

1. Nell’ambiente identificato, passa alla cartella dello spazio delle offerte.
1. Seleziona lo spazio dell&#39;offerta **Proposta d&#39;acquisto** e fai clic su **[!UICONTROL Advanced parameters]**.

   ![Spazio per la migliore offerta Web identificato con il collegamento Parametri avanzati che apre la scheda Identificazione di Target](assets/offer_inbound_fallback_example_044.png)

1. Nella scheda **[!UICONTROL Target identification]**, fai clic su **[!UICONTROL Add]**.

   ![Parametri avanzati Scheda di identificazione di destinazione con il pulsante Aggiungi per un percorso chiave](assets/offer_inbound_fallback_example_046.png)

1. Fare clic su **[!UICONTROL Edit expression]**, passare alla tabella dei destinatari e selezionare il campo **[!UICONTROL Email]**.

   ![Modifica selettore campo espressione nella tabella dei destinatari con il campo E-mail selezionato](assets/offer_inbound_fallback_example_047.png)

1. Fai clic su **[!UICONTROL OK]** per chiudere la finestra **[!UICONTROL Advanced parameters]** e completare la configurazione dello spazio dell&#39;offerta **Proposta d&#39;acquisto**.
1. Applica lo stesso processo per lo spazio dell&#39;offerta **Partner**.

   ![Spazio identificato dal partner Web con il percorso della chiave @email impostato nella scheda Identificazione destinazione dei parametri avanzati](assets/offer_inbound_fallback_example_048.png)

### Creazione di categorie di offerta in un ambiente identificato {#creating-offer-categories-in-an-identified-environment}

Stiamo per creare due categorie separate: la categoria **Proposta d&#39;acquisto** e la categoria **Partner**, ciascuna con due offerte personalizzate.

1. Passare al nodo **[!UICONTROL Offer catalogs]** nell&#39;ambiente identificato.
1. Come nell&#39;ambiente anonimo, aggiungi due cartelle **[!UICONTROL Offer category]** con **Proposta d&#39;acquisto** e **Partner** come etichette.

   ![Ambiente - Struttura del destinatario con categorie di offerte e partner, con mirroring dell&#39;ambiente dei visitatori](assets/offer_inbound_fallback_example_009.png)

### Creazione di offerte personalizzate {#creating-personalized-offers}

Vogliamo creare due offerte personalizzate per ogni categoria, ovvero quattro offerte.

1. Vai alla categoria **Offerta migliore** e crea una prima offerta personalizzata.

   ![Finestra di dialogo Nuova offerta nella categoria Migliore offerta identificata utilizzando il modello Nuova offerta (emptyOffer), etichetta Proposta d&#39;acquisto #1](assets/offer_inbound_fallback_example_011.png)

1. Passa alla scheda **[!UICONTROL Eligibility]** e specifica il peso delle offerte in base ai relativi contesti di applicazione.

   ![Scheda Idoneità della prima Proposta d&#39;acquisto identificata con i pesi per la home page di Neobank e la pagina Banking](assets/offer_inbound_fallback_example_012.png)

1. Passa alla scheda **[!UICONTROL Content]** e definisci il contenuto dell&#39;offerta.

   ![Scheda Contenuto della Proposta d&#39;acquisto personalizzata con titolo Conto bancario Neobank e offerta per clienti Neobank](assets/offer_inbound_fallback_example_013.png)

1. Crea una seconda offerta nella categoria **Proposta d&#39;acquisto**.

   ![Scheda Contenuto della seconda Proposta d&#39;acquisto personalizzata, Neobank Home Insurance, con rimborso per i clienti esistenti](assets/offer_inbound_fallback_example_014.png)

1. Vai alla categoria **Partner** e crea un&#39;offerta personalizzata.

   ![Scheda Contenuto dell&#39;offerta personalizzata per i partner con titolo Escursione e uno sconto del 20% per i clienti Neobank](assets/offer_inbound_fallback_example_015.png)

1. Passa alla scheda **[!UICONTROL Eligibility]** e specifica il peso delle offerte in base ai relativi contesti di applicazione.

   ![Scheda Idoneità dell&#39;offerta di viaggio per i partner con un peso di 5 per la home page di Neobank](assets/offer_inbound_fallback_example_016.png)

1. Crea una seconda offerta per la categoria **Partner**.

   ![Scheda Contenuto della seconda offerta per i partner, Neo Weekly, con uno sconto del 50% per i clienti Neobank](assets/offer_inbound_fallback_example_017.png)

1. Passa alla scheda **[!UICONTROL Eligibility]** e applica lo stesso peso applicato alla prima offerta di questa categoria in modo che le offerte vengano visualizzate in successione sul sito Web.
1. Esegui il ciclo di approvazione per ogni offerta per iniziare ad aggiornarla. Durante l&#39;approvazione del contenuto, attiva gli spazi dell&#39;offerta **Partner** o **Proposta d&#39;acquisto**.

### Configurazione degli spazi dell’offerta sulla pagina web {#configuring-offer-spaces-on-the-web-page}

Il sito Web della società Neobank dispone di tre spazi per le offerte: due per le offerte relative alla banca della categoria **Proposta d&#39;acquisto** e uno per le offerte della categoria **Partner**.

![Home page di Neobank per un utente connesso con due frame di offerta migliore e un frame di offerta partner in Offerte speciali](assets/offer_inbound_fallback_example_038.png)

Per configurare questi spazi dell’offerta sulla pagina HTML del sito web, applica la procedura seguente:

1. Nel contenuto della pagina HTML, inserisci tre

   elementi con un attributo @id il cui valore ci consentirà di richiamare le offerte nei vari spazi di offerta del sito web.

   ![Origine pagina HTML con divs ContBO1, ContBO2 e ContPtn che definiscono i tre spazi dell&#39;offerta](assets/offer_inbound_fallback_example_039.png)

1. Quindi inserisci lo script per la definizione dei valori degli attributi.

   ![Script che definisce i divInterazione per ContBO1, ContBO2 e ContPtn con i relativi spazi e categorie](assets/offer_inbound_fallback_example_040.png)

   In questo esempio, **ContBO1** e **ContBO2** ricevono il valore **OsWebBestOfferIdentified**, ovvero il nome interno dello spazio dell&#39;offerta **Migliore offerta** creato in precedenza nell&#39;ambiente identificato. I valori **CatBestOffer** e **CatBestOfferAnonym** corrispondono al nome interno delle categorie **Best Offer** per gli ambienti anonimi e identificati.

   ![Spazio dell&#39;offerta migliore OSWebBestOfferIdentified e categorie dell&#39;offerta migliore degli ambienti identificati e anonimi](assets/offer_inbound_fallback_example_041.png)

   Analogamente, **ContPtn** riceve il valore **OSWebPartnerIdentified**, che corrisponde al nome interno dello spazio dell&#39;offerta **Partner** creato nell&#39;ambiente identificato. **CatPartner** e **CatPartnerAnonym** corrispondono al nome interno delle categorie **Partner** per gli ambienti anonimi e identificati.

   ![Spazio partner OSWebPartnerIdentified e i valori delle categorie CatPartner e CatPartnerAnonym nello script](assets/offer_inbound_fallback_example_042.png)

1. Assegna le informazioni che ti consentiranno di identificare la persona che accede al sito Neobank nella variabile **interfaceTarget**.

   ![variabile interfaceTarget impostata per l&#39;indirizzo e-mail della persona che effettua l&#39;accesso, nello script della pagina](assets/offer_inbound_fallback_example_043.png)

   L’identificazione della persona può essere basata su un cookie del browser, un parametro di lettura nell’URL, nell’e-mail o nell’identificatore della persona. Se viene utilizzato un campo della tabella dei destinatari diverso dalla chiave primaria, deve essere definito nei parametri avanzati dello spazio (fare riferimento a [Specifica delle impostazioni avanzate degli spazi dell&#39;offerta identificati](#specifying-the-advanced-settings-of-the-identified-offer-spaces)).

1. Inserisci l’URL della chiamata.

   ![Chiamata script a interfaceProject.js con env=EnvNeobankIdnRecip, nome interno dell&#39;ambiente identificato](assets/offer_inbound_fallback_example_049.png)

   L&#39;URL contiene **EnvNeobankIdnRecip**, il nome interno dell&#39;ambiente identificato.

Quando apri la pagina web, lo script consente di richiamare il motore di interazione per visualizzare il contenuto delle offerte negli spazi pertinenti della pagina web. In una singola chiamata al server Adobe Campaign, il motore determina l’ambiente, lo spazio dell’offerta e le categorie da selezionare.

In questo esempio, il motore riconosce l&#39;ambiente identificato (**EnvNeobankIdnRecip**). Identifica lo spazio dell&#39;offerta (**OSWebBestOfferIdentified**) e la categoria **Proposta d&#39;acquisto** (**CatBestOffer**) per la prima e la seconda offerta sulla pagina Web, nonché lo spazio dell&#39;offerta (**OSWebPartnerIdentified**) e la categoria **Partner** (**CatPartner**) per la terza offerta sul sito.

Se il motore non è in grado di identificare il destinatario, passa agli spazi di offerta anonimi a cui si fa riferimento negli spazi di offerta identificati e alle categorie anonime (**CatPartner** e **CatPartnerAnonym**) come specificato nello script.
