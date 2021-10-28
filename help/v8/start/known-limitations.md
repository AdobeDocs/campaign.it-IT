---
title: Limitazioni note di Campaign v8
description: Limitazioni note
feature: Overview
role: Data Engineer
level: Beginner
hidefromtoc: true
exl-id: 50c254ba-cc33-49b2-b7d5-12aa69883c07
source-git-commit: e41816003958c3373e92d5ea82240fd7ceda5857
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 87%

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
* Il modulo di ottimizzazione di Adobe Campaign Campaign non tiene conto delle consegne pianificate nelle regole di tipologia della pressione. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/campaign-optimization/pressure-rules.html?lang=en#setting-the-period).