---
title: Interazione campagna - Gestione delle offerte
description: Introduzione a Gestione delle offerte
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 4da3e69a-6230-4c94-a6f1-4e8c01e854ba
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '1608'
ht-degree: 1%

---

# Gestire le interazioni in tempo reale

Campaign viene fornito con **Interazione** modulo che consente di rispondere in tempo reale durante un’interazione con un determinato contatto proponendo loro una o più offerte specifiche. Queste offerte possono essere semplici messaggi di comunicazione, offerte speciali su uno o più prodotti o un servizio.

Puoi creare un catalogo di offerte che si interfaccia con i canali in uscita (e-mail, direct mailing, SMS) per selezionare l’offerta migliore da inviare a un contatto in un determinato contesto. La selezione dell’offerta migliore per un destinatario si basa su **regole di idoneità**. La selezione di un’offerta da una serie di offerte pertinenti è determinata utilizzando regole di priorità. Le regole di presentazione delle offerte prendono in considerazione la cronologia del contatto e consentono di evitare che ricevano più volte la stessa offerta.

L’interazione consente di creare e gestire un catalogo di offerte e configurare le regole di idoneità e i temi dell’applicazione ad esse collegati. A seconda del canale scelto, il contenuto dell’offerta può essere personalizzato grazie a varie funzioni di rendering. Infine, puoi utilizzare il modulo di simulazione per calcolare l’impatto di una presentazione di offerta.

![](assets/interaction-cycle.png)

