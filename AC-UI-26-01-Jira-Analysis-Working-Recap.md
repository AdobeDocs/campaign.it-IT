---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '2430'
ht-degree: 3%

---
# Analisi dei ticket Jira AC-UI - Riepilogo di lavoro
**Data:** 12 gennaio 2026
**Tipo di documento:** Documento di lavoro / Analisi interna

---

## Sintesi

Questo documento analizza i ticket Jira del prodotto da più query relative alle versioni dell’interfaccia utente AC (gennaio 2026 e novembre 2025). L&#39;analisi si concentra sull&#39;identificazione dei requisiti della documentazione, proponendo biglietti DOCAC ed evidenziando le domande aperte.

**Totale ticket univoci analizzati:** 19
**Ticket che richiedono la documentazione:** 14
**Ticket già documentati:** 5
**Biglietti senza bisogno di documenti:** 5

---

## &#x200B;1. Elenco dei biglietti analizzati

### Versione mensile 1.1 AC-UI-26-01 (gennaio 2026)

| ID ticket | Titolo | Stato | Priorità | Componenti |
|-----------|-------|--------|----------|------------|
| NEO-91565 | [Interfaccia utente Web] Aggiunta del supporto per i campi di personalizzazione (integrazione avanzata di AEM) | Risolto | Normale | ACS ad ACC, interfaccia PIX/UX |
| NEO-80973 | Disponibilità del reporting dinamico per tutti gli utenti dell’interfaccia web | In corso | Normale | ACS ad ACC, interfaccia PIX/UX |
| NEO-86754 | [UX/UI] Test A/B | In corso | Bloccante | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |
| NEO-76126 | Authoring degli schemi: crea una nuova tabella, estende gli schemi e accedi al database esterno | In corso | Critico | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |
| NEO-93487 | [Interfaccia Web] processo di calcolo della pianificazione della consegna simile a quello di ACS | Nuovo | Critico | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |
| NEO-92400 | Miglioramenti della versione - 26 gennaio | Nuovo | Normale | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |
| NEO-88838 | Editor contenuto: utilizzare variabili tema nel frammento | Nuovo | Normale | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |
| NEO-92668 | [UX/interfaccia utente] Web Analytics | Nuovo | Normale | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |
| NEO-86753 | Integrazione di [UX/UI] AEM per Live Copy/Copie per lingua | Nuovo | Bloccante | ACS ad ACC, interfaccia PIX/UX |

### Miglioramenti della versione 1.2 per i ticket collegati (NEO-92400)

| ID ticket | Titolo | Stato | Priorità | Componenti |
|-----------|-------|--------|----------|------------|
| NEO-92942 | [Generatore regole] Filtri predefiniti - Opzione condivisa | Risolto | Normale | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |
| NEO-91299 | Interfaccia web - Attività di consegna continua | Chiusa | Grave | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |
| NEO-90130 | Abilitare il caricamento di file OOTB per le consegne di notifiche push multilingue | Chiusa | Critico | ACS ad ACC, interfaccia PIX/UX |

### Versione mensile 1.3 AC-UI-25-11 (novembre 2025)

| ID ticket | Titolo | Stato | Priorità | Componenti |
|-----------|-------|--------|----------|------------|
| NEO-91566 | [Supporto interfaccia utente Web] per il tracciamento di CTA in webui | Chiusa | Normale | ACS ad ACC, interfaccia PIX/UX |
| NEO-91564 | [Interfaccia utente Web] [AEM multilingue in ACC] Supporto interfaccia utente per AEM multilingue | Chiusa | Normale | ACS ad ACC, interfaccia PIX/UX |
| NEO-90183 | [UX/UI] Rich Push multilingue - Interfaccia utente | Chiusa | Bloccante | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |
| NEO-91567 | [Interfaccia utente Web] Aggiunta del supporto per la funzionalità NRT | Risolto | Normale | ACS ad ACC, interfaccia PIX/UX |
| NEO-91563 | API REST transazionale per l’arricchimento basato su profili - Interfaccia web | Risolto | Normale | ACS ad ACC, interfaccia PIX/UX |
| NEO-92151 | [Interfaccia utente/UX] Messaggistica transazionale basata su profilo - Fase 2 | Risolto | Grave | ACS ad ACC, interfaccia PIX/UX |
| NEO-84916 | [UX/UI] Imposta e gestisci il processo di approvazione | Risolto | Critico | INTERFACCIA UTENTE/INTERFACCIA UTENTE PIX |

