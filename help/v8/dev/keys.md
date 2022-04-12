---
title: Gestione delle chiavi in Campaign
description: Guida introduttiva alla gestione delle chiavi
exl-id: ef06cb6b-1b25-4dbe-8fd0-f880ec9d645b
source-git-commit: 2d0b40e49afdfd71e8bb5c3f0b1d569a715420b2
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 2%

---

# Gestione delle chiavi e unicità {#key-management}

In Campaign v8, la chiave primaria è un identificatore ID universale univoco (UUID), che è una stringa sui caratteri. Per creare questo UUID, l’elemento principale dello schema deve contenere **autouuid** e **autopk** attributi impostati su **true**.

Adobe Campaign v8 viene fornito con Snowflake come database di base. L’architettura distribuita del database di Snowflake non fornisce meccanismi per gestire l’unicità di una chiave all’interno di una tabella: gli utenti finali sono responsabili di garantire la coerenza delle chiavi all’interno del database Adobe Campaign.

Per preservare la coerenza relazionale del database, è obbligatorio evitare duplicati sulle chiavi e in particolare sulle chiavi primarie. I duplicati sulle chiavi primarie generano problemi con le attività del flusso di lavoro di gestione dei dati, ad esempio **Query**, **Reconciliation**, **Update data** e altro ancora.

Come best practice, l&#39;Adobe raccomanda di adottare [Rileva](#detect-duplicates) e [Corretto](#correct-duplicates) strategia come parte del processo di gestione dei dati complessivo, nel caso in cui siano state caricate chiavi duplicate nel database.

## Rileva duplicati{#detect-duplicates}

Campaign viene fornito con una nuova guardrail che rimuove automaticamente qualsiasi UUID duplicato da un pubblico durante la preparazione della consegna. Questo nuovo meccanismo impedisce che si verifichi un errore durante la preparazione di una consegna.

>[!CAUTION]
>
>Le chiavi duplicate non sono limitate agli UUID. Può accadere con gli ID, incluse le chiavi personalizzate create nelle tabelle personalizzate.

In qualità di utente finale, puoi controllare queste informazioni nei registri di consegna: alcuni destinatari possono essere esclusi dal target principale a causa di una chiave duplicata. In tal caso, viene visualizzato il seguente avviso: `Exclusion of duplicates (based on the primary key or targeted records)`.

![](assets/delivery-log-duplicates.png)

In questo caso, puoi creare un flusso di lavoro per identificare le chiavi duplicate. Potrai quindi correggere queste chiavi. Per eseguire questa operazione, effettua le seguenti operazioni:

1. Crea un nuovo flusso di lavoro.

   ![](assets/new-wf.png)

1. Aggiungi un **Query** attività
1. Seleziona la **Destinatario** tabella

   ![](assets/add-query-on-rcp.png)

1. Aggiungi un **Deduplication** e deduplica sulla chiave primaria (UUID). Mantieni un solo duplicato e controlla il  **Genera completamento** per creare una transizione in uscita per i duplicati.

   ![](assets/deduplicate.png)

1. Salva i duplicati in un elenco utilizzando un’attività di aggiornamento elenco .

   ![](assets/list-update.png)

Ora puoi accedere ai destinatari duplicati direttamente dall’elenco. Anche se la transizione contiene solo una delle righe duplicate, tutti i duplicati verranno registrati nell’elenco.


## Duplicati corretti{#correct-duplicates}

Per correggere i duplicati, i clienti devono aggiornare i dati di Campaign. Il tipo di azione è strettamente legato alla natura dei duplicati e all’implementazione. Possiamo affrontare casi multipli che dovrebbero richiedere una strategia di mitigazione diversa (rimozione, unione o aggiornamento).

>[!IMPORTANT]
>
>Le chiavi primarie duplicate non consentono di utilizzare attività del flusso di lavoro integrate per selezionare o aggiornare una riga specifica. A causa dell’UUID duplicato, la deduplicazione dei dati avrà esito negativo e potrà influire sull’integrità del database. Di conseguenza, si consiglia vivamente di correggere i duplicati.

Ad esempio:

* **Caso 1** - Destinatari duplicati con lo stesso UUID e le stesse informazioni di profilo (stessa e-mail, nome e così via) : i destinatari sembrano duplicati &quot;reali&quot; e la mitigazione potrebbe consistere nel rimuovere uno dei duplicati.
Un altro approccio potrebbe essere quello di unire le informazioni di un destinatario all&#39;altro.

* **Caso 2** - Destinatari duplicati con lo stesso UUID ma informazioni di profilo diverse (e-mail, nome e così via diverse): questa volta, sembra che ci siano profili diversi e potresti voler mantenere entrambi nel database di Campaign, il che significa che potremmo preferire solo l’aggiornamento di uno dei duplicati che generano un nuovo UUID. [Ulteriori informazioni in questa esenzione](#deduplicate-sample).

A seconda della strategia di mitigazione, puoi sempre eseguire query sull’elenco da un altro flusso di lavoro e quindi applicare l’aggiornamento in base alle tue esigenze. Per ulteriori informazioni, contatta l’Adobe .

### Esempio di deduplicazione{#deduplicate-sample}

In caso di destinatari duplicati, puoi conservare entrambi i record nel database di Campaign. In tal caso, devi aggiornare uno di questi con un nuovo UUID.

Per eseguire una query di aggiornamento SQL nel database cloud è possibile utilizzare **Gestione dati SQL** attività del flusso di lavoro ed esegui il seguente aggiornamento SQL:

```sql
update nmsrecipient set urecipientid = uuid_string()
where semail = 'bretta37@adobe.com'
and urecipientid = 'c04d93f2-6012-4668-b523-88db1262cd46';
```

![](assets/sql-data-management.png)

Una volta aggiornata la riga selezionata con un nuovo UUID, puoi controllare la riga aggiornata dall’interfaccia e notare che l’UUID è stato aggiornato come previsto. È inoltre possibile rilevare i duplicati nel database eseguendo il **Rileva duplicati** workflow [come spiegato qui](#detect-duplicates).
