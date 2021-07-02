---
product: Adobe Campaign
title: Limitazioni note di Campaign v8
description: Limitazioni note
feature: Panoramica
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: cf00895f988514fc029d0060d7404bdef0c8b30e
workflow-type: ht
source-wordcount: '177'
ht-degree: 100%

---

# Limitazioni note

Le limitazioni note descrivono le funzionalità, l’architettura o i processi non supportati dall’attuale versione del prodotto o che non vi interagiscono correttamente. Esamina attentamente queste limitazioni.

Adobe Campaign v8 presenta le seguenti limitazioni:

* Adobe Campaign v8 non è disponibile per le implementazioni locali o ibride; questa versione è rilasciata solo come Cloud Service gestito da Adobe.
* I clienti attuali non possono eseguire la migrazione da un ambiente Adobe Campaign esistente ad Adobe Campaign v8.
* Nessuna replica bidirezionale dei dati: la replica viene eseguita solo dal database locale di Campaign al database Cloud.
* Le funzionalità elencate in [questa sezione](capability-matrix.md#gs-unavailable-features) non sono disponibili nella build corrente di Campaign v8.
* Alcune funzioni non disponibili o rimosse risultano ancora visibili nell’interfaccia utente.
* I meccanismi di abbonamento (opt-in), di annullamento dell’abbonamento (opt-out) e la registrazione mobile sono processi asincroni. Le richieste vengono elaborate ogni ora, mediante un flusso di lavoro tecnico specifico. [Ulteriori informazioni](../config/replication.md#tech-wf)
* I duplicati devono essere gestiti manualmente dagli utenti finali. [Ulteriori informazioni](../dev/keys.md)
* Adobe Campaign v8 non supporta la velocità di elaborazione estesa nelle applicazioni API e web. In caso di esigenze specifiche, contatta Adobe per ottenere assistenza.