---

## &#x200B;2. Biglietti che richiedono documentazione

### 2.1 PRIORITÀ ALTA - Sviluppo attivo (AC-UI-26-01)

#### **NEO-86754: Test A/B**
- **Stato:** In Corso (Sulla Traccia)
- **Perché è necessaria la documentazione:** Nuova funzionalità importante per la sperimentazione del contenuto delle e-mail con funzionalità di test A/B
- **DOCAC esistente:** DOCAC-13104 (nuovo stato)
- **Ambito documentazione:**
   - Creazione di esperimenti di test A/B nelle consegne
   - Definizione delle varianti di contenuto/consegna
   - Impostazione delle proporzioni del campione e invio delle varianti di test
   - Definizione dei criteri di valutazione
   - Analisi dei risultati dell’esperimento e selezione dei vincitori
   - Best practice e limitazioni
- **Pubblico di destinazione:** utenti marketing, manager campagna
- **Versione:** 8.9.1, AC-UI-26-01-Monthly
- **Domande aperte:**
   - Stato di convalida finale dell’interfaccia utente/interfaccia utente?
   - Esistono limitazioni per i messaggi transazionali?
   - Integrazione con l’anteprima dei contenuti di Acrite?

#### **NEO-80973: disponibilità Reporting dinamico**
- **Stato:** In corso (Pronto per la revisione)
- **Documentazione necessaria:** espansione del reporting dinamico a tutti gli utenti dell&#39;interfaccia utente Web (non solo a clienti ACC con 8.7 ACS)
- **DOCAC esistente:** DOCAC-11070 (chiuso), DOCAC-13432 (risolto - limitazioni di lingua)
- **Ambito documentazione:**
   - Disponibilità e requisiti di accesso
   - Documentazione delle lingue supportate
   - Limitazioni note e reporting legacy
   - Visualizzazione di metriche in conflitto con reporting legacy
   - Configurazione dell’ambiente demo
- **Pubblico di destinazione:** Tutti gli utenti dell&#39;interfaccia utente Web, analisti
- **Versione:** 8.8.1, AC-UI-26-01-Monthly
- **Domande aperte:**
   - Stato di disponibilità dell’ambiente demo?
   - Elenco completo delle metriche in conflitto con i rapporti legacy?
   - Matrice di supporto della lingua?

#### **NEO-76126: authoring degli schemi**
- **Stato:** In Corso (Sulla Traccia)
- **Perché è necessaria la documentazione:** importante funzione di amministrazione per la gestione dei modelli di dati
- **DOCAC esistente:** DOCAC-13826 (nuovo stato)
- **Ambito documentazione:**
   - Creazione di nuove tabelle
   - Estensione degli schemi esistenti
   - Accesso a database esterni
   - Definizione modulo per entità personalizzate
   - Navigazione e operazioni CRUD
   - Funzionalità di fase 3 (creazione ed estensione degli schemi) - Fine febbraio ETA
- **Pubblico di destinazione:** utenti amministratori, amministratori tecnici
- **Versione:** AC-UI-26-01-Mensile
- **Data di scadenza:** 28 febbraio 2026
- **Domande aperte:**
   - Quando verrà completata la fase 2 per l&#39;attivazione di FF?
   - Conferma della tempistica della consegna di fase 3?
   - Requisiti di configurazione dell’ambiente?

#### **NEO-93487: processo di calcolo pianificazione consegna (H&amp;M)**
- **Stato:** Nuovo
- **Perché è necessaria la documentazione:** Escalation cliente critica - Pianificazione consegna basata sul fuso orario
- **DOCAC esistente:** Nessuno identificato
- **Ambito documentazione:**
   - Pianificazione delle consegne in base al fuso orario dell’utente
   - Utilizzo di formule calcolate per aree con più fusi orari
   - Esempi di configurazione (ad esempio, Stati Uniti con più fusi orari)
   - Best practice per le campagne globali
   - Confronto delle funzioni con ACS
