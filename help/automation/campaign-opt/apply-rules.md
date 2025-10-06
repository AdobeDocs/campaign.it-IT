---
product: campaign
title: Applicare le regole di tipologia
description: Scopri come applicare le regole di tipologia
feature: Typology Rules
exl-id: 4ec3bbe1-fc4c-4b1e-989c-f4dcf8ee8d5e
source-git-commit: 95c944963feee746a2bb83a85f075134c91059d1
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 7%

---

# Applicare le regole di tipologia{#applying-rules}

## Applicare una tipologia a una consegna {#apply-a-typology-to-a-delivery}

Per applicare le regole di tipologia create, associale a una tipologia e fai riferimento a essa nella consegna.

A questo scopo, segui la procedura indicata di seguito:

1. Creare una tipologia di campagna.

   Le tipologie sono accessibili tramite la cartella **[!UICONTROL Administration > Campaign Management > Typology management]** > **[!UICONTROL Typologies]** di Campaign Explorer.

1. Vai alla scheda **[!UICONTROL Rules]**, fai clic sul pulsante **[!UICONTROL Add]** e seleziona le regole da applicare con questa tipologia.

   ![](assets/campaign_opt_pressure_sample_1_6.png)

1. Salva la tipologia: viene aggiunta all’elenco delle tipologie esistenti.
1. Apri la consegna a cui desideri applicare le regole.
1. Individuare le proprietà di consegna e aprire la scheda **[!UICONTROL Typology]**.
1. Seleziona la tipologia nell’elenco a discesa.

   ![](assets/campaign_opt_pressure_sample_1_7.png)

   >[!NOTE]
   >
   >La tipologia può essere definita nel modello di consegna, da applicare automaticamente a tutte le consegne create utilizzando questo modello.

## Definire le condizioni di applicazione {#define-application-conditions}

È possibile limitare il campo di applicazione di una regola in base alle proprie esigenze (ad eccezione delle regole di controllo).

È possibile configurare le regole di tipologia in modo che riguardino solo determinate consegne a cui sono collegate o determinati destinatari tra i target di una consegna.

Per definire le condizioni di applicazione di una regola, fare clic sul collegamento **[!UICONTROL Edit the rule application conditions...]** nella scheda **[!UICONTROL General]**.

Quindi utilizza l&#39;[editor query](../../v8/start/query-editor.md) per definire le condizioni di filtro. Nell’esempio seguente, la regola di capacità riguarda solo le consegne con la parola &quot;offerta&quot; nell’etichetta o le consegne create prima del 1° aprile 2013.

![](assets/campaign_opt_create_capacity_criterion.png)

