---
title: Utilizzare i tipi di pubblico in Campaign
description: Utilizzare i tipi di pubblico in Campaign
feature: Audiences
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 19%

---

# Utilizzare i tipi di pubblico in Campaign{#gs-ac-audiences}

I profili sono contatti memorizzati nel database Campaign.

In Adobe Campaign, **destinatari** sono i profili predefiniti target per l’invio di consegne (e-mail, SMS, ecc.). I dati dei destinatari memorizzati nel database ti consentono di filtrare il target che riceverà una determinata consegna e di aggiungere dati di personalizzazione nel contenuto della consegna. Nel database sono presenti altri tipi di profili. Essi sono progettati per diversi utilizzi. Ad esempio, i profili di seed vengono creati per testare le consegne prima che vengano inviate al target finale.

Scopri come importare, aggiornare e gestire profili e pubblico [in questa sezione](../audiences/gs-audiences.md).

## Creare elenchi{#create-lists}

Un elenco è un set statico di contatti che possono essere targetizzati nelle azioni di consegna o aggiornati durante un’importazione o un’altra azione del flusso di lavoro. Ad esempio, una popolazione estratta dal database tramite una query può essere memorizzata come elenco.

![](../assets/do-not-localize/glass.png) Scopri come creare e gestire gli elenchi in [questa pagina](../audiences/create-audiences.md).

## Filtrare il database{#filter-the-database}

La configurazione del filtro consente di selezionare i dati da un elenco **[!UICONTROL dynamically]**: quando i dati vengono modificati, i dati filtrati vengono aggiornati. Puoi creare filtri personalizzati o utilizzare i filtri incorporati per definire un pubblico di destinazione.

![](../assets/do-not-localize/glass.png) Scopri come creare e gestire i filtri in [questa pagina](../audiences/create-filters.md).

## Creare un pubblico in un flusso di lavoro

Il targeting può essere creato tramite una combinazione di query in una sequenza grafica in un flusso di lavoro. Puoi creare un pubblico di destinazione in base alle tue esigenze. Per visualizzare l’editor del flusso di lavoro, fai clic sul pulsante **[!UICONTROL Targeting and workflows]** nel dashboard della campagna.

![](../assets/do-not-localize/book.png) Scopri come creare un pubblico in un flusso di lavoro della campagna in [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow){target=&quot;_blank&quot;}.


## Profili attivi{#active-profiles}

In base al contratto, a ciascuna istanza di Campaign viene fornito un numero specifico di profili attivi conteggiati a scopo di fatturazione. Per informazioni sul numero di profili attivi acquistati, fai riferimento al contratto più recente.

**Profilo** un registro di informazioni (ad esempio: un record [Tabella destinatari](../dev/datamodel.md) oppure una tabella esterna contenente un ID cookie, un ID cliente, un identificatore mobile o altre informazioni pertinenti a un particolare canale) che rappresenta un cliente finale, potenziale o lead. I profili sono considerati attivi se sono stati targetizzati o se sono stati comunicati negli ultimi 12 mesi tramite qualsiasi canale.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

![](../assets/do-not-localize/book.png) For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->


## Privacy e consenso

Adobe Campaign è un potente strumento per la raccolta e l’elaborazione di un grande volume di dati, inclusi dati personali e sensibili.  Adobe Campaign ti consente di raccogliere dati, incluse informazioni personali e riservate. È pertanto essenziale ricevere e monitorare il consenso dei destinatari.

![](../assets/do-not-localize/book.png) Scopri come gestire la privacy e il consenso in [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it){target=&quot;_blank&quot;}.


**Argomenti correlati** nella documentazione di Campaign Classic v7:

* [Progettazione ed esecuzione di un flusso di lavoro specifico per la campagna](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html){target=&quot;_blank&quot;}

* [Scopri come selezionare il pubblico di una campagna](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html){target=&quot;_blank&quot;}

* [Guida introduttiva ai flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html){target=&quot;_blank&quot;}