- **Pubblico di destinazione:** Manager campagne, utenti marketing
- **Impatto sul cliente:** H&amp;M (oltre 50 mercati)
- **Versione:** 8.9.1, AC-UI-26-01-Monthly, 8.8.2.NEO-90300
- **Domande aperte:**
   - Dimostrazione delle funzioni pianificata con PM?
   - Specifiche funzionali complete disponibili?
   - I modelli di interfaccia utente sono stati finalizzati?

#### **NEO-86753: integrazione di AEM per Live Copy/Copie per lingua**
- **Stato:** Nuovo
- **Perché è necessaria la documentazione:** funzionalità specifica di Microsoft per la gestione dei contenuti multilingue
- **DOCAC esistente:** DOCAC-13829 (risolto)
- **Ambito documentazione:**
   - Esplorazione dei modelli di consegna di AEM
   - Creazione di Live Copy
   - La creazione di una lingua copia le varianti di contenuto
   - Flusso di lavoro e best practice
   - Requisiti di configurazione dell’integrazione
- **Pubblico di destinazione:** utenti marketing che lavorano con AEM, team Microsoft
- **Versione:** AC-UI-26-01-Mensile
- **Priorità:** Blocco
- **Domande aperte:**
   - Il lavoro è stato trasferito alla squadra di Himanshu - stato attuale?
   - Timeline per il completamento?

#### **NEO-92668: analisi Web**
- **Stato:** Nuovo (In Esecuzione)
- **Documentazione necessaria:** configurazione account esterno per l&#39;integrazione di Web Analytics
- **DOCAC esistente:** Nessuno identificato
- **Ambito documentazione:**
   - Creazione account esterno Web Analytics
   - Parametri di configurazione
   - Integrazione con il tracciamento della consegna
   - Funzionalità di reporting
- **Pubblico di destinazione:** utenti amministratori, analisti di marketing
- **Versione:** AC-UI-26-01-Mensile
- **Domande aperte:**
   - Stato di disponibilità dell’ambiente?
   - Passaggi di configurazione richiesti?

### 2.2 PRIORITÀ MEDIUM - Recentemente consegnato (AC-UI-25-11)

#### **NEO-90183: push multilingue formattato**
- **Stato:** Chiuso
- **Perché è necessaria la documentazione:** Nuova funzionalità per iOS/Android rich push con supporto multilingue
- **DOCAC esistente:** DOCAC-13565 (nuovo stato)
- **Ambito documentazione:**
   - Configurazione di notifiche push potenziate per iOS e Android
   - Varianti di contenuto multilingue
   - Selezione modello
   - Campi aggiuntivi per contenuti avanzati
   - Funzionalità di caricamento file
   - Best practice e limitazioni
- **Pubblico di destinazione:** Utenti marketing, gestori di canali mobili
- **Versione:** AC-UI-25-11-Monthly, 8.8.2
- **Cliente:** H&amp;M

#### **NEO-84916: Gestione dei processi di approvazione**
- **Stato:** risolto
- **Perché è necessaria la documentazione:** importante funzionalità del flusso di lavoro per la convalida della consegna
- **DOCAC esistente:** DOCAC-13827 (nuovo stato)
- **Ambito documentazione:**
   - Impostazione degli operatori di approvazione nelle consegne/campagne
   - Configurazione dell’approvazione del contenuto
   - Configurazione dell’approvazione del target
   - Gestione dei flussi di lavoro di approvazione tra canali diversi (e-mail, SMS, push iOS/Android, direct mailing, call center)
   - Accetta/rifiuta processi
   - Reporting e tracciamento dell’approvazione
- **Pubblico di destinazione:** manager campagne, utenti amministratori
- **Versione:** AC-UI-25-11-Mensile
- **Priorità:** critica
- **Cliente:** Pierre Fabre

