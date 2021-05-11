---
solution: Campaign
product: Adobe Campaign
title: Introduzione ai tipi di pubblico
description: Introduzione ai tipi di pubblico
feature: Pubblici
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
translation-type: tm+mt
source-git-commit: 9bc94c213d65b828444888f553722e42fc029165
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 26%

---

# Introduzione ai tipi di pubblico{#gs-ac-audiences}

I profili possono essere raggruppati in elenchi o raccolti eseguendo una query sul database.

## Utilizzare i profili{#gs-ac-profiles}

I profili sono centralizzati nel database cloud. Esistono molti possibili meccanismi per l’acquisizione di profili e la creazione di questo database: raccolta on-line tramite moduli web, importazione manuale o automatica di file di testo, replica con database aziendali o altri sistemi di informazioni. Con Adobe Campaign, puoi incorporare la cronologia di marketing, le informazioni di acquisto, le preferenze, i dati CRM ed eventuali dati PI rilevanti in una vista consolidata per analizzare e intraprendere azioni.

&quot;**Profilo**&quot; significa un record di informazioni che rappresenta un cliente, un potenziale cliente, un abbonato a una newsletter, ecc.
Un record nella tabella **nmsRecipient** o in una tabella esterna contiene un ID cookie, un ID cliente, un identificatore mobile o altre informazioni pertinenti a un particolare canale. Ulteriori informazioni sui profili incorporati e sulle tabelle dei destinatari in [questa sezione](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign, i destinatari sono i profili predefiniti oggetto di targeting per l’invio di consegne (e-mail, SMS, ecc.). I dati dei destinatari memorizzati nel database ti consentono di filtrare il target che riceverà una determinata consegna e di aggiungere dati di personalizzazione nel contenuto della consegna. Nel database sono presenti altri tipi di profili. Essi sono progettati per diversi utilizzi. Ad esempio, i profili di seed vengono creati per testare le consegne prima che vengano inviate al target finale.

:arrow_forward: [Comprendere cos&#39;è un profilo in video](https://video.tv.adobe.com/v/35611?quality=12)

:arrow_Upper_right: Scopri come gestire i profili in [questa guida](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html/?target=_blank).

## Privacy e consenso

Adobe Campaign è uno strumento utile per la raccolta e l’elaborazione di grandi quantità di dati, compresi informazioni personali e dati riservati.  Adobe Campaign ti consente di raccogliere dati, incluse informazioni personali e riservate. È pertanto essenziale ricevere e monitorare il consenso dei destinatari.

:arrow_Upper_right: Scopri come gestire la privacy e il consenso in [questa guida](https://experienceleague.corp.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html).


## Creare elenchi

Un elenco è un set statico di profili che possono essere oggetto di targeting nelle azioni di consegna o aggiornati durante le operazioni di importazione o l’esecuzione di un flusso di lavoro. Ad esempio, una popolazione estratta dal database tramite una query può fornire un elenco.

:arrow_Upper_right: Scopri come creare e gestire gli elenchi in [questa sezione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html).

## Eseguire una query sul database

Utilizza l’attività **Query** in un flusso di lavoro per eseguire query sul database, segmentare i dati e creare tipi di pubblico complessi.

:arrow_Upper_right: Ulteriori informazioni sulle query Campaign in [questa guida](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html).

:arrow_Upper_right: Tutte le attività di targeting sono elencate in [questa pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)

## Creare un pubblico in un flusso di lavoro

Il targeting può essere creato tramite una combinazione di query in una sequenza grafica in un flusso di lavoro. Puoi creare un pubblico di destinazione in base alle tue esigenze. Per visualizzare l’editor del flusso di lavoro, fai clic sulla scheda **[!UICONTROL Targeting and workflows]** nel dashboard della campagna.

:arrow_Upper_right: Scopri come creare un pubblico in un flusso di lavoro della campagna in [questa pagina]https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)


## Profili attivi{#active-profiles}

In base al contratto, a ciascuna istanza di Campaign viene fornito un numero specifico di profili attivi conteggiati a scopo di fatturazione. Per informazioni sul numero di profili attivi acquistati, fai riferimento al contratto più recente.

&quot;Profilo&quot;: un registro di informazioni (ad esempio: un record nella [tabella Destinatario](../dev/datamodel.md) o una tabella esterna contenente un ID cookie, un ID cliente, un identificatore mobile o altre informazioni pertinenti a un particolare canale) che rappresenta un cliente finale, potenziale o lead. I profili sono considerati attivi se sono stati targetizzati o se sono stati comunicati negli ultimi 12 mesi tramite qualsiasi canale.

Puoi monitorare il numero di profili attivi utilizzati sulle istanze direttamente dal Pannello di controllo Campaign Campaign.

:arrow_Upper_right: Per ulteriori informazioni, consulta la [documentazione del Pannello di controllo Campaign](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).


**Argomenti correlati**

:arrow_Upper_right: [Progettare ed eseguire un flusso di lavoro specifico per la campagna](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

:arrow_Upper_right: [Scopri come selezionare il pubblico di una campagna](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

:arrow_Upper_right: [Introduzione ai flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
