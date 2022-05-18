---
title: Matrice di funzionalità Campaign Classic v7 e Campaign v8
description: Comprendere le differenze tra Campaign Classic v7 e Campaign v8
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 40%

---

# [!DNL Campaign Classic] v7 - [!DNL Campaign] v8: cosa cambia{#gs-matrix}

Come ex [!DNL Campaign Classic] Utente v7, non ci si dovrebbe aspettare grandi interruzioni nel modo con cui si interagisce di solito con [!DNL Adobe Campaign]. La maggior parte delle modifiche nella versione 8 non sono visibili, tranne che per le piccole modifiche visualizzate nell’interfaccia utente e nei passaggi di configurazione.

Adobe Campaign v8 è disponibile come **Cloud Service gestito**. La nuova offerta combina servizi all&#39;avanguardia con un monitoraggio proattivo e un avviso tempestivo, incentrato su tre aree:

* **Agilità cloud** automazione per Adobe, con implementazioni cloud ottimizzate e standardizzate per prestazioni più prevedibili, maggiore agilità e produttività self-service migliorata.
* **Esperienza del servizio** disponibilità proattiva, capacità e monitoraggio e risposta delle prestazioni per prevenire interruzioni, risolvere gli incidenti più rapidamente e rivedere regolarmente il servizio per un miglioramento continuo.
* **Competenze approfondite su Campaign** servizio ad alta affinità offerto da team tecnici specializzati della clientela per soddisfare le esigenze funzionali, tecniche o di recapito dei messaggi, ridurre i rischi di distribuzione e migliorare la gestione dei cambiamenti.

Come ex [!DNL Campaign Classic] utente, tieni presente che la maggior parte [!DNL Campaign Classic] Le funzionalità v7 sono disponibili con [!DNL Campaign] v8, ad eccezione di un piccolo insieme di essi, elencati in [questa sezione](#gs-removed). Altre funzioni saranno disponibili nelle prossime versioni. [Per ulteriori informazioni, consulta questa sezione](#gs-unavailable-features).

>[!NOTE]
>
> Campaign v8 si basa su un’architettura ibrida. Se stai eseguendo la transizione da Campaign Classic v7, tieni presente che tutte le consegne passano attraverso il server di mid-sourcing . [Ulteriori informazioni](../architecture/architecture.md)
>
> Di conseguenza, il routing interno è **impossibile** in Campaign v8 e l’account esterno è stato disabilitato di conseguenza.


## [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 funziona con [!DNL Snowflake]. Sono disponibili due modelli di distribuzione.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull’architettura di [!DNL Campaign] v8 sono disponibili in [questa pagina](../architecture/architecture.md).


## Utilizza il tuo Adobe ID per connetterti a Campaign{#adobe-id}

Gli utenti di Campaign si connettono tramite il proprio Adobe ID. Lo stesso Adobe ID viene utilizzato per mantenere tutti i piani e i prodotti di Adobe associati a un singolo account, per tutte le soluzioni Adobe Experience Cloud.

![](../assets/do-not-localize/glass.png) Scopri come connetterti a [!DNL Campaign] in [questa pagina](connect.md).

## Analizzare i dati con i cubi{#adobe-reporting}

Utilizza il modulo Marketing Analytics per analizzare e misurare i dati, calcolare le statistiche, semplificare e ottimizzare la creazione e il calcolo dei rapporti. Inoltre, crea report e genera popolazioni target: una volta identificati, vengono memorizzati in elenchi che possono essere utilizzati in Adobe Campaign (targeting, segmentazione, ecc.).

I rapporti cubo di Adobe Campaign sono ottimizzati e forniscono funzionalità di scalabilità migliore rispetto a Campaign Classic v7. Le precedenti limitazioni sui cubi non si applicano in Campaign v8.

## Modificare l’origine dati {#change-data-source}

Campaign v8 offre un’ulteriore attività del flusso di lavoro di targeting: **[!UICONTROL Change data source]**.

L’attività **[!UICONTROL Change data source]** consente di modificare l’origine dati di un flusso di lavoro **[!UICONTROL Working table]** per gestire i dati tra diverse origini dati, come FDA, FFDA e database locale.

![](../assets/do-not-localize/glass.png) Per saperne di più sull’attività **[!UICONTROL Change data source]**, visita [questa pagina](../config/workflows.md#change-data-source-activity).

## Funzioni non disponibili{#gs-unavailable-features}

Tieni presente che alcune funzionalità non sono ancora disponibili in questa versione di Campaign, ad esempio:

* Gestione delle risorse marketing
* Marketing distribuito
* Gestione della risposta
* Modelli di distribuzione on-premise/ibrida

>[!CAUTION]
>
>* Per il momento, Campaign v8 è disponibile **solo** come Cloud Service gestito e non può essere implementato in ambienti locali o ibridi.
>
>* La migrazione da un ambiente esistente di Campaign Classic v7 non è ancora disponibile.
>
>* Se non sei sicuro del tuo modello di implementazione o hai domande, contatta il tuo responsabile dell&#39;account Adobe.


## Funzioni non supportate{#gs-removed}

Per allinearsi alla nuova architettura e al modello di implementazione di Campaign v8, alcune funzionalità storiche di Campaign Classic v7 non sono più supportate in Campaign v8, come ad esempio:

* Coupon
* Tracciamento web
* Indagini
* Social marketing con Facebook
* Connettore ACS (offerta Prime)
* Integrazione con LDAP
* Accesso utente/password

>[!NOTE]
>
>Alcune funzioni non disponibili o non supportate potrebbero ancora essere visibili nell’interfaccia utente.