#### **NEO-91299: attività di consegna continua**
- **Stato:** Chiuso
- **Documentazione necessaria:** nuova attività del flusso di lavoro per scenari di consegna ricorrenti
- **DOCAC esistente:** DOCAC-13586 (nuovo stato), DOCAC-13808 (chiuso - guida contestuale)
- **Ambito documentazione:**
   - Configurazione dell’attività di consegna continua
   - Requisiti del selettore del modello di consegna
   - Gestione degli errori di processo
   - Integrazione dei flussi di lavoro
   - Casi d’uso ed esempi
- **Pubblico di destinazione:** utenti tecnici, progettisti di flussi di lavoro
- **Versione:** AC-UI-26.01.06

#### **NEO-90130: caricamento file push multilingue (H&amp;M)**
- **Stato:** Chiuso
- **Perché è necessaria la documentazione:** parità di funzionalità OOTB con ACS per push multilingue basato su file
- **DOCAC esistente:** DOCAC-13606 (nuovo stato)
- **Ambito documentazione:**
   - Caricamento di file CSV per notifiche push multilingue
   - Specifiche del formato del file
   - Mappatura campi
   - Configurazioni specifiche per iOS e Android
   - Gestione del tipo di messaggio dati
   - Risoluzione dei problemi e problemi noti
- **Pubblico di destinazione:** utenti marketing, manager campagna
- **Versione:** AC-UI-25-10-Mensile, AC-UI-25.11.03
- **Priorità:** critica
- **Cliente:** H&amp;M (migrazione da ACS a ACC)

#### **NEO-92942: Filtri predefiniti - Opzione condivisa**
- **Stato:** risolto
- **Documentazione necessaria:** miglioramento della funzionalità del generatore di regole
- **DOCAC esistente:** DOCAC-13697 (stato revisione codice), DOCAC-13522 (chiuso - helper)
- **Ambito documentazione:**
   - Opzione condivisa per filtri predefiniti
   - Gestione della visibilità dei filtri con altri operatori
   - Comportamenti ACC e Percorso del marchio
   - Gestione degli elenchi di filtri
- **Pubblico di destinazione:** Tutti gli utenti, Progettazione query
- **Versione:** Versione principale
- **FF:** enable-query-filter-shared

### 2.3 BASSA PRIORITÀ - Miglioramento dell’editor di contenuti

#### **NEO-88838: variabili tema nei frammenti**
- **Stato:** Nuovo (In Attesa)
- **Perché è necessaria la documentazione:** funzionalità tema Designer e-mail
- **DOCAC esistente:** DOCAC-12941 (nuovo stato)
- **Ambito documentazione:**
   - Utilizzo di variabili tema nei frammenti e-mail
   - Configurazione tema
   - Gestione delle variabili
   - Best practice
- **Pubblico di destinazione:** designer e-mail, utenti marketing
- **Versione:** AC-UI-26-01-Mensile
- **Nota:** la funzionalità è in attesa di una nuova visita lato account

---

## &#x200B;3. I biglietti NON richiedono documentazione

### 3.1 Annullato/Non più applicabile

| ID ticket | Titolo | Motivo |
|-----------|-------|--------|
| NEO-91566 | Tracciamento di CTA in webui | Nessun lavoro previsto per l&#39;interfaccia utente; informazioni in sospeso da MSFT |
| NEO-91564 | Supporto per l’interfaccia utente multilingue di AEM | Lavoro dell’interfaccia utente gestito da un team diverso |
| NEO-91567 | Supporto della funzione NRT | Nessun impatto sull’interfaccia web; specifiche disponibili |
| NEO-91563 | API REST transazionale | Nessun lavoro nell’interfaccia web; aggiornamento istanza in sospeso |
| NEO-92151 | Fase 2 di arricchimento del profilo | La storia non ha attività; contrassegnata come non più valida |

### 3.2 Ticket segnaposto/tracciamento

| ID ticket | Titolo | Motivo |
|-----------|-------|--------|
| NEO-92400 | Miglioramenti della versione - 26 gennaio | Segnaposto per tenere traccia del completamento dei miglioramenti |