>[!NOTE]
>
>Per le regole di filtro, puoi selezionare la condizione di applicazione dei criteri di filtro, che possono dipendere dalla consegna o dalla struttura della consegna. [Ulteriori informazioni](filtering-rules.md#condition-a-filtering-rule).

## Regola frequenza di calcolo {#adjust-calculation-frequency}

Gli arbitrati vengono rieseguiti automaticamente ogni notte tramite il flusso di lavoro di pulizia del database. Tuttavia, i valori possono essere salvati anche dopo questo periodo.

In effetti, alcuni calcoli utilizzano valori che non cambiano quotidianamente. Sarebbe quindi irrilevante ricalcolare i dati ogni giorno e sovraccaricare il database senza alcun risultato. Ad esempio, se un processo arricchisce il database di marketing con punteggi di propensione del cliente e informazioni di acquisto su base settimanale, non è necessario ricalcolare i dati basati su questi valori ogni giorno.

A questo scopo, il campo **[!UICONTROL Frequency]** della scheda **[!UICONTROL General]** ti consente di definire un periodo massimo durante il quale viene salvato il targeting. Per impostazione predefinita, il valore **0** indica che il calcolo rimane valido fino alla successiva esecuzione di un nuovo arbitrato giornaliero.

Per salvare i risultati oltre questo periodo, immettere un valore maggiore di 12 nel campo **[!UICONTROL Frequency]**: una volta scaduto questo periodo, tutte le regole vengono riapplicate.

L&#39;opzione **[!UICONTROL Re-apply the rule at the start of personalization]** ti consente di applicare la regola automaticamente durante la fase di personalizzazione, anche se il periodo indicato nel campo **[!UICONTROL Frequency]** è ancora valido.

## Selezione della fase di applicazione della regola {#selecting-the-rule-application-phase}

Le regole di tipologia vengono applicate in una sequenza specifica durante le fasi di targeting, analisi e personalizzazione delle consegne a cui si riferiscono.

### Ordine di esecuzione {#execution-order}

Nella modalità operativa standard, le regole vengono applicate nella sequenza seguente:

1. Regole di controllo, se applicate all’inizio del targeting.
1. Regole di filtro:

   * Regole di applicazione native per la qualifica dell&#39;indirizzo: indirizzo definito/indirizzo/indirizzo non verificato sul inserisco nell&#39;elenco Bloccati di/indirizzo messo in quarantena/qualità dell&#39;indirizzo.
   * Regole di filtro definite dall’utente.
   * Regola di deduplicazione sull’indirizzo o sull’identificatore (applicata se necessario).

1. Regole di pressione.
1. Regole di capacità.
1. Regole di controllo, se applicate alla fine del targeting.
1. Regole di controllo, se applicate all’inizio della personalizzazione. Se le regole dell’utente (filtro/pressione/capacitivo) sono scadute e devono essere ricalcolate, vengono applicate durante questo passaggio.
1. Regole di controllo, se applicabili alla fine della personalizzazione.

>[!NOTE]
>
>Se utilizzi il modulo di interazione di Campaign, le regole di idoneità per le offerte vengono applicate contemporaneamente alle regole di filtro (per le offerte che si trovano nei profili di consegna) o durante la fase di personalizzazione, durante la chiamata al motore di offerta.

È possibile adattare la sequenza di esecuzione delle regole dello stesso tipo utilizzando il campo appropriato nella scheda **[!UICONTROL General]** della regola. Quando più regole vengono eseguite durante la stessa fase di elaborazione dei messaggi, è possibile configurarne la sequenza di esecuzione nel campo **[!UICONTROL Execution sequence]**.

Ad esempio, una regola di pressione con ordine di esecuzione di 20 viene eseguita prima di una regola di pressione con ordine di esecuzione di 30.

### Regole di controllo {#control-rules}

Per le regole **[!UICONTROL Control]**, puoi decidere a quale punto del ciclo di vita della consegna viene applicata la regola: prima o dopo il targeting, all&#39;inizio della personalizzazione, alla fine dell&#39;analisi. Selezionare il valore da applicare nell&#39;elenco a discesa del campo **[!UICONTROL Phase]** nella scheda **[!UICONTROL General]** della regola di tipologia.

![](assets/campaign_opt_define_control_phase.png)

I valori possibili sono:

* **[!UICONTROL At the start of targeting]**

  Per evitare che il passaggio di personalizzazione venga eseguito in caso di errori, puoi applicare la regola di controllo qui.

* **[!UICONTROL After targeting]**

  Se è necessario conoscere il volume della destinazione per applicare la regola di controllo, selezionare questa fase.

  Ad esempio, la regola di controllo **[!UICONTROL Check proof size]** si applica dopo ogni fase di targeting: questa regola impedisce la personalizzazione dei messaggi se sono presenti troppi destinatari bozza.

* **[!UICONTROL At the start of personalization]**

  Questa fase deve essere selezionata se il controllo riguarda l’approvazione della personalizzazione dei messaggi. La personalizzazione dei messaggi viene eseguita durante la fase di analisi.

* **[!UICONTROL At the end of the analysis]**

  Quando un controllo richiede il completamento della personalizzazione dei messaggi, seleziona questa fase.

## Configurazioni aggiuntive {#additional-configurations}

### Controllare il traffico SMTP in uscita {#control-outgoing-smtp-traffic}

Come opzione, puoi utilizzare il campo **[!UICONTROL Managing affinities with IP addresses]** per collegare le consegne al server di consegna (MTA) questa affinità. Questo ti consente di limitare il numero di e-mail per consegne specifiche a computer o indirizzi di output.

![](assets/campaign_opt_select_ip_affinity.png)

>[!NOTE]
>
>La gestione delle affinità non è applicabile per le tipologie **[!UICONTROL Filtering]**.

<!--
>Affinities are defined in the instance configuration file, on the Adobe Campaign server. For more on this, refer to [this section](../../installation/using/about-initial-configuration.md).-->

### Ottimizzazione delle campagne e marketing distribuito {#campaign-optimization-and-distributed-marketing}

La scheda **[!UICONTROL Distributed Marketing]** ti consente di definire la nuova mappatura di tipologie e/o regole che si applica quando una campagna condivisa viene ordinata e/o riservata. Le tipologie/regole definite per un’entità locale (collegate a quelle definite per l’entità centrale) sostituiscono le regole/tipologie collegate all’entità centrale. La nuova mappatura consente di adattare le regole dell’entità centrale alle entità locali che ordinano la campagna.

![](assets/simu_campaign_opti_distrib_mkg.png)

>[!NOTE]
>
>Nelle tipologie e nelle regole di tipologia, la scheda **[!UICONTROL Distributed Marketing]** viene aggiunta se la licenza include questa opzione: verificare il contratto di licenza.\
>Per ulteriori informazioni sul Marketing distribuito, consulta [questa sezione](../distributed-marketing/about-distributed-marketing.md).
