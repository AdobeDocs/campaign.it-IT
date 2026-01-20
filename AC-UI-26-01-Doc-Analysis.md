---
source-git-commit: 548b4be24e26a6970f953f92af1f89d829689592
workflow-type: tm+mt
source-wordcount: '1522'
ht-degree: 0%

---
# AC-UI-26-01 Analisi della documentazione

## Contenuto della versione successiva

In questo documento vengono analizzate le versioni mensili di JIRA del prodotto per le versioni AC-UI-26-01 e AC-UI-25-11 per pianificare le azioni di documentazione.

### Filtri JIRA

1. **[AC-UI-26-01-Monthly Stories](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-26-01-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Storie della versione principale
2. **[Miglioramenti di NEO-92400](https://jira.corp.adobe.com/issues/?jql=issueFunction%20in%20linkedIssuesOf(%27key%3DNEO-92400%27%2C%20%27is%20implemented%20by%27))** - Problemi collegati ai miglioramenti della versione
3. **[Storie mensili AC-UI-25-11](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20type%20%3D%20story%20order%20by%20status)** - Riporto delle versioni precedenti
4. **[AC-UI-25-11 Escluso 8.8.2](https://jira.corp.adobe.com/issues/?jql=project%20%3D%20NEO%20AND%20fixVersion%20%3D%20AC-UI-25-11-Monthly%20and%20fixVersion%20!%3D%208.8.2%20and%20type%20%3D%20story%20order%20by%20status)** - Versione precedente filtrata

&#x200B;---

## 🟢 Crea DOCAC

### [NEO-91565](https://jira.corp.adobe.com/browse/NEO-91565) - Aggiunta del supporto per i campi di personalizzazione (integrazione AEM avanzata)**Stato:** risolto\**Documento richiesto:** Sì\**DOCAC esistente:** Nessuno\**Azione:** Creare DOCAC

**Ambito:**
- Supporto dei documenti per i campi di personalizzazione nell’integrazione avanzata di AEM
- Flusso di lavoro dell’interfaccia utente e passaggi di configurazione
- Funzionalità di integrazione multilingue di AEM

**Descrizione funzionalità:**
Supporto per l’aggiunta di campi di personalizzazione nelle consegne tramite l’integrazione avanzata di AEM, che consente di inserire contenuti dinamici dai dati di Campaign nei modelli e-mail creati con AEM.

**Contesto:** ACS a parità ACC, requisito specifico di MSFT

**Riferimenti:** [Wiki multilingue AEM](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=2988189953)

&#x200B;---

### [NEO-93487](https://jira.corp.adobe.com/browse/NEO-93487) - Processo di calcolo della pianificazione della consegna (parità ACS)**Stato:** Nuovo\**Documento richiesto:** Sì\**DOCAC esistente:** Nessuno\**Azione:** Creare DOCAC

**Ambito:**
- Processo di calcolo della pianificazione della consegna dei documenti per le notifiche push
- Formule di pianificazione basate sul fuso orario
- Caricamento di file per il targeting di più fusi orari

**Descrizione funzionalità:**
Abilita la pianificazione delle consegne basata su file OOTB con orari di invio calcolati in base al fuso orario del destinatario, consentendo il targeting di singole consegne in più fusi orari con tempi di invio ottimizzati per area geografica.

**Contesto:** esigenze di parità da ACS a ACC basate sul cliente (H&amp;M)

**Riferimenti:** [documentazione ACS](https://experienceleague.adobe.com/en/docs/campaign-standard/using/testing-and-sending/scheduling-messages/computing-the-sending-date)

&#x200B;---

## 🔄 aggiornamento DOCAC

### [NEO-80973](https://jira.corp.adobe.com/browse/NEO-80973) - Disponibilità di Reporting dinamico per tutti gli utenti dell&#39;interfaccia utente Web&#x200B;**Stato:** In Corso\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-11070](https://jira.corp.adobe.com/browse/DOCAC-11070) (chiuso), [DOCAC-13432](https://jira.corp.adobe.com/browse/DOCAC-13432) (risolto)\**Azione:** Rivedi DOCAC

**Ambito:**
- Aggiornare le informazioni sulla disponibilità (ora per tutti gli utenti dell’interfaccia utente Web, non solo per la versione 8.7)
- Limitazioni della lingua del documento
- Visualizzazione più chiara delle metriche in conflitto con i rapporti precedenti

**Descrizione funzionalità:**
Il reporting dinamico è ora disponibile per tutti gli utenti dell’interfaccia utente web di Campaign (in precedenza limitata a clienti ACC 8.7), fornendo funzionalità avanzate di analisi e reporting personalizzato con un’interfaccia di tipo ACS.

**Contesto:** espansione funzionalità, dipendenza di compilazione back-end (8.8.1)

**Riferimenti:** [Wiki - Confronto report](https://wiki.corp.adobe.com/display/~kumarvishal/Reports+-+Client+console+vs+WebUI)

&#x200B;---

### [NEO-86754](https://jira.corp.adobe.com/browse/NEO-86754) - Test A/B&#x200B;**Stato:** In Corso\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-13104](https://jira.corp.adobe.com/browse/DOCAC-13104) (nuovo)\**Azione:** aggiornamento DOCAC

**Ambito:**
- Documentazione del flusso di lavoro completa per il test A/B
- Configurazione della variante e dell’impostazione della sperimentazione dei contenuti
- Definizione delle proporzioni del campione e criteri di selezione dei vincitori
- Raccolta e valutazione delle statistiche

**Descrizione funzionalità:**
Sperimentazione dei contenuti e test A/B per le consegne di e-mail, consentendo agli addetti al marketing di testare diverse varianti di contenuto, definire le dimensioni del campione, raccogliere statistiche sulle prestazioni e inviare automaticamente la variante vincente ai destinatari rimanenti.

**Contesto:** progetto Europa, requisito Microsoft, flag di funzionalità abilitato

**Riferimenti:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?pageId=3017705719), [Figma scherza](https://www.figma.com/design/4EfXEaA6OIV0D8rauuXSWX/A-B-Testing)

&#x200B;---

### [NEO-76126](https://jira.corp.adobe.com/browse/NEO-76126) - Authoring degli schemi (creazione di una nuova tabella, estensione degli schemi, accesso a un database esterno)**Stato:** In Corso\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-13826](https://jira.corp.adobe.com/browse/DOCAC-13826) (nuovo)\**Azione:** aggiornamento DOCAC

**Ambito:**
- Flusso di lavoro di authoring dello schema del documento (solo 3 opzioni: crea tabella, estende schema, accedi a database esterno)
- Definizione modulo per entità personalizzate
- Navigare tra le operazioni CRUD e gli schemi personalizzati
- Funzionalità di fase 2 e fase 3

**Descrizione funzionalità:**
Funzionalità di creazione degli schemi nell’interfaccia utente Web che consentono agli amministratori di creare nuove tabelle di database, estendere gli schemi esistenti con campi personalizzati e connettersi a database esterni, essenziale per la personalizzazione del modello di dati.

**Contesto:** requisiti Microsoft, progetto Europa, consegna graduale (fase 2 attiva, fase 3 feb)

**Riferimenti:** [PRD](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=AC+Web+UI+-+Schemas+PRD), [Figma](https://www.figma.com/design/lZkJso2HvXPbNjG0TmQTrC/Schemas)

&#x200B;---

### [NEO-92668](https://jira.corp.adobe.com/browse/NEO-92668) - Analisi Web&#x200B;**Stato:** Nuovo\**Documento richiesto:** Sì\**DOCAC esistente:** Nessuno\**Azione:** Creare DOCAC

**Ambito:**
- Configurazione account esterno Web Analytics
- Configurazione e autenticazione dell’integrazione
- Utilizzo dei dati di Analytics nelle campagne

**Descrizione funzionalità:**
Integrazione di Web Analytics che consente la connessione alle piattaforme di analisi web per il tracciamento e il reporting sulle prestazioni della campagna e sul comportamento dei visitatori del sito web.

**Contesto:** richiesta cliente (P2E-RSC), disponibilità ambiente in sospeso

**Riferimenti:** Nessuno fornito

&#x200B;---

### [NEO-86753](https://jira.corp.adobe.com/browse/NEO-86753) - Integrazione AEM per Live Copy/Copie per lingua&#x200B;**Stato:** Nuovo\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-13829](https://jira.corp.adobe.com/browse/DOCAC-13829) (risolto)\**Azione:** Rivedi DOCAC

**Ambito:**
- Sfogliare i modelli di consegna di AEM
- Crea Live Copy e copie per lingua con un clic
- Flusso di lavoro per la creazione di varianti di contenuto multilingue

**Descrizione funzionalità:**
L’integrazione semplificata di AEM consente la creazione con un solo clic di Live Copy e copie in lingua dai modelli di consegna di AEM, semplificando la creazione di campagne multilingue per gli utenti di AEM.

**Contesto:** requisito Microsoft, lavoro trasferito al team di Himanshu

**Riferimenti:** [documentazione ACS](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-experience-manager/creating-multilingual-email-aem.html)

&#x200B;---

### [NEO-88838](https://jira.corp.adobe.com/browse/NEO-88838) - Editor contenuto: usa variabili tema nel frammento&#x200B;**Stato:** Nuovo\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-12941](https://jira.corp.adobe.com/browse/DOCAC-12941) (nuovo)\**Azione:** aggiornamento DOCAC

**Ambito:**
- Variabili del tema in e-mail designer (Beta)
- Utilizzo dei temi nei frammenti
- Attivazione funzione Acrite

**Descrizione funzionalità:**
Supporto per l’utilizzo di variabili tema all’interno di frammenti di contenuto, per consentire un’applicazione coerente del sistema di branding e progettazione tra i componenti e-mail con la gestione centralizzata dei temi.

**Contesto:** In attesa, caratteristica Acrite da rivedere

**Riferimenti:** [ATU-5460](https://jira.corp.adobe.com/browse/ATU-5460)

&#x200B;---

## ➕ Crea DOCAC (miglioramenti)

### [NEO-92942](https://jira.corp.adobe.com/browse/NEO-92942) - Filtri predefiniti - Opzione Condiviso&#x200B;**Stato:** risolto\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-13697](https://jira.corp.adobe.com/browse/DOCAC-13697) (revisione del codice), [DOCAC-13522](https://jira.corp.adobe.com/browse/DOCAC-13522) (chiuso - helper)\**Azione:** Rivedi DOCAC

**Ambito:**
- Opzione condivisa per filtri predefiniti
- Filtrare la visibilità con altri operatori (comportamento ACC vs. Percorso del marchio)
- Gestione utente dei filtri condivisi

**Descrizione funzionalità:**
Ora è possibile contrassegnare i filtri predefiniti come &quot;condivisi&quot; per renderli visibili ad altri operatori, con un comportamento diverso per ACC (impostazione predefinita) e Brand Percorsi (filtro specifico per l’utente).

**Contesto:** miglioramento generatore regole, flag di funzionalità: enable-query-filter-shared

**Riferimenti:** relativi a [NEO-88441](https://jira.corp.adobe.com/browse/NEO-88441)

&#x200B;---

### [NEO-91299](https://jira.corp.adobe.com/browse/NEO-91299) - Attività di consegna continua&#x200B;**Stato:** Chiuso\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-13586](https://jira.corp.adobe.com/browse/DOCAC-13586) (nuovo), [DOCAC-13808](https://jira.corp.adobe.com/browse/DOCAC-13808) (chiuso - guida contestuale)\**Azione:** aggiornamento DOCAC

**Ambito:**
- Attività del flusso di lavoro di consegna continua
- Configurazione del selettore dei modelli di consegna
- Generazione automatica delle transizioni in uscita
- Opzioni di targeting (nessun accesso ai contenuti)

**Descrizione funzionalità:**
L’attività di consegna continua per i flussi di lavoro consente un’esecuzione ricorrente della consegna dai modelli, generando automaticamente transizioni in uscita per l’orchestrazione dei flussi di lavoro senza modifiche dei contenuti.

**Contesto:** Flag di funzionalità: enable-continuous-delivery

**Riferimenti:** correlati [NEO-67972](https://jira.corp.adobe.com/browse/NEO-67972)

&#x200B;---

### [NEO-90130](https://jira.corp.adobe.com/browse/NEO-90130) - Abilita caricamento file OOTB per notifiche push multilingue&#x200B;**Stato:** Chiuso\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-13606](https://jira.corp.adobe.com/browse/DOCAC-13606) (nuovo)\**Azione:** aggiornamento DOCAC

**Ambito:**
- Caricamento di file per notifiche push multilingue (iOS e Android)
- Formato CSV e mappatura campi
- Supporto push completo con funzionalità multilingue

**Descrizione funzionalità:**
Capacità di caricamento di file OOTB per creare consegne di notifiche push multilingue tramite importazione CSV, funzionalità ACS corrispondenti e configurazione efficiente di campagne multilingue.

**Contesto:** basato sul cliente (H&amp;M), da ACS a parità ACC, fondamentale per la migrazione

**Riferimenti:** [documentazione ACS](https://experienceleague.adobe.com/en/docs/campaign-standard/using/communication-channels/push-notifications/generating-csv-multilingual-push)

&#x200B;---

## ❌ Annullato/Non più Applicabile

### [NEO-91566](https://jira.corp.adobe.com/browse/NEO-91566) - Supporto per il tracciamento di CTA in webui&#x200B;**Stato:** Chiuso (Non Più Applicabile)\**Documento richiesto:** No\**DOCAC esistente:** [DOCAC-13821](https://jira.corp.adobe.com/browse/DOCAC-13821) (nuovo)\**Azione:** Chiudi DOCAC

**Motivo:** nuova funzionalità ACS per il supporto di MSFT - non avviata, informazioni in sospeso da MSFT, non previsto alcun lavoro nell&#39;interfaccia utente

**Contesto:** requisito di tracciamento CTA specifico per Microsoft

&#x200B;---

### [NEO-91564](https://jira.corp.adobe.com/browse/NEO-91564) - Supporto interfaccia utente multilingue di AEM&#x200B;**Stato:** Chiuso (Non Più Applicabile)\**Documento richiesto:** No\**DOCAC esistente:** [DOCAC-13822](https://jira.corp.adobe.com/browse/DOCAC-13822) (nuovo)\**Azione:** Chiudi DOCAC

**Motivo:** l&#39;interfaccia utente è gestita dal team di Himanshu (storia diversa)

**Contesto:** requisiti Microsoft, lavoro trasferito

&#x200B;---

### [NEO-91567](https://jira.corp.adobe.com/browse/NEO-91567) - Aggiunta del supporto per la funzione NRT&#x200B;**Stato:** Risolto (Non Più Applicabile)\**Documento richiesto:** No\**DOCAC esistente:** [DOCAC-13824](https://jira.corp.adobe.com/browse/DOCAC-13824) (nuovo)\**Azione:** Chiudi DOCAC

**Motivo:** nuova funzionalità specifica di ACS per MSFT - Specifiche disponibili ma nessun impatto sull&#39;interfaccia Web

**Contesto:** requisito Microsoft, messaggistica transazionale

&#x200B;---

### [NEO-91563](https://jira.corp.adobe.com/browse/NEO-91563) - API REST transazionale per l&#39;arricchimento basato su profili&#x200B;**Stato:** Risolto (Non Più Applicabile)\**Documento richiesto:** No\**DOCAC esistente:** [DOCAC-13825](https://jira.corp.adobe.com/browse/DOCAC-13825) (nuovo)\**Azione:** Chiudi DOCAC

**Motivo:** nessuna interfaccia utente Web, istanza aggiornata in sospeso, aggiornamento della build obbligatorio per la versione

**Contesto:** funzionalità endpoint REST API

&#x200B;---

### [NEO-92151](https://jira.corp.adobe.com/browse/NEO-92151) - Fase 2 della messaggistica transazionale di arricchimento basata su profili&#x200B;**Stato:** Risolto (Non Più Applicabile)\**Documento richiesto:** No\**DOCAC esistente:** [DOCAC-13823](https://jira.corp.adobe.com/browse/DOCAC-13823) (nuovo)\**Azione:** Chiudi DOCAC

**Motivo:** la storia non ha attività, contrassegnata come &quot;non più applicabile&quot;

**Contesto:** requisito Microsoft, progetto Europa

&#x200B;---

## 🟢 Documentazione pronta (da AC-UI-25-11)

### [NEO-90183](https://jira.corp.adobe.com/browse/NEO-90183) - Rich Push multilingue - Interfaccia utente&#x200B;**Stato:** Chiuso\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-13565](https://jira.corp.adobe.com/browse/DOCAC-13565) (nuovo)\**Azione:** Rivedi DOCAC

**Ambito:**
- Campi push potenziati per consegne multilingue
- Supporto delle piattaforme iOS e Android
- Configurazione di modelli e contenuti

**Descrizione funzionalità:**
Supporto di notifiche push potenziate con funzionalità multilingue, che consentono agli addetti al marketing di creare notifiche push migliorate con immagini, pulsanti e rich media per iOS e Android in più lingue.

**Contesto:** attività basate sul cliente (H&amp;M), consegnate tra il 25 e l&#39;11, lavoro di back-end completato

**Riferimenti:** [Wiki](https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=neolane&title=Rich+push+fields+in+multilingual)

&#x200B;---

### [NEO-84916](https://jira.corp.adobe.com/browse/NEO-84916) - Imposta e gestisci il processo di approvazione&#x200B;**Stato:** risolto\**Documento richiesto:** Sì\**DOCAC esistente:** [DOCAC-13827](https://jira.corp.adobe.com/browse/DOCAC-13827) (nuovo)\**Azione:** aggiornamento DOCAC

**Ambito:**
- Configurare gli operatori di convalida nella consegna/campagna
- Configurazione del flusso di lavoro di approvazione
- Processo di approvazione del contenuto e del target
- Supporto multicanale (e-mail, SMS, push, direct mail, call center, personalizzato)

**Descrizione funzionalità:**
Gestione dei processi di approvazione per abilitare i flussi di lavoro di convalida per la distribuzione di contenuti e il targeting, con assegnazione dell’operatore e tracciamento dell’approvazione per tutti i canali di consegna.

**Contesto:** orientato al cliente (Pierre Fabre), requisiti Microsoft, sviluppo completato e test

**Riferimenti:** [Documentazione classica](https://experienceleague.adobe.com/en/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval), [Figma si fa beffa](https://www.figma.com/design/r2vpqXoVyI3aucKgkt8TLN/Approvals)

&#x200B;---

## Riepilogo 📊 per azione

| Azione | Conteggio |
|--------|-------|
| 🟢 Crea DOCAC | 3 |
| 🔄 aggiornamento DOCAC | 6 |
| ✅ Revisione DOCAC | 3 |
| ❌ Chiudi DOCAC | 5 |
| **Totale** | **17** |

&#x200B;---

## ⚠️ domande aperte

1. NEO-93487 - Escalation H&amp;M: necessità di attenzione urgente per la pianificazione del processo di elaborazione
2. NEO-92668 - Web Analytics - In attesa della disponibilità dell’ambiente prima che la documentazione possa essere completata
3. NEO-76126 - Schemi Fase 3 - Fine febbraio ETA, è necessaria una documentazione separata
4. NEO-88838 - Variabili di tema - In attesa di revisione della funzione Acrite
5. Reporting dinamico: chiarimento delle indicazioni sulla visualizzazione delle metriche in conflitto con il reporting legacy

&#x200B;---

## 🔗 Epics correlati

- NEO-85263 - Da ACS a ACC (EUROPA) padre epico
- NEO-67972 - Miglioramenti al flusso di lavoro
- NEO-87980 - Integrazione avanzata di AEM
- NEO-90199 - Preparazione alla versione di Dynamic Reporting
- NEO-63067 - Sperimentazione dei contenuti UX/UI
- NEO-67726 - Test A/B e sperimentazione dei contenuti
- NEO-85274 - Schema e modulo (fase 2)
- NEO-87993 - Schema e modulo (fase 3)
