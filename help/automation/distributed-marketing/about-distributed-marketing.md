---
product: campaign
title: Introduzione al marketing distribuito
description: Introduzione al marketing distribuito
feature: Distributed Marketing
role: User
exl-id: c9f5b277-3ad8-4316-94b9-789d37813b8b
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 0%

---

# Introduzione al marketing distribuito{#about-distributed-marketing}

Adobe Campaign offre un&#39;applicazione **Marketing distribuito** per l&#39;implementazione di campagne di cooperazione tra entità centrali (sedi centrali, dipartimenti di marketing, ecc.) ed entità locali (punti vendita, agenzie regionali, ecc.). Questa cooperazione si basa su un&#39;area di lavoro condivisa nota come **[!UICONTROL list of campaign packages]**, in cui i modelli e le istanze della campagna creati a livello centrale vengono offerti alle entità locali.

L’entità centrale fornisce campagne che le entità locali possono utilizzare. Le campagne vengono materializzate da pacchetti che rappresentano campagne locali o collaborative. Per utilizzare una campagna, l’entità locale deve ordinarla e l’ordine deve essere approvato.

>[!CAUTION]
>
>Il modulo Marketing distribuito è un&#39;opzione **Campaign**. Controlla il contratto di licenza.

## Terminologia {#terminology}

* **Entità centrali**

  Gli enti centrali sono composti da operatori di marketing incaricati di specificare le comunicazioni e assistere gli enti locali nell’esecuzione della loro campagna di marketing.

  Il modulo di marketing distribuito consente all’entità centrale di:

   * configurare pacchetti di campagne di marketing per enti locali,
   * aumentare il grado di autonomia delle entità locali per quanto riguarda la scelta di comunicazione, targeting, contenuto, ecc. tra clienti e potenziali.
   * gestire e controllare i costi,
   * gestisce una rete di agenzie.

* **Entità locali**

  Gli enti locali possono essere agenzie, negozi o gruppi di operatori locali specifici (responsabili nazionali o regionali, gestori di marchi, ecc.).

  Il Marketing distribuito consente alle entità locali di disporre di maggiore autonomia, ottimizzando al contempo i costi di esecuzione.

* **Localizzazione**

  La localizzazione è la capacità di un’entità locale di modificare la destinazione e il contenuto di una campagna. Il possibile livello di localizzazione dipende dal tipo di campagna e dalla relativa implementazione.

* **Elenco dei pacchetti di campagne**

  L’elenco dei pacchetti di campagne contiene le campagne disponibili per le entità locali.

* **Pacchetto campagne**

  Modello (o istanza della campagna) creato da un&#39;entità centrale e reso disponibile a un set di entità locali.

* **Campagna locale**

  Una campagna locale è un&#39;istanza creata da un modello a cui si fa riferimento nell&#39;elenco di **[!UICONTROL campaign packages]** con una **pianificazione di esecuzione specifica**. Il suo obiettivo è soddisfare una necessità di comunicazione locale utilizzando un modello di campagna configurato e configurato dall’entità centrale.

  Il grado di autonomia dell’entità locale dipende dall’implementazione utilizzata.

  Consulta [Creazione di una campagna locale](creating-a-local-campaign.md).

* **Campagna collaborativa**

  Una campagna collaborativa è una campagna la cui pianificazione di esecuzione **è definita** dall&#39;entità centrale, che può essere utilizzata dall&#39;entità locale. Il contenuto rimane lo stesso per ogni entità locale, ma i costi sono condivisi. Per partecipare, gli enti locali si abbonano alla campagna collaborativa.

   * **[!UICONTROL Collaborative campaign (by form)]**: consigliato per campagne che coinvolgono fino a 300 entità locali. L’entità locale può immettere parametri predefiniti per il targeting e la personalizzazione del contenuto in un modulo web. Il modulo può essere un modulo Adobe Campaign o un modulo esterno (client Extranet). Un amministratore funzionale può definire e configurare il modulo in base a un modello di modulo definito dall&#39;integratore. Per ordinare la campagna, l’entità locale ha solo bisogno dell’accesso web.
   * **[!UICONTROL Collaborative campaign (by campaign)]**: consigliato per campagne indirizzate a decine di entità locali. Questo tipo di campagna crea campagne secondarie per ogni entità locale. Una volta che **[!UICONTROL collaborative campaign (by campaign)]** è stato approvato dall&#39;entità centrale, la campagna è resa disponibile all&#39;entità locale, che può modificarla. L’esecuzione viene sincronizzata automaticamente tra le campagne principali e secondarie. L’entità locale deve avere accesso a un’istanza per ordinare una campagna e parteciparvi.
   * **[!UICONTROL Collaborative campaign (by target approval)]**: consigliato per campagne indirizzate a diverse migliaia di entità locali. L&#39;entità locale riceve un elenco di contatti predefinito dall&#39;entità centrale. L’entità locale decide se mantenere o meno alcuni contatti in base al contenuto della campagna tramite un modulo web. Le entità locali vengono dedotte dall&#39;elenco dei contatti selezionati. Per partecipare alla campagna, l’entità locale ha solo bisogno dell’accesso web.
   * **[!UICONTROL Collaborative campaign (simple)]**: questa modalità garantisce la compatibilità con i processi di esecuzione specifici delle versioni precedenti.

  Consulta [Creazione di una campagna collaborativa](creating-a-collaborative-campaign.md).