In primo luogo, si verifica un contatto tra un cliente e un’azienda attraverso un canale di comunicazione: può essere un sito web (interazione in uscita), un’e-mail, un SMS, una notifica push (interazioni in entrata). [Ulteriori informazioni](#interaction-types)

Il contatto determina una chiamata al motore di offerta. (1)

Quando si verifica la chiamata al motore di offerta, una o più offerte vengono selezionate dal catalogo delle offerte a seconda del numero di impostazioni sulla proposta. (2)

Vengono quindi applicate le regole di idoneità: le offerte migliori vengono selezionate in base alle regole di idoneità, alle date di inizio e di fine delle offerte, ai dati del profilo e al comportamento in tempo reale del cliente. (3)

La cronologia delle proposte di profilo viene aggiornata una volta effettuata la selezione, per evitare la duplicazione delle offerte presentate. (4)

Infine, viene proposta al target l&#39;offerta migliore. (5)

## Introduzione alle offerte

Di seguito sono elencati i passaggi chiave per iniziare.

### Configurare la piattaforma

Prima di iniziare, come campagna **Amministratore**, accertati di aver eseguito le seguenti attività in ambienti di progettazione:

1. Creare profili utente. [Ulteriori informazioni](interaction-operators.md)
1. (facoltativo) Crea un ambiente di offerta per ogni dimensione di targeting. [Ulteriori informazioni](interaction-env.md)
1. Crea regole di tipologia per ogni ambiente. [Ulteriori informazioni](interaction-offer.md#offer-presentation)
1. Crea spazi di offerta per ogni ambiente e configura le funzioni di rendering. [Ulteriori informazioni](interaction-offer-spaces.md)
Se lo spazio è definito da un canale unitario in modalità identificata, è necessario specificare i parametri avanzati per questo spazio.

   >[!NOTE]
   >
   >Se lo spazio è definito da un canale unitario in modalità identificata, è necessario specificare i parametri avanzati per questo spazio.

1. Configura il motore delle offerte per le interazioni in entrata per presentare e aggiornare una o più offerte.

   Le varie modalità di integrazione sono descritte in [questa sezione](interaction-present-offers.md).

   >[!NOTE]
   >
   >Quando si crea uno spazio dell’offerta sul canale web in entrata, è necessario configurare il sito web in modo da visualizzare questa offerta.

### Creare e pubblicare il catalogo delle offerte {#managing-the-offer-catalog-}

Come un **Gestione offerte** devi:

1. Crea categorie di offerta in ambienti di progettazione. [Ulteriori informazioni](interaction-offer-catalog.md#creating-offer-categories)
1. Creare le offerte in ambienti di progettazione. [Ulteriori informazioni](interaction-offer.md)
1. Approva e pubblica le offerte in uno o più spazi per renderle disponibili negli ambienti live per il responsabile della consegna. [Ulteriori informazioni](interaction-offer.md#approve-offers)

### Utilizzare il catalogo delle offerte {#using-the-offer-catalog-}

As a **Responsabile della consegna**  devi:

1. Creare una campagna.
1. Fai riferimento a un’offerta nella campagna o nella consegna. [Ulteriori informazioni](interaction-send-offers.md).

## Glossario

Scopri i termini specifici dell’offerta e le relative indicazioni prima di iniziare.

* **Ambiente**: set che include un catalogo di offerte e hook (spazi di offerta). Crea un ambiente eseguendo il targeting della dimensione. Esistono due tipi di ambienti:

   * **Ambiente di progettazione**: ambiente in cui vengono create le offerte e/o vengono definite le regole di tipologia (regole che determineranno le offerte da presentare o non presentare a una persona mirata). In questo documento sono anche definiti la tabella delle persone target delle offerte e la tabella per l’archiviazione di tutte le proposte di offerta. Il **[!UICONTROL Design environment]** Il nodo contiene sottocartelle per lo spazio delle offerte, filtri predefiniti e categorie di offerta. Per ogni **[!UICONTROL Design environment]** esiste un valore corrispondente di sola lettura **[!UICONTROL Live environment]**, generato dallo stesso **[!UICONTROL Design environment]**.
   * **Ambiente live**: ambiente collegato a un **[!UICONTROL Design environment]**. Contiene offerte di sola lettura il cui contenuto e la cui idoneità sono stati approvati tramite **[!UICONTROL Design environment]**. Possono essere visualizzati su un sito Web o inseriti in un messaggio.

* **Spazio dell’offerta**: cartella che definisce il percorso in cui viene esposta l’offerta. Quando si definisce uno spazio è possibile:
   * seleziona il canale
   * scegli può essere utilizzato in modalità unitaria (per impostazione predefinita: solo in modalità batch)
   * creare il contenuto dell’offerta utilizzando le funzioni di rendering
   * specifica le offerte da presentare

   Uno spazio è un’interfaccia tra il canale e il motore di offerta.

   >[!CAUTION]
   >
   >Uno spazio dell’offerta non è un canale di comunicazione, bensì coincide con una posizione specifica dell’esposizione sul canale. Ad esempio, le offerte esposte su un sito web possono occupare due spazi sulla stessa pagina. In questo caso, sono disponibili due spazi per lo stesso canale.
   >
   >Gli spazi devono essere definiti nelle specifiche e non devono essere modificati durante il progetto.

* **Catalogo delle offerte**: set di offerte definite in Adobe Campaign che possono essere selezionate durante un’interazione. Il catalogo è organizzato gerarchicamente e ogni nodo corrisponde a una categoria.
* **Categoria**: cartella collegata al catalogo delle offerte in un ambiente, che organizza le offerte in base alla natura, alla data di idoneità e al tema dell’applicazione. Una categoria può contenere sottocategorie, che ereditano tutte le caratteristiche della categoria padre. Le regole di idoneità possono essere definite per una categoria in modo da condividerle per più offerte.
* **Temi applicazione**: parole chiave definite nella categoria, che consentono di filtrare le offerte quando vengono presentate a un canale in entrata o in uscita limitando la selezione delle offerte a una o due categorie.

   >[!NOTE]
   >
   >Le categorie figlio ereditano i temi identificati nella categoria padre.

* **Regole di idoneità**: vincoli applicati a un ambiente, una categoria o un’offerta per quanto riguarda il periodo di validità, il target e il peso. Ti consentono di verificare che un’offerta sia in linea con il contatto mirato.

   Negli ambienti, le regole di idoneità includono le regole di presentazione applicate alle offerte e alle persone di destinazione.

   Nelle categorie, le regole di idoneità consentono di: limitare la validità della categoria nel tempo, definire i temi dell’applicazione e determinare le persone di destinazione. Possono anche ricevere un peso moltiplicatore per un dato tempo. Questo consente di condividere le regole per le offerte in altre categorie, semplificandone la gestione.

   Nelle offerte, le regole di idoneità ti consentono di limitare la validità delle offerte in tempo e determinare le persone di destinazione.

* **Arbitraggio**: selezione delle offerte da visualizzare in un ambiente (offerte idonee). Il principio di arbitraggio classifica le offerte per priorità in base ai criteri definiti nelle categorie, nelle offerte e nelle offerte contestuali.
* **Contatto**: un contatto da un’interazione in entrata. Durante l’elaborazione delle chiamate al motore, il contatto è associato a una dimensione di targeting. Esistono due tipi di contatti:

   * **[!UICONTROL Identified contact]** : contatto che è stato identificato volontariamente sul canale. Nelle interazioni in uscita, il contatto viene identificato automaticamente.
   * **[!UICONTROL Anonymous contact]** : un contatto che non si è abbonato volontariamente tramite il canale, ma che può essere identificato implicitamente tramite un cookie. Questa terminologia viene utilizzata solo per le interazioni in ingresso.

      >[!NOTE]
      >
      >I contatti anonimi non identificati vengono attribuiti alla dimensione di targeting dei visitatori.

* **Interazione in uscita**: chiama al motore delle offerte da un elenco di contatti (utilizzato per la consegna di e-mail, direct mailing, ecc.). A ogni contatto vengono applicate le stesse regole e le stesse procedure. Questo tipo di interazione viene in genere elaborato in modalità batch.
* **Interazione in entrata**: interazione successiva a una chiamata in arrivo generata dall’azione di un contatto sul canale. Questo tipo di interazione viene solitamente elaborato in modalità unitaria.
* **Modalità batch**: la modalità batch ti consente di selezionare l’offerta migliore per un set di contatti. Le regole di idoneità/definizione delle priorità vengono applicate a tutti i contatti del set. Questa modalità viene in genere applicata per le interazioni in uscita.
* **Modalità unitaria**: viene elaborato un singolo contatto alla volta. Questa modalità si applica in genere alle interazioni in entrata e ai messaggi transazionali.
* **Modalità di identificazione**: si riferisce allo stato di un contatto:

   * **[!UICONTROL explicit]** : i contatti sono identificati dal loro accesso all’interfaccia del canale.
   * **[!UICONTROL implicit]** : il contatto è identificato da un cookie (permanente o sessione). Può essere elaborato come contatto anonimo o identificato.
   * **[!UICONTROL anonymous]** : impossibile identificare i contatti.

* **Offerta idonea**: offerta che soddisfa i vincoli definiti a monte e che può essere offerta in modo coerente a un target.
* **Regole di presentazione**: regole di tipologia a cui si fa riferimento nell’ambiente delle offerte, che ti consentono di escludere alcune offerte tenendo conto della cronologia delle proposte.
* **Spessore**: formule che consentono di calcolare con precisione la rilevanza di un’offerta, per selezionare l’offerta più pertinente. I pesi sono definiti nelle offerte. Le offerte idonee vengono prese in considerazione in ordine decrescente di peso.
* **Funzione di rendering**: funzione definita nello spazio dell’offerta per costruire la sua rappresentazione dell’offerta in base agli attributi definiti nell’offerta. Esistono tre diverse modalità di funzione di rendering: HTML, XML e testo.
* **Proposta di offerta**: risultato dell’azione che consiste nel presentare una o più offerte a un contatto in un determinato spazio (ad esempio, banner su un sito web, e-mail o SMS). Questo risultato viene memorizzato nella tabella delle proposte di offerta. Tuttavia, non è obbligatorio salvare le proposte.
* **Simulazione**: modulo che consente di testare la presentazione delle offerte sui destinatari target prima di inviarle effettivamente.
* **Anteprima**: anteprima dell’offerta così come viene visualizzata nella sua cartella. È accessibile dalla finestra delle impostazioni dell’offerta o dal profilo di contatto.
* **filtri predefiniti**: regole di filtro predefinite possono tenere conto dei parametri dell’offerta (ad esempio, un codice offerta). Possono essere riutilizzati dopo la creazione delle offerte.
* **Rappresentazione dell’offerta**: informazioni utilizzate dal canale per visualizzare l’offerta. La rappresentazione dell’offerta può essere realizzata a partire dalla funzione di rendering dello spazio in cui l’offerta viene rappresentata o immessa direttamente nell’interfaccia (ad esempio, nel blocco HTML). Un’offerta può essere rappresentata da uno spazio.
* **Processo di transizione**: processo attivato in un ambiente identificato, responsabile di indirizzare la chiamata a un ambiente anonimo se il contatto non è stato identificato in modo esplicito e/o implicito.
