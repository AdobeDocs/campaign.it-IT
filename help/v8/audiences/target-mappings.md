---
title: Utilizzare le mappature target
description: Scopri come utilizzare e creare mappature di destinazione
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
exl-id: 5256fc15-1878-4064-9c75-7876a3826b83
TQID: https://experienceleague.adobe.com/ArJJi775HkzlpPOu-SoKg8UTcYTperTC1ySmXrHHpJg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 376
ht-degree: 27%

---

# Utilizzare le mappature target{#gs-target-mappings}

Per impostazione predefinita, i modelli di consegna e-mail e SMS sono destinati a **[!UICONTROL Recipients]**. La mappatura di destinazione utilizza pertanto i campi della tabella **nms:recipient**.

Per le notifiche push, il mapping di destinazione predefinito è **Applicazioni sottoscrittore (nms:appSubscriptionRcp)**, che è collegato alla tabella dei destinatari.

Puoi utilizzare altre mappature di destinazione per le consegne o crearne una nuova.

## Mappature di destinazione incorporate {#ootb-mappings}

Adobe Campaign è dotato delle seguenti mappature di destinazione integrate:

| Nome | Utilizza per | Schema |
|---|---|---|
| Destinatari | Consegnare ai destinatari (tabella dei destinatari incorporata) | nms:recipient |
| Visitatori | Consegnare ai visitatori i cui profili sono stati raccolti tramite riferimento (marketing virale) per es. | mns:visitor |
| Abbonamenti | Consegnare ai destinatari abbonati o iscritti a un servizio informativo, ad esempio una newsletter | nms:subscription |
| Abbonamenti visitatore | Consegnare ai visitatori abbonati o iscritti a un servizio informativo | nms:visitorSub |
| Operatori | Consegnare agli operatori Adobe Campaign | nms:operator |
| File esterno | Consegnare tramite un file contenente tutte le informazioni necessarie per la consegna | Nessuno schema collegato, nessuna destinazione immessa |
| Applicazioni in abbonamento | Consegnare ai destinatari abbonati o iscritti a un’applicazione | nms:appSubscriptionRcp |


## Creare una mappatura target {#new-mapping}

Puoi anche creare una mappatura di destinazione. Potrebbe essere necessario aggiungere una mappatura di destinazione personalizzata, ad esempio, se:

* si utilizza una tabella dei destinatari personalizzata,
* puoi configurare una dimensione di filtro diversa dalla dimensione di targeting incorporata nella schermata mappatura target.

Ulteriori informazioni sulle tabelle dei destinatari personalizzate in [questa pagina](../dev/custom-recipient.md).

la procedura guidata per la creazione di Adobe Campaign target mapping consente di creare tutti gli schemi necessari per utilizzare la mappatura di destinazione personalizzata.

1. Passare a **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** da Adobe Campaign Explorer.

1. Crea una nuova mappatura di destinazione e seleziona lo schema personalizzato come dimensione di targeting.

   ![](assets/new-target-mapping.png)


1. Indica i campi in cui sono memorizzate le informazioni del profilo: cognome, nome, e-mail, indirizzo, ecc.

   ![](assets/wf_new_mapping_define_join.png)

1. Specifica i parametri per l’archiviazione delle informazioni, compreso il suffisso degli schemi di estensione affinché siano facilmente identificabili.

   ![](assets/wf_new_mapping_define_names.png)

   Puoi scegliere se memorizzare le esclusioni (**excludelog**), con i messaggi (**broadlog**) o in una tabella separata.

   Puoi anche scegliere se gestire il tracciamento per questa mappatura di consegna (**trackinglog**).

1. Quindi seleziona le estensioni da prendere in considerazione. Il tipo di estensione dipende dalle impostazioni e dai componenti aggiuntivi di Campaign.

   ![](assets/wf_new_mapping_define_extensions.png)

   Fai clic sul pulsante **[!UICONTROL Save]** per avviare la creazione della mappatura di consegna: tutte le tabelle collegate vengono create automaticamente in base ai parametri selezionati.
