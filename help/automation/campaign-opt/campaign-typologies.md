---
product: campaign
title: Introduzione alle tipologie di campagne
description: Scopri come configurare e implementare le tipologie di campagne
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 50688c051b9d8de2b642384963ac1c685c0c33ee
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 19%

---

# Introduzione alle tipologie di campagne{#about-campaign-typologies}

**Ottimizzazione campagne** è il modulo di Adobe Campaign che consente di controllare, filtrare e monitorare l&#39;invio delle consegne. Per evitare conflitti tra campagne, Adobe Campaign può sottoporre a test diverse combinazioni applicando specifiche regole di vincolo. Ciò garantisce che i messaggi inviati soddisfino le esigenze e le aspettative dei clienti, in linea con le politiche di comunicazione aziendali.

![](assets/do-not-localize/how-to-video.png) [Guarda il video su questa funzione](#typologies-video)

>[!NOTE]
>
>A seconda dell’offerta, è possibile includere l’ottimizzazione di Campaign o un componente aggiuntivo. Controlla il contratto di licenza.

## Regole e tipologie di tipologia {#typology-rules}

Per impostazione predefinita, Campaign è dotato di tipologie integrate e regole di tipologia.

Una tipologia è un insieme di regole di verifica applicate a tutti i messaggi durante l’analisi della consegna.

Una tipologia di campagna può contenere diverse regole di tipologia, ma una consegna può fare riferimento a una sola tipologia.

Le regole e le tipologie incorporate sono disponibili nella cartella **[!UICONTROL Administration > Campaign management > Typology management]** di Campaign Explorer.

Per ogni tipologia, la scheda **[!UICONTROL Rules]** ti consente di aggiungere, eliminare o visualizzare le regole di tipologia da applicare.

![](assets/campaign_opt_rules_tab.png)

Una volta create, le regole di tipologia sono raggruppate nelle **tipologie** della campagna a cui si fa riferimento nelle consegne. [Ulteriori informazioni](#apply-typologies).


Campaign viene fornito con un set di regole predefinite **Filtro** e **Controllo**:

* **Le regole di filtro** vengono utilizzate per escludere parte della destinazione in base a criteri. [Ulteriori informazioni](filtering-rules.md).
* **Le regole di controllo** consentono di verificare la validità dei messaggi prima che vengano inviati. [Ulteriori informazioni](control-rules.md).

Il componente aggiuntivo Ottimizzazione Campaign fornisce due ulteriori tipi di **regole di tipologia**:

* **Regole di pressione** che consentono di controllare l&#39;eccesso di marketing. [Ulteriori informazioni](pressure-rules.md).
* **Regole di capacità** che consentono di limitare i carichi per garantire condizioni di elaborazione ottimali. [Ulteriori informazioni](consistency-rules.md#controlling-capacity).


>[!NOTE]
>
>Se utilizzi il modulo **Interaction** per gestire le offerte, puoi anche creare **Regole di tipologia di presentazione delle offerte** per controllare il flusso delle proposte di offerta utilizzando le regole di presentazione. [Ulteriori informazioni](../../v8/interaction/interaction-offer.md#offer-presentation).


## Passaggi chiave per creare e utilizzare le tipologie {#apply-typologies}

Per creare e utilizzare una tipologia per le consegne, segui i passaggi seguenti:

1. Crea regole di tipologia e crea una tipologia per farvi riferimento.
I passaggi dettagliati sono elencati nella sezione seguente:

   * [Regole di filtro](filtering-rules.md)
   * [Regole di controllo](control-rules.md)
   * [Regole di pressione](pressure-rules.md)
   * [Regole di capacità](consistency-rules.md)

1. Configura la consegna in modo da utilizzare la tipologia creata. [Ulteriori informazioni](apply-rules.md#apply-a-typology-to-a-delivery).
1. Puoi testare e controllare il comportamento tramite simulazioni di campagne. [Ulteriori informazioni](campaign-simulations.md).

Durante la preparazione della consegna, i destinatari vengono esclusi quando viene soddisfatto il criterio. Per monitorare le esclusioni, puoi controllare i registri.

Casi d&#39;uso di esempio sulle regole di tipologia della pressione sono disponibili in [questa pagina](pressure-rules.md#use-cases-on-pressure-rules).

## Video tutorial {#typologies-video}

### Configurare la gestione dell’eccesso utilizzando le regole di tipologia

Questo video spiega come implementare la gestione dell’eccesso in Adobe Campaign sfruttando le regole di tipologia.

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### Gestire l’eccesso di comunicazioni mediante filtri predefiniti

La gestione dell’eccesso controlla la frequenza e la quantità di messaggi per evitare un’eccessiva sollecitazione dei destinatari. Se nell’istanza della campagna non è presente il modulo di ottimizzazione, puoi configurare un filtro predefinito che filtrerà la popolazione target in base al numero di messaggi ricevuti
Questo video spiega come implementare la gestione dell’eccesso in Adobe Campaign utilizzando i filtri.

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)
