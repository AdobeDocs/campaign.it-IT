---
product: Adobe Campaign
title: Limiti noti per Campaign v8
description: Limitazioni note
feature: Panoramica
role: Data Engineer
level: Beginner
hidefromtoc: true
source-git-commit: 08c1f2fbe79845fe54670e25ac4a63ab65517513
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 3%

---

# Limitazioni note

Le limitazioni note identificano funzionalità, architettura o processi non supportati da questa versione del prodotto o che non interagiscono correttamente con esso. Esamina attentamente queste limitazioni.

Per Adobe Campaign v8 esistono le seguenti limitazioni:

* Adobe Campaign v8 non è disponibile per le distribuzioni on-premise/ibride; viene rilasciato solo come Cloud Service gestito da Adobe.
* I clienti esistenti non possono eseguire la migrazione da un ambiente Adobe Campaign esistente ad Adobe Campaign v8
* Nessuna replica bidirezionale dei dati: la replica viene eseguita solo dal database locale di Campaign al database Cloud
* Le funzionalità elencate [in questa sezione](capability-matrix.md#gs-unavailable-features) non sono disponibili nella build corrente di Campaign v8
* Alcune funzioni non disponibili o rimosse sono ancora visibili nell’interfaccia utente di .
* I meccanismi di abbonamento (opt-in) e di annullamento dell’abbonamento (opt-out) e la registrazione mobile sono processi asincroni. Le richieste vengono elaborate ogni ora tramite uno specifico flusso di lavoro tecnico. [Ulteriori informazioni](../config/replication.md#tech-wf)
* I duplicati devono essere gestiti manualmente dagli utenti finali. [Ulteriori informazioni](../dev/keys.md)
* LINE - per confermare + dettagli
* Latenza - per confermare + dettagli