---

## &#x200B;4. Biglietti DOCAC proposti

### 4.1 Necessità di nuovi ticket DOCAC

#### **DOCAC-XXXX: pianificazione delle consegne con supporto per il fuso orario**
**Ticket padre:** NEO-93487
**Priorità:** Critica
**Versione di destinazione:** AC-UI-26-01-Monthly
**Descrizione:**
Documenta il nuovo processo di calcolo della pianificazione della consegna che consente di pianificare la consegna in base al fuso orario in modo simile alla funzionalità ACS. Questa funzione consente agli addetti al marketing di inviare comunicazioni in base ai fusi orari dei destinatari utilizzando formule calcolate, particolarmente importanti per i mercati con più fusi orari, come Stati Uniti.

**Ambito:**
- Guida alla configurazione per la pianificazione basata sul fuso orario
- Esempi di formule calcolate
- Scenari di mercato con più fusi orari
- Guida alla migrazione da ACS
- Best practice e limitazioni

**Cliente:** H&amp;M (critico per la migrazione da ACS ad ACC)

#### **DOCAC-XXXX: Configurazione account esterno Web Analytics**
**Ticket padre:** NEO-92668
**Priorità:** Normale
**Versione di destinazione:** AC-UI-26-01-Monthly
**Descrizione:**
Documenta la configurazione e l’utilizzo del tipo di account esterno Web Analytics nell’interfaccia utente Web.

**Ambito:**
- Passaggi per la creazione di account esterni
- Parametri di configurazione
- Integrazione con il tracciamento della consegna
- Funzionalità di reporting
- Risoluzione dei problemi

---

### 4.2 Ticket DOCAC esistenti da aggiornare

#### **DOCAC-13104: Test A/B**
**Stato:** Nuovo
**Ticket padre:** NEO-86754
**Azione richiesta:** Avvia la documentazione - funzionalità nello sviluppo attivo
**Consegna stimata:** febbraio 2026 (in attesa del completamento dello sviluppo)

#### **DOCAC-11070 e DOCAC-13432: Reporting dinamico**
**Stato:** chiuso/risolto
**Ticket padre:** NEO-80973
**Azione necessaria:**
- Aggiornamento per disponibilità generale (non solo 8.7)
- Documentare le metriche in conflitto con il reporting legacy
- Verificare la documentazione relativa al supporto linguistico

#### **DOCAC-13826: Authoring degli schemi**
**Stato:** Nuovo
**Ticket padre:** NEO-76126
**Azione necessaria:**
- Documentazione della fase 2 (navigare + CRUD + definizione del modulo)
- Preparazione per la fase 3 (creazione/estensione degli schemi) - fine febbraio ETA

#### **DOCAC-13829: AEM Live Copy/Copie per lingua**
**Stato:** risolto
**Ticket padre:** NEO-86753
**Azione richiesta:** Verificare lo stato corrente e aggiornare in base alle esigenze

#### **DOCAC-13565: push multilingue formattato**
**Stato:** Nuovo
**Ticket padre:** NEO-90183
**Azione richiesta:** Documentazione completa - funzionalità distribuita a novembre 2025

#### **DOCAC-13827: processo di approvazione**
**Stato:** Nuovo
**Ticket padre:** NEO-84916
**Azione richiesta:** Documentazione completa - funzionalità distribuita a novembre 2025

#### **DOCAC-13586 e DOCAC-13808: distribuzione continua**
**Stato:** Nuovo/Chiuso
**Ticket padre:** NEO-91299
**Azione richiesta:** Documentazione principale completa (13586) - funzionalità consegnata

#### **DOCAC-13606: caricamento file push multilingue**
**Stato:** Nuovo
**Ticket padre:** NEO-90130
**Azione richiesta:** Documentazione completa - funzionalità consegnata

#### **DOCAC-13697 e DOCAC-13522: filtri predefiniti condivisi**
**Stato:** Revisione codice/Chiusa
**Ticket padre:** NEO-92942
**Azione richiesta:** Finalizzare la documentazione (13697)

