---
title: Interazione campagna - Gestione delle offerte
description: Guida introduttiva alla gestione delle offerte
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '1608'
ht-degree: 1%

---

# Gestione delle interazioni in tempo reale

Campaign viene fornito con un **Interazione** modulo che consente di rispondere in tempo reale durante un&#39;interazione con un determinato contatto proponendo loro una o più offerte specifiche. Queste offerte possono essere semplici messaggi di comunicazione, offerte speciali su uno o più prodotti o un servizio.

Puoi creare un catalogo di offerte che si interfaccia con i tuoi canali in uscita (e-mail, direct mailing, SMS) per selezionare l’offerta migliore da inviare a un contatto in un dato contesto. La selezione dell&#39;offerta migliore per un destinatario si basa su **regole di idoneità**. La selezione di un’offerta da un set di offerte pertinenti è determinata utilizzando regole di priorità. Le regole di presentazione delle offerte tengono conto della cronologia del contatto e aiutano a evitare che riceva la stessa offerta più volte.

L’interazione ti consente di creare e gestire un catalogo di offerte e di configurare le regole di idoneità e i temi dell’applicazione ad esse collegati. A seconda del canale scelto, il contenuto dell’offerta può essere personalizzato grazie a varie funzioni di rendering. Infine, puoi utilizzare il modulo di simulazione per calcolare l’impatto di una presentazione di offerta.

![](assets/interaction-cycle.png)

Innanzitutto, si verifica un contatto tra un cliente e un&#39;azienda attraverso un canale di comunicazione: può essere un sito web (interazione in uscita), un’e-mail, un SMS, una notifica push (interazioni in entrata). [Ulteriori informazioni](#interaction-types)

Questo contatto si traduce in una chiamata al motore di offerta. (1)

Quando si verifica la chiamata al motore di offerta, una o più offerte vengono selezionate dal catalogo Offerte a seconda del numero di impostazioni di offerte sulla proposta. (2)

Vengono quindi applicate le regole di idoneità: le offerte migliori vengono selezionate in base alle regole di idoneità, alle date di inizio e fine delle offerte, ai dati di profilo e al comportamento in tempo reale del cliente. (3)

La cronologia delle proposte di profilo viene aggiornata una volta effettuata la selezione, per evitare la duplicazione delle offerte presentate. (4)

Infine, l&#39;offerta migliore viene proposta all&#39;obiettivo. (5)

## Guida introduttiva alle offerte

I passaggi chiave da avviare sono elencati di seguito.

### Configurare la piattaforma

Prima di iniziare, come campagna **Amministratore**, assicurati di aver eseguito le seguenti attività in ambienti di progettazione:

