---
title: Versioni e aggiornamenti di Campaign
description: Ulteriori informazioni sulle versioni e sugli aggiornamenti di Campaign
feature: Release Notes
role: User
level: Beginner
exl-id: 04bda36f-051f-41a3-84b3-6af3c5e34ab2
TQID: https://experienceleague.adobe.com/EaoWEmt7vNplA6Cs6CdMvP-iwia6BkaDRjawsPoa6fs
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 59a1ad4bbb194222f0c2b86117cc7dc6ecc3335d
workflow-type: tm+mt
source-wordcount: 1190
ht-degree: 10%

---

# Versioni e aggiornamenti {#upgrades}

Adobe Campaign v8 è offerto esclusivamente come soluzione **Managed Cloud Services**. Adobe gestisce ed esegue automaticamente ogni aggiornamento lato server: non è prevista alcuna distribuzione on-premise o ibrida di v8 e non è previsto alcun aggiornamento del server per pianificare o eseguire autonomamente l’operazione.

Adobe Campaign viene aggiornato regolarmente. Questa frequenza regolare di aggiornamenti mira a ottenere il massimo e più recente nelle tue mani, mantenendo il tuo ambiente sicuro e migliorando la tua esperienza con il nostro prodotto.

In qualità di utente di Managed Cloud Services:

* L’istanza del server Campaign viene aggiornata da Adobe con ogni nuova versione, in modo automatico e senza richiedere alcuna azione da parte tua.
* Il rappresentante Adobe ti contatta prima di un aggiornamento che influisce sul tuo ambiente.
* **La console client è l&#39;unico componente di cui sei responsabile.** Deve essere aggiornato alla stessa versione del server Campaign. Scopri come aggiornare la console client in questa [pagina](../start/connect.md#upgrade-ac-console).

Inoltre, in qualità di cliente, assicurati di utilizzare la versione supportata più recente dei sistemi elencati nella [Matrice di compatibilità](compatibility-matrix.md).

>[!IMPORTANT]
>
>Adobe si riserva il diritto di applicare patch di sicurezza critiche all’ambiente in hosting in qualsiasi momento, senza preavviso, al fine di correggere le vulnerabilità il più rapidamente possibile. Queste patch vengono distribuite senza interruzione del servizio. Risolvere una vulnerabilità critica ha la precedenza sulla notifica preventiva.

## Versioni di Campaign {#versions}

Adobe Campaign rilascia periodicamente versioni di prodotto che migliorano le prestazioni, la sicurezza, la logica e l’usabilità dell’infrastruttura Campaign.

Gli aggiornamenti possono essere:

* **Aggiornamenti principali**, da una versione principale a un&#39;altra, ad esempio da v7 a v8. Questi aggiornamenti apportano nuove funzionalità, miglioramenti, aggiornamenti di compatibilità e sicurezza e correzioni.
* **Aggiornamenti secondari**, da una versione secondaria a un&#39;altra, ad esempio dalla versione 8.5 alla versione 8.6. Questi aggiornamenti apportano miglioramenti, aggiornamenti di compatibilità e sicurezza e correzioni.
* **Aggiornamenti patch**, da una versione patch a un&#39;altra, ad esempio dalla versione v8.5.1 alla versione v8.5.2. Questi aggiornamenti apportano aggiornamenti e correzioni di sicurezza.

