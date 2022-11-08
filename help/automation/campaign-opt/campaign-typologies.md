---
product: campaign
title: Guida introduttiva alle tipologie di campagne
description: Scopri come configurare e implementare le tipologie di campagne
feature: Typology Rules
exl-id: 7832ffe1-eb65-4b37-9fc5-1374516755d9
source-git-commit: 7fe079c5473fa164405753c2be6cc8be16329f58
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 19%

---

# Guida introduttiva alle tipologie di campagne{#about-campaign-typologies}

**Ottimizzazione di Campaign** è il modulo Adobe Campaign che ti consente di controllare, filtrare e monitorare l’invio di consegne. Per evitare conflitti tra campagne, Adobe Campaign può sottoporre a test diverse combinazioni applicando specifiche regole di vincolo. Ciò garantisce che i messaggi inviati soddisfino le esigenze e le aspettative dei clienti, in linea con le politiche di comunicazione aziendali.

![](assets/do-not-localize/how-to-video.png) [Scopri questa funzione nel video](#typologies-video)

>[!NOTE]
>
>A seconda dell’offerta, è possibile includere l’ottimizzazione per Campaign o un componente aggiuntivo. Controlla il contratto di licenza.

## Regole di tipologia e tipologie {#typology-rules}

Per impostazione predefinita, Campaign viene fornito con tipologie integrate e regole di tipologia.

Una tipologia è un insieme di regole di verifica applicate a tutti i messaggi durante l’analisi della consegna.

Una tipologia di campagna può contenere diverse regole di tipologia, ma una consegna può fare riferimento a una sola tipologia.

Le regole di tipologia e le tipologie incorporate sono disponibili nella **[!UICONTROL Administration > Campaign management > Typology management]** nodo di Campaign Explorer.

Per ogni tipologia, la variabile **[!UICONTROL Rules]** consente di aggiungere, eliminare o visualizzare le regole di tipologia da applicare.

![](assets/campaign_opt_rules_tab.png)

Una volta create, le regole di tipologia sono raggruppate in campaign **tipologie** a cui si fa riferimento nelle consegne. [Ulteriori informazioni](#apply-typologies).


Campaign viene fornito con un set di impostazioni predefinite **Filtro** e **Controllo** regole:

* **Filtro** Le regole vengono utilizzate per escludere parte del target in base ai criteri. [Ulteriori informazioni](filtering-rules.md).
* **Controllo** Le regole ti consentono di verificare la validità dei messaggi prima che vengano inviati. [Ulteriori informazioni](control-rules.md).

Il componente aggiuntivo per l’ottimizzazione di Campaign fornisce due tipi aggiuntivi di **regole di tipologia**:

* **Pressione** regole che ti consentono di controllare l’affaticamento del marketing. [Ulteriori informazioni](pressure-rules.md).
* **Capacità** regole che consentono di limitare i carichi per garantire condizioni di elaborazione ottimali. [Ulteriori informazioni](consistency-rules.md#controlling-capacity).


>[!NOTE]
>
>Se utilizzi **Interazione** modulo per gestire le offerte, puoi anche creare **Presentazione dell&#39;offerta** regole di tipologia per controllare il flusso delle proposte di offerta utilizzando le regole di presentazione. [Ulteriori informazioni](../../v8/interaction/interaction-offer.md#offer-presentation).


## Passaggi chiave per creare e utilizzare le tipologie {#apply-typologies}

Per creare e utilizzare una tipologia per le consegne, segui i passaggi seguenti:

1. Crea regole di tipologia e crea una tipologia per farvi riferimento.
I passaggi dettagliati sono elencati nella sezione seguente:

   * [Regole di filtro](filtering-rules.md)
   * [Regole di controllo](control-rules.md)
   * [Regole di pressione](pressure-rules.md)
   * [Regole di capacità](consistency-rules.md)

1. Configura la consegna per utilizzare la tipologia creata. [Ulteriori informazioni](apply-rules.md#apply-a-typology-to-a-delivery).
1. Testa e controlla il comportamento attraverso le simulazioni delle campagne. [Ulteriori informazioni](campaign-simulations.md).

Durante la preparazione della consegna, i destinatari vengono esclusi quando il criterio è soddisfatto. Per monitorare le esclusioni, puoi controllare i registri.

I casi di utilizzo di esempio sulle regole di tipologia della pressione sono disponibili in [questa pagina](pressure-rules.md#use-cases-on-pressure-rules).

## Video tutorial {#typologies-video}

### Configurare la gestione dell’eccesso utilizzando le regole di tipologia

Questo video spiega come implementare la gestione dell’affaticamento in Adobe Campaign sfruttando le regole di tipologia.

>[!VIDEO](https://video.tv.adobe.com/v/333787?quality=12)

### Configurare la gestione dell’affaticamento utilizzando filtri predefiniti

La gestione dell’eccesso controlla la frequenza e la quantità di messaggi per evitare un’eccessiva sollecitazione dei destinatari. Se nell&#39;istanza della campagna non è presente il modulo di ottimizzazione della campagna, è possibile configurare un filtro predefinito che filtrerà la popolazione target in base al numero di messaggi ricevuti Questo video spiega come implementare la gestione dell&#39;affaticamento in Adobe Campaign utilizzando i filtri.

>[!VIDEO](https://video.tv.adobe.com/v/333778?quality=12)