1. Creare profili utente. [Ulteriori informazioni](interaction-operators.md)
1. (facoltativo) Crea un ambiente di offerta per ogni dimensione di targeting. [Ulteriori informazioni](interaction-env.md)
1. Crea regole di tipologia per ogni ambiente. [Ulteriori informazioni](interaction-offer.md#offer-presentation)
1. Crea spazi di offerta per ogni ambiente e configura funzioni di rendering. [Ulteriori informazioni](interaction-offer-spaces.md)
Se lo spazio è definito da un canale unitario in modalità identificata, è necessario specificare i parametri avanzati per questo spazio.

   >[!NOTE]
   >
   >Se lo spazio è definito da un canale unitario in modalità identificata, è necessario specificare i parametri avanzati per questo spazio.

1. Configura il motore di offerta per le interazioni in entrata per presentare e aggiornare una o più offerte.

   Le varie modalità di integrazione sono descritte in [questa sezione](interaction-present-offers.md).

   >[!NOTE]
   >
   >Quando crei uno spazio di offerta sul canale web in entrata, devi configurare il sito web per visualizzare questa offerta.

### Creare e pubblicare il catalogo delle offerte {#managing-the-offer-catalog-}

Come **Gestione delle offerte** devi:

1. Crea categorie di offerte in ambienti di progettazione. [Ulteriori informazioni](interaction-offer-catalog.md#creating-offer-categories)
1. Creare offerte in ambienti di progettazione. [Ulteriori informazioni](interaction-offer.md)
1. Approva e pubblica le offerte su uno o più spazi per renderle disponibili in ambienti live per il gestore delle consegne. [Ulteriori informazioni](interaction-offer.md#approve-offers)

### Utilizzare il catalogo delle offerte {#using-the-offer-catalog-}

Come **Responsabile della consegna**  devi:

1. Creare una campagna.
1. Fai riferimento a un’offerta nella campagna o nella consegna. [Ulteriori informazioni](interaction-send-offers.md).

## Glossario

Scopri i termini specifici dell’offerta e le relative indicazioni prima di iniziare.

* **Ambiente**: set che include un catalogo di offerte e hook (spazi di offerta). Crea un ambiente per dimensione di targeting. Esistono due tipi di ambienti:

   * **Ambiente di progettazione**: ambiente in cui vengono create le offerte e/o vengono definite le regole di tipologia (regole che determineranno le offerte da presentare o meno a una persona target). In questa sezione sono definite anche la tabella dei singoli destinatari delle offerte e la tabella per la memorizzazione di tutte le proposte di offerta. La **[!UICONTROL Design environment]** Il nodo contiene sottocartelle per lo spazio di offerta, filtri predefiniti e categorie di offerte. Per ogni **[!UICONTROL Design environment]** esiste una sola lettura corrispondente **[!UICONTROL Live environment]**, generato dallo stesso **[!UICONTROL Design environment]**.
   * **Ambiente live**: ambiente collegato a un **[!UICONTROL Design environment]**. Contiene offerte di sola lettura il cui contenuto e idoneità sono stati approvati tramite il **[!UICONTROL Design environment]**. Sono disponibili per essere visualizzati su un sito Web o inseriti in un messaggio.

* **Spazio offerta**: cartella che definisce il percorso in cui viene esposta l’offerta. Quando definisci uno spazio puoi:
   * seleziona il canale
   * scegli può essere utilizzato in modalità unitaria (per impostazione predefinita: solo in modalità batch)
   * creare il contenuto dell’offerta utilizzando le funzioni di rendering
   * specificare le offerte da presentare

   Uno spazio è un’interfaccia tra il canale e il motore di offerta.

   >[!CAUTION]
   >
   >Uno spazio di offerta non è un canale di comunicazione, coincide con una posizione di esposizione specifica sul canale. Ad esempio, le offerte esposte su un sito web possono occupare due spazi sulla stessa pagina. In questo caso, hai due spazi per lo stesso canale.
   >
   >Gli spazi devono essere definiti nelle specifiche e non devono essere modificati durante il progetto.

* **Catalogo delle offerte**: set di offerte definite in Adobe Campaign che possono essere selezionate durante un’interazione. Il catalogo è organizzato gerarchicamente con ogni nodo corrispondente a una categoria.
* **Categoria**: una cartella collegata al catalogo delle offerte in un ambiente, che organizza le offerte in base alla natura, alla data di idoneità e al tema dell’applicazione. Una categoria può contenere sottocategorie che ereditano tutte le caratteristiche della categoria padre. Le regole di idoneità possono essere definite per una categoria in modo da condividerle per diverse offerte.
* **Temi di applicazione**: parole chiave definite nella categoria , che consentono di filtrare le offerte quando vengono presentate a un canale in entrata o in uscita limitando la selezione delle offerte a una o due categorie.

   >[!NOTE]
   >
   >Le categorie figlio ereditano i temi identificati nella categoria padre.

* **Regole di idoneità**: vincoli applicati a un ambiente, una categoria o un&#39;offerta relativi al periodo di validità, al target e al peso. Ti consentono di garantire che un’offerta sia in linea con il contatto mirato.

   Negli ambienti, le regole di idoneità includono le regole di presentazione applicate alle offerte e alle persone a cui eseguire il targeting.

   Nelle categorie, le regole di idoneità consentono di: limita la validità della categoria nel tempo, definisce i temi dell’applicazione e determina le persone a cui rivolgersi. Possono anche ricevere un peso moltiplicatore per un dato tempo. Ciò ti consente di condividere le regole per le offerte in altre categorie e di semplificarne la gestione.

   Nelle offerte, le regole di idoneità ti consentono di limitare la validità delle offerte nel tempo e di determinare le persone a cui rivolgerti.

* **Arbitrato**: selezionare le offerte da visualizzare in un ambiente (offerte idonee). Il principio di arbitraggio classifica le offerte per priorità in base ai criteri definiti nelle categorie, offerte e offerte di contesto.
* **Contatto**: un contatto da un&#39;interazione in entrata. Durante l’elaborazione della chiamata del motore, il contatto è associato a una dimensione di targeting. Esistono due tipi di contatti:

   * **[!UICONTROL Identified contact]** : un contatto volontariamente identificato sul canale. Nelle interazioni in uscita, il contatto viene identificato automaticamente.
   * **[!UICONTROL Anonymous contact]** : un contatto che non si è iscritto volontariamente attraverso il canale ma può essere identificato implicitamente tramite un cookie. Questa terminologia viene utilizzata solo per le interazioni in entrata.

      >[!NOTE]
      >
      >I contatti anonimi non identificati sono attribuiti alla dimensione di targeting del visitatore.

* **Interazione in uscita**: chiama al motore di offerta da un elenco di contatti (utilizzato per la consegna di e-mail, direct mailing, ecc.). Le stesse regole e procedure vengono applicate a ogni contatto. Questo tipo di interazione viene generalmente elaborato in modalità batch.
* **Interazione in entrata**: interazione successiva a una chiamata in arrivo generata dall&#39;azione di un contatto sul canale. Questo tipo di interazione viene generalmente elaborato in modalità unitaria.
* **Modalità batch**: la modalità batch consente di selezionare l&#39;offerta migliore per un set di contatti. Le regole di idoneità/priorità vengono applicate a tutti i contatti del set. Questa modalità viene in genere applicata alle interazioni in uscita.
* **Modalità unitaria**: viene elaborato un unico contatto alla volta. Questa modalità viene in genere applicata alle interazioni in entrata e ai messaggi transazionali.
* **Modalità di identificazione**: si riferisce allo stato di un contatto:

   * **[!UICONTROL explicit]** : i contatti sono identificati dal loro accesso all&#39;interfaccia del canale.
   * **[!UICONTROL implicit]** : i contatti sono identificati da un cookie (permanente o sessione). Può essere elaborato come contatto anonimo o identificato.
   * **[!UICONTROL anonymous]** : Impossibile identificare i contatti.

* **Offerta idonea**: offerta conforme ai vincoli definiti a monte che possono essere offerti in modo coerente a un target.
* **Regole di presentazione**: regole di tipologia a cui si fa riferimento nell’ambiente delle offerte, che consentono di escludere alcune offerte tenendo conto della cronologia delle proposte.
* **Peso**: formule che consentono di calcolare con precisione la rilevanza di un’offerta, per selezionare l’offerta più pertinente. I pesi sono definiti nelle offerte. Le offerte ammissibili sono prese in considerazione in ordine decrescente di peso.
* **Funzione di rendering**: funzione definita nello spazio di offerta per creare la relativa rappresentazione dell’offerta in base agli attributi definiti nell’offerta. Esistono tre diverse modalità di rendering della funzione: HTML, XML e testo.
* **Proposta di offerta**: risultato dell’azione che consiste nel presentare una o più offerte a un contatto in un dato spazio (ad esempio banner su un sito web, e-mail o SMS). Questo risultato viene memorizzato nella tabella delle proposte di offerta. Tuttavia, non è obbligatorio salvare le proposte.
* **Simulazione**: che consente di testare la presentazione dell’offerta sui destinatari desiderati prima di inviare effettivamente le offerte.
* **Anteprima**: anteprima dell’offerta così come viene visualizzata nella relativa cartella. È accessibile dalla finestra delle impostazioni dell’offerta o dal profilo del contatto.
* **filtri predefiniti**: le regole di filtro predefinite possono tenere conto dei parametri delle offerte (ad esempio, un codice di offerta). Possono essere riutilizzati dopo la creazione delle offerte.
* **Rappresentazione dell’offerta**: informazioni utilizzate dal canale per visualizzare l’offerta. La rappresentazione dell’offerta può essere creata a partire dalla funzione di rendering dello spazio su cui l’offerta è rappresentata o inserita direttamente nell’interfaccia (ad esempio, nel blocco HTML). Un&#39;offerta può essere rappresentata da uno spazio.
* **Processo di transizione**: un processo attivato in un ambiente identificato, responsabile dell&#39;indirizzamento della chiamata a un ambiente anonimo se il contatto non è stato esplicitamente e/o implicitamente identificato.
