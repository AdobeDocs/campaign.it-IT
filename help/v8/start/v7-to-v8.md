---
title: Transizione da Campaign Classic v7 a Campaign v8
description: Scopri le differenze tra Campaign Classic v7 e Campaign v8.
feature: Overview
role: User
level: Beginner
exl-id: 00ba1c43-9558-4adb-83a1-6597c2bbca62
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '714'
ht-degree: 76%

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

Adobe Campaign Managed Cloud Services fornisce una piattaforma Managed Cloud Services per la progettazione di esperienze cliente cross-channel oltre a un ambiente per l’orchestrazione visiva delle campagne, la gestione delle interazioni in tempo reale e l’esecuzione su più canali. Ulteriori informazioni su Campaign Managed Cloud Services sono disponibili nella [pagina di descrizione del prodotto](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

La nuova offerta combina servizi all’avanguardia con un monitoraggio proattivo e un avviso tempestivo, incentrato su tre aree:

* **Agilità cloud**: automazione per Adobe, con implementazioni cloud ottimizzate e standardizzate per prestazioni più prevedibili, maggiore agilità e produttività autonoma migliorata.
* **Esperienza del servizio**: disponibilità proattiva, capacità e monitoraggio e risposta delle prestazioni per prevenire interruzioni, risolvere gli incidenti più rapidamente e rivedere regolarmente il servizio per un miglioramento continuo.
* **Competenze approfondite su Campaign**: servizio ad alta affinità offerto da team tecnici specializzati della clientela per soddisfare le esigenze funzionali, tecniche o di recapito dei messaggi, ridurre i rischi di distribuzione e migliorare la gestione dei cambiamenti.

In qualità di utente di [!DNL Campaign Classic], tieni presente che la maggior parte delle funzioni di [!DNL Campaign Classic] v7 sono disponibili anche in [!DNL Campaign] v8, ad eccezione di alcune che sono elencate in [questa sezione](#gs-removed).

>La nuova architettura cloud consente a Campaign di semplificare i processi, ridurre i costi, gestire i rischi e migliorare la sicurezza dei dati. Il tuo ambiente Campaign v8 è dotato di un Virtual Private Cloud (VPC) dedicato e preconfigurato.


## Architettura ibrida {#hybrid-archi}

Campaign v8 si basa su una **architettura ibrida**. Se stai passando da Campaign Classic v7, tieni presente che tutte le consegne passano attraverso il server di mid-sourcing.

Di conseguenza:

* Il routing interno è **impossibile** in Campaign v8 e l&#39;account esterno è stato disabilitato di conseguenza,
* Lo stato delle consegne non viene aggiornato all’istante: viene eseguito un processo tecnico sull’istanza Marketing che aggiornerà gli stati di consegna in modo tempestivo.


Ulteriori informazioni sull&#39;invio di bozze dei messaggi transazionali durante la transizione da v7 in [questa pagina](../send/transactional-template.md#transition-from-v7).


## [!DNL Campaign] e [!DNL Snowflake] {#ac-gs-snowflake}

Nella distribuzione [Enterprise (FFDA)](../architecture/enterprise-deployment.md), [!DNL Adobe Campaign] v8 funziona con due database: un database [!DNL Campaign] locale per la messaggistica in tempo reale, le query unitarie dell&#39;interfaccia utente e le operazioni di scrittura tramite API e un database [!DNL Snowflake] cloud per l&#39;esecuzione della campagna, le query batch e l&#39;esecuzione del flusso di lavoro.

Campaign v8 Enterprise introduce il concetto di **Full Federated Data Access** (FFDA): adesso tutti i dati sono remoti, nel database cloud. Con questa nuova architettura, l’implementazione di Campaign v8 Enterprise (FFDA) semplifica la gestione dei dati, in quanto nel database cloud non è richiesto alcun indice. È sufficiente creare le tabelle, copiare i dati e iniziare. La tecnologia del database cloud non richiede una manutenzione specifica per garantire le prestazioni del servizio.

Ulteriori informazioni sull&#39;architettura di [!DNL Campaign] v8 in [questa pagina](../architecture/architecture.md).


## Utilizza il tuo Adobe ID per connetterti a Campaign{#adobe-id}

Gli utenti di Campaign si connettono unicamente tramite il proprio Adobe ID. Lo stesso Adobe ID viene utilizzato per mantenere tutti i piani e i prodotti di Adobe associati a un singolo account, per tutte le soluzioni di Adobe Experience Cloud.

Scopri come connetterti a [!DNL Campaign] in [questa pagina](connect.md).

## Analizzare i dati con i cubi{#adobe-reporting}

Utilizza il modulo Marketing Analytics per analizzare e misurare i dati, calcolare le statistiche, semplificare e ottimizzare la creazione e il calcolo dei rapporti. Inoltre, crea rapporti e genera popolazioni target: una volta identificati, vengono memorizzati in elenchi che possono essere utilizzati in Adobe Campaign (targeting, segmentazione, ecc.).

Con Adobe Campaign v8, i rapporti cubo sono ottimizzati e offrono migliori funzioni di scalabilità rispetto a Campaign Classic v7. In questo specifico modello di implementazione, le limitazioni precedenti sui cubi non sono applicabili a Campaign v8. Per ulteriori informazioni sui cubi, consulta [questa sezione](../../v8/reporting/gs-cubes.md).

## Funzioni non disponibili{#gs-unavailable-features}

Tieni presente che alcune funzionalità non sono disponibili nel contesto di una [implementazione Enterprise (FFDA)](../architecture/enterprise-deployment.md) di Campaign, ad esempio:

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