#### **DOCAC-12941: temi in E-mail Designer**
**Stato:** Nuovo
**Ticket padre:** NEO-88838
**Azione necessaria:** funzionalità in attesa di attesa di revisione

---

## &#x200B;5. Domande aperte e informazioni mancanti

### 5.1 Per funzione

#### **Test A/B (NEO-86754)**
- [ ] Qual è lo stato di convalida finale dell&#39;interfaccia utente/interfaccia utente?
- [ ] Esistono limitazioni specifiche per i messaggi transazionali?
- [ ] Come si integra con l&#39;anteprima del contenuto di Acrite (blocco di NEO-92516)?
- [ ] Quali sono le funzionalità di simulazione/anteprima all&#39;interno di ogni variante?

#### **Reporting dinamico (NEO-80973)**
- [ ] Qual è lo stato della riattivazione dell&#39;ambiente demo?
- [ ] Elenco completo delle metriche in conflitto con i rapporti legacy?
- [ ] Matrice di supporto dettagliata per le lingue?
- [ ] confronto delle prestazioni con la generazione rapporti legacy?

#### **Authoring di schemi (NEO-76126)**
- [ ] Quando verrà attivata la fase 2?
- [ ] ETA confermato per la fase 3 (creare/estendere schemi)?
- [ ] Quali sono i requisiti di configurazione dell&#39;ambiente?
- [ ] Limitazioni rispetto alla funzionalità della console client?

#### **Pianificazione consegna (NEO-93487)**
- [ ] È pianificata la demo della funzione con PM?
- [ ] Sono disponibili specifiche funzionali complete?
- [ ] modelli di interfaccia utente finalizzati e rivisti?
- [ ] Qual è la sintassi/struttura esatta della formula?

#### **AEM Live/Copie per lingua (NEO-86753)**
- [ ] Qual è lo stato attuale del team di Himanshu?
- [ ] Timeline di consegna aggiornata?
- [ ] Dipendenze dalla versione di AEM?

#### **Analisi Web (NEO-92668)**
- [ ] Cos&#39;è lo stato di disponibilità dell&#39;ambiente?
- [ ] Completare i requisiti di installazione?
- [ ] piattaforme di analisi supportate?

#### **Variabili di tema nei frammenti (NEO-88838)**
- [ ] Quando Acrite rivisiterà la funzionalità?
- [ ] È ancora pianificato per AC-UI-26-01?

### 5.2 Per versione

#### **AC-UI-26-01-Monthly (gennaio 2026)**
- [ ] conferma della data di rilascio ufficiale?
- [ ] Data di blocco delle funzioni?
- [ ] Timeline di completamento test?
- [ ] Termine per la consegna della documentazione?

#### **Novembre 2025: funzionalità distribuite**
- [ ] Quali funzionalità sono già attivate in produzione?
- [ ] Sono stati rilevati problemi o limitazioni noti dopo il rilascio?
- [ ] feedback del cliente ricevuto?

### 5.3 Processo di documentazione

- [ ] Chi sono le PMI per ogni funzionalità?
- [ ] Qual è il processo di revisione della documentazione?
- [ ] Lingua della documentazione di Target (solo EN o multilingue)?
- [ ] Requisiti di piattaforma/formato della documentazione?
- [ ] Schermate e disponibilità dell&#39;ambiente demo?

---

## &#x200B;6. Impatto sui clienti ed escalation

### 6.1 Ticket per i clienti critici

| Cliente | Ticket | Funzionalità | Impatto |
|----------|--------|---------|--------|
| **H&amp;M** | NEO-93487 | Pianificazione consegna | Oltre 50 mercati; requisiti di distribuzione con più fusi orari; da ACS a ACC migration blocker |
| **H&amp;M** | NEO-90130 | Caricamento di file push multilingue | Critico per la migrazione da ACS ad ACC; riduce i costi operativi |
| **Pierre Fabre** | NEO-84916 | Processo di approvazione | Requisiti normativi e di workflow |

