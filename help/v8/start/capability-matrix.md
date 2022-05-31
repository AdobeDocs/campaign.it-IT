---
title: Matrice di funzionalità Campaign Classic v7 e Campaign v8
description: Comprendere le differenze tra Campaign Classic v7 e Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 0c01b0a597e54ae93dd581ccba6f19b2ff13f956
workflow-type: tm+mt
source-wordcount: '550'
ht-degree: 100%

---

# [!DNL Campaign Classic] v7 - Funzionalità [!DNL Campaign] v8{#gs-matrix}

Per chi già utilizza [!DNL Campaign Classic] v7, non vi sono differenze significative nel modo abituale in cui si interagisce con [!DNL Adobe Campaign]. La maggior parte delle modifiche nella versione 8 non sono visibili, tranne che per le piccole modifiche visualizzate nell’interfaccia utente e nei passaggi di configurazione.

Adobe Campaign v8 è disponibile come **Cloud Service gestito**. La nuova offerta combina servizi all’avanguardia con un monitoraggio proattivo e un avviso tempestivo, incentrato su tre aree:

* **Agilità cloud**: automazione per Adobe, con implementazioni cloud ottimizzate e standardizzate per prestazioni più prevedibili, maggiore agilità e produttività autonoma migliorata.
* **Esperienza del servizio**: disponibilità proattiva, capacità e monitoraggio e risposta delle prestazioni per prevenire interruzioni, risolvere gli incidenti più rapidamente e rivedere regolarmente il servizio per un miglioramento continuo.
* **Competenze approfondite su Campaign**: servizio ad alta affinità offerto da team tecnici specializzati della clientela per soddisfare le esigenze funzionali, tecniche o di recapito dei messaggi, ridurre i rischi di distribuzione e migliorare la gestione dei cambiamenti.

In qualità di utente di [!DNL Campaign Classic], tieni presente che la maggior parte delle funzioni di [!DNL Campaign Classic] v7 sono disponibili anche in [!DNL Campaign] v8, ad eccezione di poche elencate in [questa sezione](#gs-removed). Altre funzioni saranno disponibili nelle prossime versioni. [Per ulteriori informazioni, consulta questa sezione](#gs-unavailable-features).

>[!NOTE]
>
> Campaign v8 si basa su un’architettura ibrida. Se stai eseguendo la transizione da Campaign Classic v7, tieni presente che tutte le consegne passano attraverso il server di mid-sourcing . [Ulteriori informazioni](../architecture/architecture.md)
>
> Di conseguenza, il routing interno è **impossibile** in Campaign v8 e l’account esterno è stato disabilitato di conseguenza.


## [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 funziona con [!DNL Snowflake]. Sono disponibili due modelli di distribuzione.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull’architettura di [!DNL Campaign] v8 sono disponibili in [questa pagina](../architecture/architecture.md).


## Utilizza il tuo Adobe ID per connetterti a Campaign{#adobe-id}

Gli utenti di Campaign si connettono tramite il proprio Adobe ID. Lo stesso Adobe ID viene utilizzato per mantenere tutti i piani e i prodotti di Adobe associati a un singolo account, per tutte le soluzioni di Adobe Experience Cloud.

![](../assets/do-not-localize/glass.png) Scopri come connetterti a [!DNL Campaign] in [questa pagina](connect.md).

## Analizzare i dati con i cubi{#adobe-reporting}

Utilizza il modulo Marketing Analytics per analizzare e misurare i dati, calcolare le statistiche, semplificare e ottimizzare la creazione e il calcolo dei rapporti. Inoltre, crea rapporti e genera popolazioni target: una volta identificati, vengono memorizzati in elenchi che possono essere utilizzati in Adobe Campaign (targeting, segmentazione, ecc.).

I rapporti dei dati cubo di Adobe Campaign sono ottimizzati e offrono migliori funzioni di scalabilità rispetto a Campaign Classic v7. Le precedenti limitazioni sui dati cubo non si applicano in Campaign v8.

## Modificare l’origine dati {#change-data-source}

Campaign v8 offre un’ulteriore attività del flusso di lavoro di targeting: **[!UICONTROL Change data source]**.

L’attività **[!UICONTROL Change data source]** consente di modificare l’origine dati di un flusso di lavoro **[!UICONTROL Working table]** per gestire i dati tra diverse origini dati, come FDA, FFDA e database locale.

![](../assets/do-not-localize/glass.png) Per saperne di più sull’attività **[!UICONTROL Change data source]**, visita [questa pagina](../config/workflows.md#change-data-source-activity).

## Funzioni non disponibili{#gs-unavailable-features}

Tieni presente che alcune funzionalità non sono ancora disponibili in questa versione di Campaign, ad esempio:

* Gestione delle risorse marketing
* Modelli di distribuzione on-premise/ibrida

>[!CAUTION]
>
>* Per il momento, Campaign v8 è disponibile **solo** come Cloud Service gestito e non può essere implementato in ambienti locali o ibridi.
>
>* La migrazione da un ambiente esistente di Campaign Classic v7 non è ancora disponibile.
>
>* Se hai dubbi sul modello di implementazione o hai altre domande, contatta il tuo Adobe account executive.


## Funzioni non supportate{#gs-removed}

Per allinearsi alla nuova architettura e al modello di implementazione di Campaign v8, alcune funzionalità storiche di Campaign Classic v7 non sono più supportate in Campaign v8, come ad esempio:

* Coupon
* Tracciamento web
* Indagini
* Social marketing
* Connettore ACS (offerta Prime)
* Integrazione con LDAP
* Accesso utente/password

>[!NOTE]
>
>Alcune funzioni non disponibili o non supportate possono risultare ancora visibili nell’interfaccia utente.
