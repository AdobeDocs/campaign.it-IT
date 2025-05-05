---
title: Utilizzare i tipi di pubblico in Campaign
description: Utilizzare i tipi di pubblico in Campaign
feature: Audiences
role: User
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: ad96c126836981f861c246eafa2ec7d2c0e179dc
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 17%

---

# Utilizzare i tipi di pubblico in Campaign{#gs-ac-audiences}

I profili sono contatti memorizzati nel database di Campaign.

In Adobe Campaign, **destinatari** sono i profili predefiniti target per l&#39;invio di consegne (e-mail, SMS, ecc.). I dati dei destinatari memorizzati nel database consentono di filtrare il target che riceverà una determinata consegna e di aggiungere dati di personalizzazione al contenuto della consegna. Nel database sono presenti altri tipi di profili. Essi sono progettati per diversi utilizzi. Ad esempio, i profili di seed vengono creati per testare le consegne prima che vengano inviate al target finale.

Scopri come importare, aggiornare e gestire profili e tipi di pubblico [in questa sezione](../audiences/gs-audiences.md).

## Creare elenchi{#create-lists}

Un elenco è un set statico di contatti che possono essere targetizzati nelle azioni di consegna o aggiornati durante un’importazione o un’altra azione del flusso di lavoro. Ad esempio, una popolazione estratta dal database tramite una query può essere memorizzata come elenco.

Scopri come creare e gestire gli elenchi in [questa pagina](../audiences/create-audiences.md).

## Filtrare il database{#filter-the-database}

La configurazione del filtro consente di selezionare i dati da un elenco **[!UICONTROL dynamically]**: quando i dati vengono modificati, i dati filtrati vengono aggiornati. Puoi creare filtri personalizzati o utilizzare i filtri incorporati per definire un pubblico target.

Scopri come creare e gestire i filtri in [questa pagina](../audiences/create-filters.md).

## Creare un pubblico in un flusso di lavoro

Il targeting può essere creato tramite una combinazione di query in una sequenza grafica in un flusso di lavoro. Puoi creare tipi di pubblico mirati in base alle tue esigenze. Per visualizzare l&#39;editor del workflow, fare clic sulla scheda **[!UICONTROL Targeting and workflows]** nel dashboard della campagna.

Scopri come creare un pubblico in un flusso di lavoro della campagna in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/campaign-orchestration/marketing-campaign-target.html?lang=it){target="_blank"}.


## Profili attivi {#active-profiles}

Un profilo attivo è un profilo con cui il cliente ha tentato di comunicare negli ultimi 12 mesi tramite qualsiasi canale.

In base al contratto, a ciascuna istanza di Campaign viene fornito un numero specifico di profili attivi conteggiati a scopo di fatturazione. Fai riferimento al contratto più recente per informazioni sul numero di profili attivi acquistati. Ulteriori informazioni sono disponibili nella [descrizione del prodotto Adobe Campaign](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

Puoi monitorare il numero di profili attivi nell’istanza direttamente dal Pannello di controllo Campaign Campaign. Per ulteriori informazioni, consulta la [documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html?lang=it){target="_blank"}.


Si applicano le seguenti protezioni e limitazioni:

* Un profilo che è stato oggetto di targeting per diverse consegne viene conteggiato una sola volta.
* I profili target nel contesto di Social marketing al Twitter X non vengono considerati come profili attivi.
* Il conteggio si basa sulla chiave primaria del destinatario. Di conseguenza, se un profilo è presente in due diverse tabelle dei destinatari, può essere conteggiato due volte come profilo attivo.

## Privacy e consenso{#privacy-and-consent}

Adobe Campaign è uno strumento utile per la raccolta e l’elaborazione di grandi volumi di dati, compresi informazioni personali e dati sensibili.  Adobe Campaign ti consente di raccogliere dati, incluse informazioni personali e riservate. È pertanto essenziale ricevere e monitorare il consenso dei destinatari.

Scopri come gestire la privacy e il consenso nella [documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html?lang=it){target="_blank"}.

