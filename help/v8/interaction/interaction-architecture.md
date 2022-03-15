---
title: Comprendere l’architettura di interazione di Campaign
description: Nozioni di base sull’architettura di interazione di Campaign
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 7a710960-7e41-4462-bd5e-18e874aa46f8
source-git-commit: dafdf471fcaf2b6c6e3e8d5028cd65e35e7df3eb
workflow-type: tm+mt
source-wordcount: '1314'
ht-degree: 0%

---

# Comprendere gli ambienti e l’architettura di interazione di Campaign

## Ambienti {#environments}

Esistono due ambienti per ogni dimensione di targeting utilizzata per la gestione delle offerte:

* A **progettazione** ambiente in cui il gestore offerte si occupa di creare e classificare le offerte, modificarle e avviare il processo di approvazione in modo che possano essere utilizzate. In questo ambiente vengono definite anche le regole per ogni categoria, gli spazi di offerta su cui è possibile presentare le offerte e i filtri predefiniti utilizzati per definire l’idoneità di un’offerta.

   Le categorie possono anche essere pubblicate manualmente nell’ambiente online.

   La procedura per l’approvazione delle offerte è dettagliata [in questa sezione](interaction-offer.md#approve-offers).

* A **live** è possibile trovare l’ambiente in cui sono state approvate le offerte dall’ambiente di progettazione, nonché i vari spazi di offerta, filtri, categorie e regole configurati nell’ambiente di progettazione. Durante una chiamata al motore di offerta, il motore utilizzerà sempre le offerte dall’ambiente live.

Un’offerta viene distribuita solo sugli spazi di offerta selezionati durante il processo di approvazione. Pertanto, un’offerta può essere live ma inutilizzabile su uno spazio di offerta anch’esso attivo.

## Interazioni in entrata e in uscita {#interaction-types}

Il modulo di interazione Adobe Campaign propone due tipi di interazioni:

* **in entrata** interazioni, avviate da un contatto. [Ulteriori informazioni](interaction-present-offers.md)
* **in uscita** interazioni, avviate da un gestore di consegna Campaign. [Ulteriori informazioni](interaction-send-offers.md)

Questi due tipi di interazioni possono essere eseguite in **modalità unitaria** (l&#39;offerta è calcolata per un singolo contatto), oppure **modalità batch** (l&#39;offerta è calcolata per un insieme di contatti). Generalmente, le interazioni in entrata vengono eseguite in modalità unitaria e le interazioni in uscita vengono eseguite in modalità batch. Tuttavia, ci possono essere alcune eccezioni, per [messaggi transazionali](../send/transactional.md) ad esempio, quando l’interazione in uscita viene eseguita in modalità unitaria.

Non appena un&#39;offerta può o deve essere presentata (secondo le configurazioni eseguite), il motore di offerta svolge il ruolo di intermediario: calcola automaticamente la migliore offerta possibile per un contatto tra quelle disponibili combinando i dati ricevuti sul contatto e le diverse regole che possono essere applicate come specificato nell&#39;applicazione.

![](assets/architecture_interaction2.png)

## Architettura distribuita

Per supportare la scalabilità e fornire un servizio 24 ore su 24 e 7 giorni su 7 sul canale in entrata, il **Interazione** Il modulo è implementato in un&#39;architettura distribuita. Questo tipo di architettura è già utilizzato con [Centro messaggi](../dev/architecture.md#transac-msg-archi) ed è costituito da diverse istanze:

* una o più istanze di controllo dedicate al canale in uscita e contenenti la base di progettazione marketing e ambiente
* una o più istanze di esecuzione dedicate al canale in entrata

![](assets/interaction_powerbooster_schema.png)

Le istanze di controllo sono dedicate al canale in entrata e contengono la versione online del catalogo. Ogni istanza di esecuzione è indipendente e dedicata a un segmento di contatto (ad esempio, un’istanza di esecuzione per paese). Le chiamate al motore di offerta devono essere eseguite direttamente sull&#39;esecuzione (un URL specifico per istanza di esecuzione). Poiché la sincronizzazione tra le istanze non è automatica, le interazioni dello stesso contatto devono essere inviate attraverso la stessa istanza.

### Sincronizzazione {#synchronization}

La sincronizzazione delle offerte viene eseguita tramite pacchetti. Nelle istanze di esecuzione, tutti gli oggetti catalogo hanno il prefisso del nome dell’account esterno. Ciò significa che è possibile supportare più istanze di controllo (ad esempio istanze di sviluppo e produzione) in una stessa istanza di esecuzione.

>[!CAUTION]
>
>Utilizzare nomi interni brevi ed espliciti.

Le offerte vengono distribuite automaticamente e quindi pubblicate sulle istanze di esecuzione e controllo.

Le offerte eliminate nell’ambiente di progettazione sono disabilitate in tutte le istanze online. Le proposte e le offerte obsolete vengono eliminate automaticamente su tutte le istanze dopo il periodo di eliminazione (specificato nell’assistente alla distribuzione di ogni istanza) e il periodo scorrevole (specificato nelle regole di tipologia delle proposizioni in arrivo).

![](assets/interaction_powerbooster_schema2.png)

Viene creato un flusso di lavoro per ogni ambiente e account esterno per la sincronizzazione delle proposte. La frequenza di sincronizzazione può essere regolata per ogni ambiente e account esterno.

È necessario conoscere i seguenti meccanismi di sincronizzazione:

* Se utilizzi la funzione di ritorno da un ambiente anonimo a un ambiente identificato, questi due ambienti devono trovarsi nella stessa istanza di esecuzione.
* La sincronizzazione tra più istanze di esecuzione non viene eseguita in tempo reale. Le interazioni dello stesso contatto devono essere inviate alla stessa istanza. L’istanza di controllo deve essere dedicata al canale in uscita (in tempo reale).
* Il database di marketing non viene sincronizzato automaticamente. I dati di marketing utilizzati nei pesi e nelle regole di idoneità devono essere duplicati nelle istanze di esecuzione. Questo processo non è standard, è necessario svilupparlo durante il periodo di integrazione.
* La sincronizzazione della proposta viene eseguita esclusivamente dalla connessione FDA.
* Se utilizzi Interaction e Message Center nella stessa istanza, la sincronizzazione verrà eseguita tramite il protocollo FDA in entrambi i casi.

### Configurazione dei pacchetti {#packages-configuration}

Qualsiasi estensione di schema direttamente collegata a **Interazione** (offerte, proposte, destinatari, ecc.) deve essere distribuito sulle istanze di esecuzione.

La **Interazione** Il pacchetto è installato su tutte le istanze (controllo ed esecuzione). Sono disponibili due pacchetti aggiuntivi: un pacchetto per le istanze di controllo e l&#39;altro per ogni istanza di esecuzione.

>[!NOTE]
>
>Quando installi il pacchetto, il **long** digitare i campi **nms:proposizione** tabella come l’ID della proposta, diventa **int64** digitare i campi. Questo tipo di dati è descritto in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/schema-reference/schema-structure.html?lang=en#mapping-the-types-of-adobe-campaign-dbms-data){target=&quot;_blank&quot;}.

La durata di conservazione dei dati è configurata su ogni istanza (tramite il **[!UICONTROL Data purge]** nella procedura guidata di distribuzione). Nelle istanze di esecuzione, tale periodo deve corrispondere alla profondità storica necessaria per il calcolo delle regole di tipologia (periodo scorrevole) e delle regole di idoneità.

Sulle istanze di controllo:

1. Crea un account esterno per istanza di esecuzione:

   ![](assets/interaction_powerbooster1.png)

   * Completare l’etichetta e aggiungere un nome interno breve ed esplicito.
   * Seleziona **[!UICONTROL Execution instance]**.
   * Seleziona l’opzione **[!UICONTROL Enabled]**.
   * Completa i parametri di connessione per l’istanza di esecuzione.
   * Ogni istanza di esecuzione deve essere collegata a un ID. Questo ID viene assegnato quando si fa clic sul pulsante **[!UICONTROL Initialize connection]** pulsante .
   * Controllare il tipo di applicazione utilizzata: **[!UICONTROL Message Center]**, **[!UICONTROL Interaction]** o entrambi.
   * Immettere l&#39;account FDA utilizzato. Un operatore deve essere creato sulle istanze di esecuzione e deve avere i seguenti diritti di lettura e scrittura sul database dell&#39;istanza in questione:

      ```
      grant SELECT ON nmspropositionrcp, nmsoffer, nmsofferspace, xtkoption, xtkfolder TO user;
      grant DELETE, INSERT, UPDATE ON nmspropositionrcp TO user;
      ```
   >[!NOTE]
   >
   >L’indirizzo IP dell’istanza di controllo deve essere autorizzato sulle istanze di esecuzione.

1. Configura l’ambiente:

   ![](assets/interaction_powerbooster2.png)

   * Aggiungi l’elenco delle istanze di esecuzione.
   * Per ciascuno di essi, specifica il periodo di sincronizzazione e i criteri di filtro (ad esempio, per paese).

      >[!NOTE]
      >
      >Se incontri un errore, puoi consultare i flussi di lavoro di sincronizzazione e le notifiche delle offerte. Questi sono disponibili nei flussi di lavoro tecnici dell’applicazione.

Se, per motivi di ottimizzazione, nelle istanze di esecuzione viene duplicata solo una parte del database di marketing, puoi specificare uno schema limitato collegato all’ambiente per consentire agli utenti di utilizzare solo i dati disponibili nelle istanze di esecuzione. Puoi creare un’offerta utilizzando dati non disponibili nelle istanze di esecuzione. A questo scopo, devi disattivare la regola sugli altri canali limitando questa regola sul canale in uscita (**[!UICONTROL Taken into account if]** (campo).

![](assets/ita_filtering.png)

### Opzioni di manutenzione {#maintenance-options}

Elenco delle opzioni di manutenzione disponibili nell’istanza di controllo:

>[!CAUTION]
>
>Queste opzioni devono essere utilizzate solo per casi di manutenzione specifici.

* **`NmsInteraction_LastOfferEnvSynch_<offerEnvId>_<executionInstanceId>`**: l’ultima data in cui un ambiente è stato sincronizzato in una determinata istanza.
* **`NmsInteraction_LastPropositionSynch_<propositionSchema>_<executionInstanceIdSource>_<executionInstanceIdTarget>`**: l&#39;ultima data in cui le proposizioni da un dato schema sono state sincronizzate da un&#39;istanza all&#39;altra.
* **`NmsInteraction_MapWorkflowId`**: un&#39;opzione contenente l&#39;elenco di tutti i flussi di lavoro di sincronizzazione generati.

L’opzione seguente è disponibile nelle istanze di esecuzione:

**NmsExecutionInstanceId**: contenente l&#39;ID istanza.

### Installazione pacchetti {#packages-installation}

Se la tua istanza non aveva in precedenza il **Interazione** pacchetto, non è necessaria alcuna migrazione. Per impostazione predefinita, la tabella delle proposte sarà in 64 bit dopo l&#39;installazione dei pacchetti.

>[!CAUTION]
>
>A seconda del volume di proposte esistenti nell’istanza, questa operazione potrebbe richiedere un po’ di tempo.

* Se l&#39;istanza ha poche o nessuna proposta, non è necessaria alcuna modifica manuale della tabella di proposta. La modifica verrà eseguita quando vengono installati i pacchetti.
* Se l&#39;istanza ha molte proposte, è meglio modificare la struttura della tabella delle proposte prima di installare i pacchetti di controllo e di eseguirli. È consigliabile eseguire le query durante un periodo di bassa attività.

>[!NOTE]
>
>Se hai eseguito configurazioni specifiche nella tabella delle proposte, adatta le query di conseguenza.


Esistono due metodi:

**Tabella di lavoro** (consigliato)

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
