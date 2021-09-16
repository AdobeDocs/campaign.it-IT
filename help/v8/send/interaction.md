---
title: Interazione campagna - Gestione delle offerte
description: Guida introduttiva alla gestione delle offerte
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
source-git-commit: f071fc227dac6d72873744ba56eb0b4b676de5dd
workflow-type: tm+mt
source-wordcount: '1213'
ht-degree: 1%

---

# Gestione dell’interazione e dell’offerta{#interaction-and-offer-management}

Campaign viene fornito con un modulo **Interazione** che ti consente di rispondere in tempo reale durante un’interazione con un determinato contatto (un cliente o un target) rendendoli una o più offerte adattate. Ad esempio, possono trattarsi di semplici messaggi di comunicazione, offerte speciali su uno o più prodotti o un servizio.

Puoi creare un catalogo di offerte che si interfaccia con i tuoi canali in uscita (e-mail, direct mailing, SMS) per selezionare l’offerta migliore da inviare a un contatto in un dato contesto. La selezione delle offerte migliori per un destinatario si basa su **regole di idoneità**. La selezione di un’offerta da un set di offerte pertinenti è determinata utilizzando regole di priorità. Le regole di presentazione delle offerte tengono conto della cronologia del contatto e aiutano a evitare che riceva la stessa offerta più volte.

L’interazione ti consente di creare e gestire un catalogo di offerte e di configurare le regole di idoneità e i temi dell’applicazione ad esse collegati. A seconda del canale scelto, il contenuto dell’offerta può essere personalizzato grazie a varie funzioni di rendering. Infine, puoi utilizzare il modulo di simulazione per calcolare l’impatto di una presentazione di offerta.

## Guida introduttiva alle offerte

I passaggi chiave da avviare sono elencati di seguito.

### Configurare la piattaforma

Prima di iniziare, in qualità di Campaign **Amministratore**, assicurati di aver eseguito le seguenti attività negli ambienti di progettazione:

