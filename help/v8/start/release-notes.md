---
title: Note sulla versione di Campaign v8
description: Ultima versione di Campaign v8
feature: Release Notes
exl-id: 7cf8111d-9f3a-46a4-813a-d4e43a1d1471
source-git-commit: d31368428fc7d5b982bb5fc67d0369bb17ea0b2c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 23%

---

# Versioni più recenti {#latest-release}

In questa pagina sono elencate le nuove funzionalità, i miglioramenti e le correzioni introdotte con le **versioni più recenti** di Campaign v8 (console). Ulteriori informazioni sulle versioni e gli aggiornamenti di Campaign sono disponibili in [questa pagina](upgrades.md). Altre versioni sono elencate nella sezione Versioni precedenti di questa documentazione.

## Versione 8.8.2 {#release-8-8-2}

_9 ottobre 2025_

>[!AVAILABILITY]
>
>Questa versione è in **disponibilità limitata** (LA).

### Nuove funzioni {#features-8-8-2}

Il **nuovo connettore di invio SMS** è ora disponibile per [distribuzioni FFDA di Campaign](../architecture/enterprise-deployment.md). Consulta la [documentazione dettagliata](../send/sms/sms.md).

Questa versione include anche una serie di funzionalità disponibili con l’interfaccia utente web di Campaign:

* [Arricchimento del profilo nei messaggi transazionali](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/transactional-messages/profile-enrichment.html){target="_blank"}
* [Funzionalità multilingue per messaggi transazionali, notifiche push e SMS](https://experienceleague.adobe.com/docs/campaign-web/v8/msg/multilingual.html){target="_blank"}

Consulta le [note sulla versione](https://experienceleague.adobe.com/docs/campaign-web/v8/release-notes/release-notes.html?lang=it){target="_blank"} dell’interfaccia utente di Campaign Web

### Correzioni {#fixes-8-8-2}

<!--
* Fixed an issue which prevented dynamic reporting from being available for transactional messages.
-->
* È stato risolto un problema che poteva causare un errore nel flusso di lavoro di pulizia del database. (NEO-87949)
* È stato risolto un problema in Marketing distribuito a causa del quale i dati di tracciamento non venivano registrati per le consegne di campagne collaborative. (NEO-86836)
<!--
* Issue SMS2.0 with FFDA Continuous Deliveries (NEO-88785)
-->
* È stato risolto un problema che poteva impedire il corretto funzionamento della personalizzazione nei frammenti. (NEO-88161)
* È stato risolto un problema, dopo la migrazione al nuovo connettore ODBC Redshift, che poteva causare un errore dell’attività Split workflow con errori SQL. (NEO-87466)
* È stato risolto un problema che poteva causare conteggi di esclusione non accurati nei flussi di lavoro. (NEO-89207)
* È stato risolto un problema che poteva causare indicatori di clic imprecisi per le notifiche push. (NEO-89503)
* È stato risolto un problema a causa del quale i registri di consegna SMS non venivano aggiornati correttamente, impedendo la creazione di rapporti di stato precisi in Adobe Campaign. (NEO-88479)
* È stato risolto un problema a causa del quale le virgolette francesi non venivano convertite correttamente in virgolette inglesi nel contenuto della consegna. (NEO-89631)
* È stato risolto un problema a causa del quale Real-Time Server restituiva un codice di risposta errato per token IMS non validi. (NEO-87428)
* È stato risolto un problema a causa del quale le statistiche di consegna per E-mail e SMS non venivano ricalcolate completamente, causando indicatori di successo imprecisi. (NEO-88106)
* È stato risolto un problema relativo al nuovo connettore di invio SMS a causa del quale i registri di consegna non assegnavano correttamente lo stato di consegna per un piccolo sottoinsieme di messaggi. (NEO-89581)
* È stato risolto un problema relativo al nuovo connettore di invio SMS a causa del quale le consegne delle metriche di successo non venivano aggiornate correttamente sui server marketing e mid. (NEO-89850)
* È stato risolto un problema di sincronizzazione tra le istanze Real-Time e Marketing che causava registri di tracciamento mancanti e rapporti errati. (NEO-90247)
* È stato risolto un problema di arricchimento del flusso di lavoro che poteva causare errori durante la selezione dei campi tra due collegamenti 1-N consecutivi negli schemi personalizzati. (NEO-87682)