### 6.2 Caratteristiche specifiche di Microsoft

| Ticket | Funzionalità | Stato | Note |
|--------|---------|--------|-------|
| NEO-86753 | AEM Live/Copie per lingua | Nuovo | Utilizzato principalmente da Microsoft |
| NEO-91566 | Tracciamento CTA | Chiuso/Non più applicabile | Informazioni in sospeso da MSFT |
| NEO-91567 | Funzione NRT | Risolto/Nessun impatto sull’interfaccia utente | Nuova funzionalità ACS per MSFT |

---

## &#x200B;7. Priorità e tempistica della documentazione

### 7.1 Necessità Di Un’Azione Immediata (Gennaio 2026)

**PRIORITÀ ALTA - Consegnato ma non documentato:**
1. **NEO-90183** - Rich Push multilingue (DOCAC-13565)
2. **NEO-84916** - Processo di approvazione (DOCAC-13827)
3. **NEO-91299** - Consegna continua (DOCAC-13586)
4. **NEO-90130** - Caricamento di file push multilingue (DOCAC-13606)

### 7.2 In Corso - Sviluppo In Corso (Feb-Mar 2026)

**PRIORITÀ CRITICA:**
1. **NEO-86754** - Test A/B (DOCAC-13104) - Scadenza: febbraio 2026
2. **NEO-76126** - Authoring degli schemi (DOCAC-13826) - Fase 2: febbraio, Fase 3: fine febbraio
3. **NEO-93487** - Pianificazione delle consegne (NEW DOCAC) - Riassegnazione critica del cliente

**PRIORITÀ NORMALE:**
1. **NEO-80973** - Reporting dinamico (aggiornamento DOCAC-11070)
2. **NEO-92668** - Analisi Web (NUOVO DOCAC)
3. **NEO-86753** - Copie AEM Live/Language Copy (DOCAC-13829)

### 7.3 In attesa / Futuro

1. **NEO-88838** - Variabili tema (DOCAC-12941) - Acrite revisit in sospeso

---

## &#x200B;8. Prossime tappe

### 8.1 Azioni del team di documentazione
1. **Assegna priorità alle funzionalità consegnate** senza documentazione (sezione 7.1)
2. **Crea nuovi ticket DOCAC** per NEO-93487 e NEO-92668
3. **Aggiorna ticket DOCAC** esistenti con ambito dettagliato (sezione 4.2)
4. **Pianifica interviste alle PMI** per test A/B, schemi e pianificazione delle consegne
5. **Raccogli le schermate** e prepara gli ambienti demo
6. **Revisione e finalizzazione** delle limitazioni linguistiche per Reporting dinamico

### 8.2 Raccolta di informazioni
1. **Contattare i responsabili tecnici** per gli aggiornamenti di stato in data:
   - Convalida finale test A/B
   - Timeline di fase 2/3 degli schemi
   - Specifiche di pianificazione della consegna
2. **Pianifica demo di funzionalità** con Product Management
3. **Raccogli il feedback dei clienti** da H&amp;M e Pierre Fabre
4. **Verifica la disponibilità dell&#39;ambiente** per Web Analytics e Dynamic Reporting

### 8.3 Coordinamento
1. **Sincronizza con il team di Himanshu** su AEM Live/Copie per lingua
2. **Coordina con il team Acrite** sullo stato delle variabili del tema
3. **Completa le funzionalità specifiche di Microsoft** con il team dell&#39;account

---

## Cronologia documento

| Data | Autore | Versione | Modifiche |
|------|--------|---------|---------|
| 12/01/2026 | Assistente IA | 1,0 | Analisi iniziale delle query Jira |

---

## Appendice: query Jira analizzate

1. `project = NEO AND fixVersion = AC-UI-26-01-Monthly and type = story order by status`
2. `issueFunction in linkedIssuesOf('key=NEO-92400', 'is implemented by')`
3. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and type = story order by status`
4. `project = NEO AND fixVersion = AC-UI-25-11-Monthly and fixVersion != 8.8.2 and type = story order by status`

**Risultati totali:** 19 ticket univoci analizzati