**Ordinamento dei pacchetti della campagna**

Se un’entità locale si registra per una campagna, questa viene inserita in un ordine che raggruppa tutte le informazioni relative alla localizzazione della campagna.

## Area di lavoro {#workspace}

È possibile accedere all&#39;elenco dei pacchetti della campagna dalla scheda **Campagne**: fare clic sul collegamento **[!UICONTROL Campaign packages]**.

![](assets/mkg_dist_home_local_op.png)

Questa finestra consente a tutti gli operatori locali di visualizzare le campagne disponibili per la propria agenzia locale.

Nel caso delle agenzie centrali, questa finestra visualizza tutti i pacchetti disponibili nell’elenco dei pacchetti della campagna e offre collegamenti aggiuntivi per la modifica dell’elenco.

## Operatori ed entità {#operators-and-entities}

Iniziare specificando gli operatori di entità centrali e locali tramite la cartella **[!UICONTROL Access management]**.

![](assets/s_advuser_mkg_dist_tree.png)

### Operatori {#operators}

È necessario creare operatori centrali e locali.

Gli operatori centrali devono appartenere al gruppo di operatori **[!UICONTROL Central management]** o disporre dell&#39;autorizzazione denominata **[!UICONTROL CENTRAL]**.

Gli operatori locali devono appartenere al gruppo di operatori **[!UICONTROL Local management]** o disporre dell&#39;autorizzazione denominata **[!UICONTROL LOCAL]**. Devono anche essere collegati al loro ente locale.

![](assets/s_advuser_mkg_dist_local_create.png)

### Entità organizzative {#organizational-entities}

Per creare un&#39;entità organizzativa, fare clic sulla cartella **[!UICONTROL Administration > Access management > Organizational entities]** e sull&#39;icona **[!UICONTROL New]** sopra l&#39;elenco delle entità.

![](assets/s_advuser_mkg_dist_local_list.png)

Ogni entità organizzativa contiene informazioni di identificazione (etichetta, nome interno, informazioni di contatto, ecc.) e gruppi coinvolti nel processo di approvazione dell’ordine. Questi sono definiti nella sezione **[!UICONTROL Notifications and approvals]** trovata nella scheda **[!UICONTROL General]**.

* Definire un gruppo di notifica dei pacchetti: gli operatori di questo gruppo riceveranno una notifica ogni volta che un nuovo pacchetto viene aggiunto all’elenco dei pacchetti della campagna e ogni volta che una campagna diventa disponibile.
* Seleziona il gruppo di revisori incaricati di approvare gli ordini, ovvero quelli incaricati di approvare le campagne ordinate dall’entità locale.
* Infine, seleziona il gruppo di revisori incaricati di approvare la campagna locale (target, contenuto, budget, ecc.). Questo gruppo può essere aggiunto a durante l’ordine di una campagna, a seconda del modello.

>[!NOTE]
>
>Il processo di approvazione è presentato nella sezione [Processo di approvazione](creating-a-local-campaign.md#approval-process).

## Implementazione {#implementation}

Le campagne di Marketing distribuito vengono create e pubblicate dall’entità centrale. Essi possono essere utilizzati da enti locali e centrali in funzione delle necessità.

La procedura di implementazione dipende dal tipo di pacchetto della campagna utilizzato e dai livelli di delega delle entità locali.

### Attività dell&#39;integratore {#integrator-side}

1. Creare entità locali.
1. Collega i destinatari agli operatori che gestiscono le entità locali.

   ![](assets/mkg_dist_local_entity_association.png)

1. Specificare i diritti e le regole di esplorazione per le entità locali
1. Specifica il set di campi necessari per la localizzazione della campagna:

   * la definizione dell&#39;obiettivo e la dimensione massima,
   * definizione del contenuto,
   * pianificazione dell&#39;esecuzione (data di contatto e data di estrazione), **solo per gli operatori locali**,
   * estensione dello schema dell’ordine con tutti i campi aggiuntivi necessari.

1. Crea un modulo web (Adobe o extranet) che ti consenta di visualizzare i parametri di localizzazione, valutare il target e il budget, nonché visualizzare in anteprima il contenuto e approvare l’ordine.

   Per **campagne collaborative (per approvazione target)**, crea la tabella in cui verranno salvate le approvazioni per ogni entità locale.

### Attività di amministrazione funzionali {#functional-administrator-side}

Questi passaggi devono essere eseguiti durante la creazione di ogni campagna.

1. Aggiorna il modulo con i campi utilizzati per la localizzazione della campagna.
1. Crea un’istanza da un modello di campagna appropriato (campagna collaborativa) o duplica il modello di campagna (campagna locale).
1. Configura la campagna con i campi di localizzazione e il riferimento del modulo.
1. Pubblica la campagna.

### Attività dell’operatore locale {#local-operator-side}

Queste fasi devono essere eseguite per ogni campagna.

1. Una volta ricevuta la notifica della disponibilità del pacchetto della campagna, specifica la posizione della campagna (facoltativo).
1. Valuta il target, il budget, ecc.
1. Anteprima del contenuto della campagna.
1. Ordina la campagna.
