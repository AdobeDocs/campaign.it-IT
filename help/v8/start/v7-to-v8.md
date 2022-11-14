---
title: Transizione da Campaign Classic v7 a Campaign v8
description: Comprendere le differenze tra Campaign Classic v7 e Campaign v8
feature: Overview
role: Admin, Developer, User
level: Beginner, Intermediate, Experienced
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: c267bf2db7dfd524bf2b56c9ae48b42da37c0376
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 96%

---

# Transizione da [!DNL Campaign Classic] v7 a [!DNL Campaign] v8{#gs-matrix}

Per chi già utilizza [!DNL Campaign Classic] v7, non vi sono differenze significative nel modo abituale in cui si interagisce con [!DNL Adobe Campaign]. La maggior parte delle modifiche nella versione 8 non sono visibili, tranne che per le piccole modifiche visualizzate nell’interfaccia utente e nei passaggi di configurazione.

>[!AVAILABILITY]
>
>* Per il momento, Campaign v8 è disponibile **solo** come Managed Cloud Service e non può essere implementato in ambienti on-premise o ibridi. [Ulteriori informazioni](#cloud-services)
>
>* La migrazione automatizzata da un ambiente esistente di Campaign Classic v7 non è ancora disponibile.



## Managed Cloud Services{#cloud-services}

Adobe Campaign v8 è disponibile come **Managed Cloud Service**.

Adobe Campaign Managed Cloud Services fornisce una piattaforma Managed Cloud Services per la progettazione di esperienze cliente cross-channel oltre a un ambiente per l’orchestrazione visiva delle campagne, la gestione delle interazioni in tempo reale e l’esecuzione su più canali. Ulteriori informazioni su Campaign Managed Cloud Services sono disponibili nella [pagina di descrizione del prodotto](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target=&quot;_blank&quot;}.

La nuova offerta combina servizi all’avanguardia con un monitoraggio proattivo e un avviso tempestivo, incentrato su tre aree:

* **Agilità cloud**: automazione per Adobe, con implementazioni cloud ottimizzate e standardizzate per prestazioni più prevedibili, maggiore agilità e produttività autonoma migliorata.
* **Esperienza del servizio**: disponibilità proattiva, capacità e monitoraggio e risposta delle prestazioni per prevenire interruzioni, risolvere gli incidenti più rapidamente e rivedere regolarmente il servizio per un miglioramento continuo.
* **Competenze approfondite su Campaign**: servizio ad alta affinità offerto da team tecnici specializzati della clientela per soddisfare le esigenze funzionali, tecniche o di recapito dei messaggi, ridurre i rischi di distribuzione e migliorare la gestione dei cambiamenti.

In qualità di utente di [!DNL Campaign Classic], tieni presente che la maggior parte delle funzioni di [!DNL Campaign Classic] v7 sono disponibili anche in [!DNL Campaign] v8, ad eccezione di alcune che sono elencate in [questa sezione](#gs-removed).

>[!NOTE]
>
> Campaign v8 si basa su un’architettura ibrida. Se stai eseguendo la transizione da Campaign Classic v7, tieni presente che tutte le consegne passano attraverso il server di mid-sourcing . [Ulteriori informazioni](../architecture/architecture.md)
>
> Di conseguenza, il routing interno è **impossibile** in Campaign v8 e l’account esterno è stato disabilitato di conseguenza.


## [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

Campaign v8 funziona con [!DNL Snowflake].

Nell’[implementazione Enterprise (FFDA)](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 funziona con due database: un database [!DNL Campaign] locale per la messaggistica in tempo reale, le query unitarie dell’interfaccia utente e le operazioni di scrittura tramite API; e un database cloud [!DNL Snowflake] per l’esecuzione della campagna, le query batch e l’esecuzione dei flussi di lavoro.

Campaign v8 Enterprise introduce il concetto di **Full Federated Data Access** (FFDA): adesso tutti i dati sono remoti, nel database cloud. Con questa nuova architettura, l’implementazione di Campaign v8 Enterprise (FFDA) semplifica la gestione dei dati, in quanto nel database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare. La tecnologia del database cloud non richiede una manutenzione specifica per garantire la qualità del servizio.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sull’architettura di [!DNL Campaign] v8 sono disponibili in [questa pagina](../architecture/architecture.md).


## Utilizza il tuo Adobe ID per connetterti a Campaign{#adobe-id}

Gli utenti di Campaign si connettono unicamente tramite il proprio Adobe ID. Lo stesso Adobe ID viene utilizzato per mantenere tutti i piani e i prodotti di Adobe associati a un singolo account, per tutte le soluzioni di Adobe Experience Cloud.

![](../assets/do-not-localize/glass.png) Scopri come connetterti a [!DNL Campaign] in [questa pagina](connect.md).

## Analizzare i dati con i cubi{#adobe-reporting}

Utilizza il modulo Marketing Analytics per analizzare e misurare i dati, calcolare le statistiche, semplificare e ottimizzare la creazione e il calcolo dei rapporti. Inoltre, crea rapporti e genera popolazioni target: una volta identificati, vengono memorizzati in elenchi che possono essere utilizzati in Adobe Campaign (targeting, segmentazione, ecc.).

Con Adobe Campaign v8, i rapporti cubo sono ottimizzati e offrono migliori funzioni di scalabilità rispetto a Campaign Classic v7. In questo specifico modello di implementazione, le limitazioni precedenti sui cubi non sono applicabili a Campaign v8. Per ulteriori informazioni sui cubi, consulta [questa sezione](../../v8/reporting/gs-cubes.md).

## Funzioni non disponibili{#gs-unavailable-features}

Tieni presente che alcune funzionalità non sono disponibili nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md) di Campaign, ad esempio:

* Gestione delle risorse marketing
* Coupon
* Tracciamento web
* Indagini

## Funzioni non supportate{#gs-removed}

Alcune funzionalità storiche di Campaign Classic v7 non sono più supportate in Campaign v8, ad esempio:

* Social marketing con Facebook
* Connettore ACS (offerta Prime)
* Integrazione con LDAP
* Accesso utente/password
* Modelli di implementazione on-premise/ibrida


>[!NOTE]
>
>Alcune funzioni non disponibili o non supportate possono risultare ancora visibili nell’interfaccia utente.