1. Creare profili utente. [Ulteriori informazioni](interaction-operators.md)
1. (facoltativo) Crea un ambiente di offerta per ogni dimensione di targeting. [Ulteriori informazioni](interaction-env.md)
1. Crea regole di tipologia per ogni ambiente. [Ulteriori informazioni](interaction-offer.md#offer-presentation)
1. Crea spazi di offerta per ogni ambiente e configura funzioni di rendering. [Ulteriori ](interaction-offer-spaces.md)
informazioniSe lo spazio è definito da un canale unitario in modalità identificata, è necessario specificare i parametri avanzati per questo spazio.

### Creare e pubblicare il catalogo delle offerte {#managing-the-offer-catalog-}

In qualità di **Gestione offerte** devi eseguire le seguenti attività:

1. Crea categorie di offerte in ambienti di progettazione. [Ulteriori informazioni](interaction-offer-catalog.md#creating-offer-categories)
1. Creare offerte in ambienti di progettazione. [Ulteriori informazioni](interaction-offer.md)
1. Approva e pubblica offerte su uno o più spazi per renderli disponibili in ambienti live per il gestore delle consegne. [Ulteriori informazioni](interaction-offer.md#approve-offers)

### Utilizzo del catalogo delle offerte {#using-the-offer-catalog-}

In qualità di **responsabile consegna** devi eseguire le seguenti attività:

1. Creare una campagna.
1. Fai riferimento a un’offerta nella campagna o nella consegna. [Ulteriori informazioni](interaction-send-offers.md).


## Concetti e terminologia

Scopri i termini specifici dell’offerta e le relative indicazioni prima di iniziare.

* **** Gli ambienti includono un catalogo di offerte e spazi di offerta (hook). È necessario creare un ambiente mediante il targeting della dimensione.
Esistono due tipi di ambienti:

   * **Ambiente** di progettazione: le offerte vengono create nell’ambiente di progettazione, nonché nelle regole di tipologia e . Le regole di tipologia determinano le offerte da presentare (o meno) a una persona di destinazione. In questo ambiente viene inoltre definita la tabella dei singoli utenti interessati dalle offerte e la tabella per la memorizzazione di tutte le proposte di offerta. Il nodo **[!UICONTROL Design environment]** contiene sottocartelle per lo spazio di offerta, filtri predefiniti e categorie di offerte. Per ogni **[!UICONTROL Design environment]** esiste una **[!UICONTROL Live environment]** di sola lettura corrispondente, generata dallo stesso **[!UICONTROL Design environment]**.
   * **Ambiente** live: ambiente collegato a un  **[!UICONTROL Design environment]** che contiene offerte di sola lettura il cui contenuto e idoneità sono stati approvati tramite  **[!UICONTROL Design environment]**. Devono essere selezionati per essere inseriti in un messaggio.

* La **Area offerte** è una posizione (cartella) che definisce la posizione in cui viene esposta l&#39;offerta. Quando crei uno spazio di offerta, puoi specificare il canale, generare il contenuto dell’offerta utilizzando le funzioni di rendering, specificare l’ordine delle offerte e la relativa modalità: modalità unitaria e/o modalità batch (impostazione predefinita). Lo spazio di offerta è l’interfaccia tra il canale e il motore di offerta.
* Il **Catalogo offerte** è un set di offerte definite in Adobe Campaign che possono essere selezionate durante un&#39;interazione. Il catalogo è organizzato gerarchicamente con ogni nodo corrispondente a una categoria.
* Una **Categoria** è una cartella collegata al catalogo delle offerte in un ambiente che organizza le offerte in base alla natura, alla data di idoneità e al tema dell&#39;applicazione. Una categoria può contenere sottocategorie che ereditano tutte le caratteristiche della categoria padre. Le regole di idoneità possono essere definite per una categoria in modo da condividerle per diverse offerte.
* **Le** stesse applicazioni sono parole chiave definite nella categoria, che consentono di filtrare le offerte quando vengono presentate limitando la selezione delle offerte a una o due categorie.
* **Le** regole di idoneità sono vincoli applicati a un ambiente, categoria o offerta, relativi al periodo di validità, al target e al peso. Ti consentono di garantire che un’offerta sia in linea con il contatto mirato.

   Negli ambienti, le regole di idoneità includono le regole di presentazione applicate alle offerte e alle persone a cui eseguire il targeting.

   Nelle categorie, le regole di idoneità consentono di limitare la validità della categoria nel tempo, definire i temi dell’applicazione e determinare le persone a cui rivolgersi. Possono anche ricevere un peso moltiplicatore per un determinato periodo di tempo. Ciò ti consente di condividere le regole per le offerte in altre categorie e di semplificarne la gestione.

   Nelle offerte, le regole di idoneità ti consentono di limitare la validità delle offerte nel tempo e di determinare le persone a cui rivolgerti.

* L’ **Arbitrato** è l’azione di selezione delle offerte che verranno visualizzate in un ambiente (offerte idonee). L&#39;arbitraggio classifica le offerte per priorità in base ai criteri definiti nelle categorie, offerte e offerte di contesto.
* Un’ **interazione in uscita** chiama il motore di interazione da un elenco di contatti (utilizzato per la consegna di e-mail, direct mail, ecc.). Le stesse regole e procedure vengono applicate a ogni contatto. Questo tipo di interazione viene generalmente elaborato in modalità batch.
* La **Modalità batch** consente di selezionare l&#39;offerta migliore per un set di contatti. Le regole di idoneità/priorità vengono applicate a tutti i contatti del set. Questa modalità viene generalmente utilizzata per le interazioni in uscita.
* La **Modalità unitaria** consente di elaborare un singolo contatto alla volta. Questa modalità viene generalmente utilizzata per i messaggi transazionali.
* **Le** offerte ammissibili sono offerte che soddisfano i vincoli definiti a monte e che possono essere offerte in modo coerente a un target.
* **Le** regole di presentazione sono regole di tipologia a cui si fa riferimento nell’ambiente di offerta, che consentono di escludere alcune offerte tenendo conto della cronologia delle proposte.
* **** Applicare delle formule che consentono di calcolare con precisione la rilevanza di un’offerta, al fine di selezionare l’offerta più pertinente. I pesi sono definiti nelle offerte. Le offerte ammissibili sono prese in considerazione in ordine decrescente di peso.
* **La** funzione di rendering è definita nello spazio dell’offerta per creare la relativa rappresentazione dell’offerta in base agli attributi definiti nell’offerta. Esistono tre diverse modalità di rendering della funzione: HTML, XML e testo.
* **La** proposta di offerta è il risultato dell’azione che consiste nel presentare una o più offerte a un contatto in un dato spazio (ad esempio, banner su un sito web, e-mail o SMS). Questo risultato viene memorizzato nella tabella delle proposte di offerta. Tuttavia, non è obbligatorio salvare le proposte.
* **** Simulazione è un modulo che consente di testare la presentazione dell’offerta sui destinatari desiderati prima di inviare effettivamente le offerte.
* L’ **Anteprima** dell’offerta mostra l’offerta così come viene visualizzata nella relativa cartella. È accessibile dalla finestra delle impostazioni dell’offerta o dal profilo del contatto.
* **I** filtri predefiniti sono regole di filtro che possono tenere conto dei parametri delle offerte (ad esempio, un codice di offerta). Possono essere riutilizzati dopo la creazione delle offerte.
* Una **rappresentazione dell&#39;offerta** è un&#39;informazione utilizzata dal canale per visualizzare l&#39;offerta. La rappresentazione dell’offerta può essere creata dalla funzione di rendering dello spazio su cui l’offerta è rappresentata o inserita direttamente nell’interfaccia (ad esempio, nel blocco HTML). Un&#39;offerta può essere rappresentata da uno spazio.
