---
solution: Campaign v8
product: Adobe Campaign
title: Introduzione alle campagne di marketing
description: Introduzione alle campagne di marketing
feature: Tipi di pubblico
role: Data Engineer
level: Beginner
exl-id: b5a6c845-13a7-4746-b856-a08a3cf80b66,c4798c8f-619e-4a60-80d7-29b9e4c61168
source-git-commit: a50a6cc28d9312910668205e528888fae5d0b1aa
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 7%

---

# Guida introduttiva alle campagne di marketing{#gs-ac-campaigns}

Adobe Campaign offre un set di soluzioni che consentono di personalizzare e distribuire campagne su tutti i canali online e offline. Puoi creare, configurare, eseguire e analizzare le campagne di marketing. Tutte le campagne di marketing possono essere gestite da un centro di controllo unificato. Scopri come sfogliare e creare campagne di marketing in questa sezione.

Le campagne includono azioni (consegne), processi (importazione o estrazione di file) e risorse (documenti di marketing, linee di consegna). Vengono utilizzati nelle campagne di marketing. Le campagne fanno parte di un programma e i programmi sono inclusi in un piano di campagna.

## Orchestrazione di campagne cross-channel

 Adobe Campaign ti consente di progettare e orchestrare campagne mirate e personalizzate su più canali: e-mail, direct mail, SMS, notifica push. Un’unica interfaccia ti offre tutte le funzioni necessarie per pianificare, orchestrare, configurare, personalizzare, automatizzare, eseguire e misurare tutte le tue campagne e comunicazioni.

### Concetti di base

Prima di iniziare a implementare le campagne di marketing, devi acquisire familiarità con i seguenti concetti:

* **Campagna** di marketing: una campagna centralizza tutti gli elementi relativi a una campagna di marketing: consegne, regole di targeting, costi, file di esportazione, documenti correlati, ecc. Ogni campagna è associata a un programma.

* **Programma**: un programma consente di definire azioni di marketing per un periodo di calendario: lancio, tela cerata, lealtà, ecc. Ogni programma contiene campagne collegate a un calendario, che fornisce una visualizzazione complessiva.

* **Pianifica**: il piano di marketing può contenere più programmi. È collegato a un periodo di calendario, ha un bilancio assegnato e può anche essere collegato a documenti e obiettivi.

* **Flusso di lavoro** della campagna: un flusso di lavoro della campagna contiene attività per generare la logica della campagna. Utilizza i flussi di lavoro delle campagne per definire i tipi di pubblico e creare consegne per tutti i canali disponibili.

* **Campagne** ricorrenti: le campagne ricorrenti vengono create da un modello specifico che definisce il modello di flusso di lavoro da eseguire e la pianificazione di esecuzione.

* **Campagne** periodiche: una campagna periodica è una campagna creata automaticamente in base alla pianificazione di esecuzione del relativo modello.

## Area di lavoro di una campagna di marketing

Adobe Campaign consente di creare, configurare, eseguire e analizzare tutte le campagne di marketing da un centro di controllo unificato.

:arrow_Upper_right: Scopri come accedere e implementare le campagne di marketing nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/about-marketing-campaigns/accessing-marketing-campaigns.html?lang=en#orchestrating-campaigns)


## Passaggi fondamentali da avviare

I passaggi chiave per creare una campagna di marketing cross-channel sono i seguenti:

1. **Pianificare e progettare programmi e campagne di marketing**

   Definire la gerarchia e la pianificazione, impostare il budget, aggiungere risorse, selezionare operatori.

   :arrow_Upper_right: Scopri come creare un piano di marketing e configurare le campagne nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#creating-plan-and-program-hierarchy)

   Tutte le campagne di marketing si basano su un modello, che memorizza le impostazioni e le funzionalità principali. Viene fornito un modello incorporato per creare una campagna per la quale non è stata definita alcuna configurazione specifica. Puoi creare e configurare i modelli delle campagne e quindi creare campagne a partire da questi modelli.

   :arrow_Upper_right: Scopri come utilizzare i modelli di campagna nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-templates.html?lang=en#orchestrating-campaigns)

   :arrow_Upper_right: Scopri le campagne ricorrenti e come configurarle nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/setting-up-marketing-campaigns.html?lang=en#recurring-and-periodic-campaigns)

1. **Definire i tipi di pubblico**

   Puoi creare il pubblico in un flusso di lavoro o selezionare un gruppo esistente, ad esempio un elenco di destinatari, gli abbonati a una newsletter, i destinatari di una consegna precedente o qualsiasi condizione di filtro.

   :arrow_Upper_right: Scopri come definire il pubblico dei messaggi nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#orchestrating-campaigns)

1. **Creare consegne**

   Seleziona i canali, definisci il contenuto del messaggio e avvia le consegne.

   :arrow_Upper_right: Scopri come creare e avviare le consegne di campagne di marketing nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-deliveries.html?lang=en#creating-deliveries)

   È possibile associare vari documenti a una campagna: report, foto, pagina web, diagramma, ecc.

   :arrow_Upper_right: Ulteriori informazioni sui documenti associati nella documentazione di [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-assets.html?lang=en#adding-documents)

1. **Imposta il processo di approvazione**

   Adobe Campaign consente di impostare processi di approvazione collaborativa per le fasi principali della campagna di marketing. Per ogni campagna puoi approvare il target di consegna, il contenuto e i costi. Gli operatori Adobe Campaign incaricati dell’approvazione possono ricevere una notifica via e-mail e accettare o rifiutare l’approvazione dalla console o tramite una connessione web.

   :arrow_Upper_right: Scopri come impostare e gestire le approvazioni nella documentazione di [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-approval.html?lang=en#orchestrating-campaigns)

