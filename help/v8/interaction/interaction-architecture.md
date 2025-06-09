---
title: Architettura dell’interazione di Campaign
description: Nozioni di base sull’architettura di interazione di Campaign
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 7a710960-7e41-4462-bd5e-18e874aa46f8
source-git-commit: 1a0b473b005449be7c846225e75a227f6d877c88
workflow-type: tm+mt
source-wordcount: '1305'
ht-degree: 0%

---

# Ambienti e architettura di interazione di Campaign

## Ambienti {#environments}

Esistono due ambienti per ogni dimensione di targeting utilizzata durante la gestione delle offerte:

* Ambiente **design** in cui il gestore delle offerte si occupa di creare e classificare le offerte, modificarle e avviare il processo di approvazione in modo che possano essere utilizzate. In questo ambiente sono definite anche le regole per ogni categoria, gli spazi di offerta su cui possono essere presentate le offerte e i filtri predefiniti utilizzati per definire l’idoneità di un’offerta.

  Le categorie possono inoltre essere pubblicate manualmente nell&#39;ambiente online.

  Il processo di approvazione delle offerte è descritto in [questa sezione](interaction-offer.md#approve-offers).

* Ambiente **live** in cui sono disponibili offerte approvate dall&#39;ambiente di progettazione, nonché vari spazi di offerta, filtri, categorie e regole configurati nell&#39;ambiente di progettazione. Durante una chiamata al motore delle offerte, questo utilizzerà sempre le offerte provenienti dall’ambiente live.

Un’offerta viene distribuita solo sugli spazi dell’offerta selezionati durante il processo di approvazione. Pertanto, un’offerta può essere live ma inutilizzabile in uno spazio dell’offerta che è anche live.

## Interazioni in entrata e in uscita {#interaction-types}

Il modulo di interazione di Adobe Campaign propone due tipi di interazioni:

* **interazioni in entrata**, avviate da un contatto. [Ulteriori informazioni](interaction-present-offers.md)
* **interazioni in uscita**, avviate da un responsabile consegna campagna. [Ulteriori informazioni](interaction-send-offers.md)

Questi due tipi di interazioni possono essere eseguiti in **modalità unitaria** (l&#39;offerta è calcolata per un singolo contatto) o in **modalità batch** (l&#39;offerta è calcolata per un insieme di contatti). In genere, le interazioni in entrata vengono eseguite in modalità unitaria, mentre le interazioni in uscita vengono eseguite in modalità batch. Tuttavia, possono esserci alcune eccezioni, ad esempio per [messaggi transazionali](../send/transactional.md), in cui l&#39;interazione in uscita viene eseguita in modalità unitaria.

Non appena un’offerta può o deve essere presentata (in base alle configurazioni effettuate), il motore di offerta svolge il ruolo di intermediario: calcola automaticamente la migliore offerta possibile per un contatto tra quelli disponibili combinando i dati ricevuti sul contatto e le diverse regole che possono essere applicate come specificato nell’applicazione.

![](assets/architecture_interaction2.png)

## Architettura distribuita

Per supportare la scalabilità e fornire un servizio 24 ore su 24, 7 giorni su 7 sul canale in entrata, il modulo **Interaction** è implementato in un&#39;architettura distribuita. Questo tipo di architettura è già in uso con [Centro messaggi](../architecture/architecture.md#transac-msg-archi) ed è costituito da diverse istanze:

* una o più istanze di controllo dedicate al canale in uscita e contenenti la base di progettazione di marketing e ambiente
* una o più istanze di esecuzione dedicate al canale in entrata

![](assets/interaction_powerbooster_schema.png)

Le istanze di controllo sono dedicate al canale in entrata e contengono la versione online del catalogo. Ogni istanza di esecuzione è indipendente e dedicata a un segmento di contatto (ad esempio, un’istanza di esecuzione per paese). Le chiamate al motore di offerta devono essere eseguite direttamente all’esecuzione (un URL specifico per ogni istanza di esecuzione). Poiché la sincronizzazione tra le istanze non è automatica, le interazioni dello stesso contatto devono essere inviate tramite la stessa istanza.

### Sincronizzazione {#synchronization}

La sincronizzazione delle offerte viene eseguita tramite pacchetti. Nelle istanze di esecuzione, tutti gli oggetti catalogo sono preceduti dal nome dell’account esterno. Ciò significa che diverse istanze di controllo (ad esempio istanze di sviluppo e produzione) possono essere supportate sulla stessa istanza di esecuzione.

>[!CAUTION]
>
>Utilizza nomi interni brevi ed espliciti.

Le offerte vengono distribuite automaticamente e quindi pubblicate nelle istanze di esecuzione e controllo.

Le offerte eliminate nell’ambiente di progettazione vengono disabilitate su tutte le istanze online. Le proposte e le offerte obsolete vengono eliminate automaticamente in tutte le istanze dopo il periodo di eliminazione (specificato nell’assistente alla distribuzione di ogni istanza) e il periodo scorrevole (specificato nelle regole di tipologia delle proposte in arrivo).

![](assets/interaction_powerbooster_schema2.png)

Per ogni ambiente e account esterno viene creato un flusso di lavoro per la sincronizzazione della proposta. La frequenza di sincronizzazione può essere regolata per ogni ambiente e account esterno.

È necessario conoscere i seguenti meccanismi di sincronizzazione:

* Se utilizzi la funzione di fallback da un ambiente anonimo a un ambiente identificato, questi due ambienti devono trovarsi nella stessa istanza di esecuzione.
* La sincronizzazione tra più istanze di esecuzione non viene eseguita in tempo reale. Le interazioni dello stesso contatto devono essere inviate alla stessa istanza. L’istanza di controllo deve essere dedicata al canale in uscita (non in tempo reale).
* Il database di marketing non viene sincronizzato automaticamente. I dati di marketing utilizzati nelle ponderazioni e nelle regole di idoneità devono essere duplicati nelle istanze di esecuzione. Questo processo non è standard, è necessario svilupparlo durante il periodo di integrazione.
* La sincronizzazione delle proposte viene eseguita esclusivamente dalla connessione FDA.
* Se utilizzi Interaction e Message Center (Centro messaggi) sulla stessa istanza, in entrambi i casi la sincronizzazione verrà eseguita tramite il protocollo FDA.

### Configurazione pacchetti {#packages-configuration}

Tutte le estensioni dello schema direttamente collegate all&#39;**interazione** (offerte, proposte, destinatari, ecc.) devono essere distribuite nelle istanze di esecuzione.

Il pacchetto **Interaction** è installato in tutte le istanze (controllo ed esecuzione). Sono disponibili due pacchetti aggiuntivi: uno per le istanze di controllo e l’altro per ogni istanza di esecuzione.

>[!NOTE]
>
>Durante l&#39;installazione del pacchetto, i campi di tipo **long** della tabella **nms:proposition**, ad esempio l&#39;ID della proposta, diventano campi di tipo **int64**. Questo tipo di dati è descritto nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/schema-structure.html#mapping-the-types-of-adobe-campaign-dbms-data){target="_blank"}.

La durata di conservazione dei dati è configurata in ogni istanza (tramite la finestra **[!UICONTROL Data purge]** nella procedura guidata di distribuzione). Nelle istanze di esecuzione, questo periodo deve corrispondere alla profondità storica necessaria per le regole di tipologia (periodo scorrevole) e le regole di idoneità da calcolare.

Sulle istanze di controllo:

1. Crea un account esterno per istanza di esecuzione:

   ![](assets/interaction_powerbooster1.png)

   * Completa l’etichetta e aggiungi un nome interno breve ed esplicito.
   * Seleziona **[!UICONTROL Execution instance]**.
   * Seleziona l’opzione **[!UICONTROL Enabled]**.
   * Completa i parametri di connessione per l’istanza di esecuzione.
   * Ogni istanza di esecuzione deve essere collegata a un ID. Questo ID viene assegnato quando si fa clic sul pulsante **[!UICONTROL Initialize connection]**.
   * Controllare il tipo di applicazione utilizzato: **[!UICONTROL Message Center]**, **[!UICONTROL Interaction]** o entrambi.
   * Immettere l&#39;account FDA utilizzato. Un operatore deve essere creato nelle istanze di esecuzione e deve disporre dei seguenti diritti di lettura e scrittura sul database dell’istanza in questione:

     ```
     grant SELECT ON nmspropositionrcp, nmsoffer, nmsofferspace, xtkoption, xtkfolder TO user;
     grant DELETE, INSERT, UPDATE ON nmspropositionrcp TO user;
     ```

   >[!NOTE]
   >
   >L&#39;indirizzo IP dell&#39;istanza di controllo deve essere autorizzato nelle istanze di esecuzione.

1. Configurare l’ambiente:

   ![](assets/interaction_powerbooster2.png)

   * Aggiungi l’elenco delle istanze di esecuzione.
   * Per ciascuno, specifica il periodo di sincronizzazione e i criteri di filtro (ad esempio, per paese).

     >[!NOTE]
     >
     >Se riscontri un errore, puoi consultare i flussi di lavoro di sincronizzazione e le notifiche delle offerte. Questi si trovano nei flussi di lavoro tecnici dell’applicazione.

Se, per motivi di ottimizzazione, nelle istanze di esecuzione viene duplicata solo una parte del database di marketing, puoi specificare uno schema con restrizioni collegato all’ambiente per consentire agli utenti di utilizzare solo i dati disponibili nelle istanze di esecuzione. Puoi creare un’offerta utilizzando dati non disponibili nelle istanze di esecuzione. A tale scopo, è necessario disattivare la regola sugli altri canali limitandola sul canale in uscita (campo **[!UICONTROL Taken into account if]**).

![](assets/ita_filtering.png)

### Opzioni di manutenzione {#maintenance-options}

Elenco delle opzioni di manutenzione disponibili nell’istanza di controllo:

>[!CAUTION]
>
>Queste opzioni devono essere utilizzate solo per casi di manutenzione specifici.

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: data dell&#39;ultima sincronizzazione di un ambiente in una determinata istanza.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: ultima data in cui le proposte da un dato schema sono state sincronizzate da un&#39;istanza all&#39;altra.
* **`NmsInteraction_MapWorkflowId`**: opzione contenente l&#39;elenco di tutti i flussi di lavoro di sincronizzazione generati.

Nelle istanze di esecuzione è disponibile la seguente opzione:

**NmsExecutionInstanceId**: opzione contenente l&#39;ID istanza.

### Installazione dei pacchetti {#packages-installation}

Se in precedenza l&#39;istanza non aveva il pacchetto **Interaction**, non è necessaria alcuna migrazione. Per impostazione predefinita, la tabella della proposta è a 64 bit dopo l’installazione dei pacchetti.

>[!CAUTION]
>
>A seconda del volume di proposte esistenti nell’istanza, questa operazione potrebbe richiedere del tempo.

* Se l’istanza ha poche proposte o non le ha, non è necessaria alcuna modifica manuale della tabella delle proposte. La modifica verrà eseguita al momento dell&#39;installazione dei pacchetti.
* Se l’istanza dispone di numerose proposte, è meglio modificare la struttura della tabella delle proposte prima di installare i pacchetti di controllo ed eseguirli. È consigliabile eseguire le query durante un periodo di bassa attività.

>[!NOTE]
>
>Se hai eseguito configurazioni specifiche nella tabella della proposta, adatta di conseguenza le query.


Esistono due metodi:

**Tabella di lavoro** (scelta consigliata)

```
CREATE TABLE NmsPropositionRcp_tmp AS SELECT * FROM nmspropositionrcp WHERE 0=1;
ALTER TABLE nmspropositionrcp_tmp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
INSERT INTO nmspropositionrcp_tmp SELECT * FROM nmspropositionrcp;
DROP TABLE nmspropositionrcp;
CREATE INDEX proposition_id ON NmsPropositionRcp (ipropositionid);
CREATE INDEX nmspropositionrcp_deliveryid ON NmsPropositionRcp (ideliveryid);
CREATE INDEX nmspropositionrcp_lastmodified ON NmsPropositionRcp (tslastmodified);
CREATE INDEX nmspropositionrcp_offerid ON NmsPropositionRcp (iofferid);
CREATE INDEX nmspropositionrcp_offerspaceid ON NmsPropositionRcp (iofferspaceid);
CREATE INDEX nmspropositionrcp_recipientidid ON NmsPropositionRcp (irecipientid);
ALTER TABLE nmspropositionrcp_tmp RENAME TO nmspropositionrcp;
```

**Modifica tabella**

```
ALTER TABLE nmspropositionrcp
  ALTER COLUMN ipropositionid TYPE bigint,
  ALTER COLUMN iinteractionid TYPE bigint;
```