Informazioni dettagliate su ogni nuova versione sono disponibili nelle [Note sulla versione](release-notes.md). Le correzioni relative alla sicurezza vengono inserite nelle note di ogni versione. Vedere [Come posso essere informato del rilascio di una nuova versione?](#upgrades-0) di seguito.

Per garantire una configurazione stabile, Adobe consiglia di installare **esattamente la stessa versione** su tutti i server Campaign. Inoltre, salvo diversa indicazione nelle [Note sulla versione](release-notes.md), la console client deve essere in **la stessa versione** dell&#39;istanza del server. Scopri come aggiornare la console client in questa [pagina](../start/connect.md#upgrade-ac-console).

## Mantieni aggiornata la console client {#ac-upgrades}

In qualità di cliente di Campaign Managed Services, quando è disponibile una nuova versione di Campaign, l’infrastruttura server viene aggiornata da Adobe senza ulteriori azioni da parte tua.

Poiché l&#39;aggiornamento del server viene eseguito automaticamente, la **console client** è l&#39;unica posizione in cui è possibile visualizzare un&#39;interruzione se non viene aggiornata contemporaneamente. Se la versione della console non corrisponde alla versione del server:

* Potresti perdere la possibilità di collegarti all’istanza Campaign fino a quando la console non viene aggiornata.
* La console smette di beneficiare delle correzioni e degli aggiornamenti di sicurezza forniti nella versione in cui il server è già stato spostato, anche se il server stesso è aggiornato.

Per evitare questo problema, aggiorna la console client non appena ricevi una notifica di una nuova versione. Scopri come [aggiornare la console client](../start/connect.md#upgrade-ac-console).

In qualità di cliente, devi inoltre assicurarti di utilizzare le versioni più recenti supportate dei sistemi elencati nella [Matrice di compatibilità](compatibility-matrix.md).

## Domande frequenti {#upgrades-faq}

### Come si controlla la versione di Campaign? {#version}

Per verificare la versione di Campaign, accedi al menu **Guida > Informazioni su...** dalla console client.

![](assets/ac-version.png)

Accedi alle seguenti informazioni:

* Numero di **versione** della console client e del server applicazioni. Nell’esempio precedente, la versione è 8.1.5 sia per la console client che per il server applicazioni.
* Il numero SHA, tra parentesi.
* Un collegamento per contattare l’Assistenza clienti di Adobe.
* Collegamenti alla Policy per i cookie, alle Condizioni d’uso e all’Informativa sulla privacy di Adobe.

>[!NOTE]
>
>Se la versione visualizzata per la console client non corrisponde a quella visualizzata per il server applicazioni, aggiornare la console come descritto in [Mantenere aggiornata la console client](#ac-upgrades).

### Come posso essere informato del rilascio di una nuova versione? {#upgrades-0}

Le nuove versioni e le modifiche apportate, incluse le correzioni di sicurezza, sono elencate nelle [Note sulla versione](release-notes.md). Quando sarà disponibile una nuova versione, il rappresentante Adobe ti contatterà e aggiornerà gli ambienti server; dovrai aggiornare separatamente la console client (vedi [Mantenere aggiornata la console client](#ac-upgrades)).

Per ricevere informazioni sulle nuove versioni della soluzione Experience Cloud e sui relativi contenuti, abbonati alla comunicazione [Aggiornamenti dei prodotti priority Adobe](https://www.adobe.com/it/subscription/priority-product-update.html){target="_blank"}.

Puoi anche visitare la [Community di Campaign](https://experienceleaguecommunities.adobe.com/t5/custom/page/page-id/Community-TopicsPage?profile.language=it&style=all&sort=date&order=desc&filters=adobe-campaign-classic-community&topic=Campaign+v8){target="_blank"} per ricevere informazioni sugli aggiornamenti delle versioni.

### Perché la mia organizzazione ha bisogno di un aggiornamento? {#upgrades-1}

L’aggiornamento garantisce che il tuo account sia protetto da vulnerabilità e utilizzi una tecnologia delle prestazioni aggiornata.

In genere, l’aggiornamento alla versione più recente comporta:

* **Sicurezza migliorata**

  La sicurezza richiede attenzione costante e manutenzione proattiva. I rischi relativi alla sicurezza sono onnipresenti e non possono essere ignorati: ogni aggiornamento di Campaign migliora la sicurezza. Una combinazione di tecnologie lavora insieme per potenziare Adobe Campaign e tutte devono essere aggiornate. Adobe applica automaticamente questi aggiornamenti al server; l’aggiornamento graduale della console client garantisce che la stessa protezione si estenda anche a esso.

* **Supporto migliorato**

  La maggior parte dei problemi critici vengono risolti con gli aggiornamenti e possono essere evitati del tutto. Gli aggiornamenti regolari contribuiscono a ridurre le sfide da affrontare e ad aumentare l&#39;efficienza. La riduzione nel volume di richieste di assistenza determina risoluzioni più rapide e maggiore attenzione ai problemi che non sono correlati agli aggiornamenti.

* **Manutenzione e stabilità migliorate**

  Nel tempo, il team Adobe Campaign individua modi efficaci per migliorare la stabilità e le prestazioni del prodotto e per risolvere i problemi noti. L’aggiornamento consente di aggiornare l’istanza con questi miglioramenti ed elimina le problematiche comuni riscontrate dalle organizzazioni che registrano una rapida crescita e/o complessità all’interno delle istanze Campaign. I team di marketing e IT dell’organizzazione coglieranno subito i miglioramenti implementati nello stack tecnologico di Campaign.

* **Rimani connesso**

  La console client può comunicare in modo affidabile solo con un server che esegue la stessa versione. Mantenere aggiornata la console, ogni volta che il server viene aggiornato, è ciò che mantiene intatta la connessione e la sicurezza e le correzioni che ne derivano.

### Qual è il processo e la tempistica per un aggiornamento? {#upgrades-2}

In qualità di cliente v8, Adobe gestisce l’aggiornamento del server end-to-end:

1. Quando è disponibile una nuova versione o il tuo account necessita di passare a una versione, ricevi una notifica dal rappresentante Adobe.
1. Adobe aggiorna l&#39;infrastruttura server: non è richiesta alcuna azione da parte dell&#39;utente per questo passaggio.
1. Dal tuo lato, l&#39;unica azione necessaria è aggiornare la console client in modo che corrisponda a e confermare che i sistemi nella [Matrice di compatibilità](compatibility-matrix.md) sono ancora supportati. Vedi [Mantenere aggiornata la console client](#ac-upgrades).

Qui trovi un team di responsabili dell’Assistenza clienti, Product Manager, tecnici, specialisti TechOps e consulenti di prodotto che potrà assisterti e garantire un’esperienza fluida.

>[!NOTE]
>
>Le patch di sicurezza critiche possono essere applicate all’ambiente ospitato al di fuori di questo ciclo di notifica — vedi la nota nella parte superiore di questa pagina.
