---
title: Utilizzare le mappature target
description: Scopri come utilizzare e creare mappature di destinazione
feature: Audiences, Profiles
role: User, Developer
level: Beginner, Intermediate
exl-id: 5256fc15-1878-4064-9c75-7876a3826b83
source-git-commit: db27abf860b0744a4120166c68e2cc2ae8a3d172
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 4%

---

# Utilizzare le mappature target{#gs-target-mappings}

Per impostazione predefinita, i modelli di consegna e-mail e SMS sono destinati a **[!UICONTROL Recipients]**. La loro mappatura target utilizza quindi i campi del **nms:destinatario** tabella.

Per le notifiche push, la mappatura target predefinita è **Applicazioni in abbonamento (nms:appSubscriptionRcp)**, che è collegato alla tabella dei destinatari.

Puoi utilizzare altre mappature di destinazione per le consegne o crearne una nuova.

## Mappature di destinazione incorporate {#ootb-mappings}

Adobe Campaign è dotato delle seguenti mappature di destinazione integrate:

| Nome | Utilizza per | Schema |
|---|---|---|
| Destinatari | Consegna ai destinatari (tabella dei destinatari incorporata) | nms:destinatario |
| Visitatori | Consegna ai visitatori i cui profili sono stati raccolti tramite riferimento (marketing virale) per es. | mns:visitatore |
| Abbonamenti | Consegna ai destinatari abbonati a un servizio di informazioni, ad esempio una newsletter | nms:sottoscrizione |
| Abbonamenti visitatore | Consegna ai visitatori abbonati a un servizio di informazioni | nms:visitorSub |
| Operatori | Consegna agli operatori Adobe Campaign | nms:operatore |
| File esterno | Consegna tramite un file contenente tutte le informazioni necessarie per la consegna | Nessuno schema collegato, nessuna destinazione immessa |

## Creare una mappatura di destinazione {#new-mapping}

Puoi anche creare una mappatura di destinazione. Potrebbe essere necessario aggiungere una mappatura di destinazione personalizzata, ad esempio, se:

* si utilizza una tabella dei destinatari personalizzata,
* puoi configurare una dimensione di filtro diversa dalla dimensione di targeting incorporata nella schermata mappatura target.

Ulteriori informazioni sulle tabelle dei destinatari personalizzate in [questa pagina](../dev/custom-recipient.md).

la procedura guidata per la creazione di Adobe Campaign target mapping consente di creare tutti gli schemi necessari per utilizzare la mappatura di destinazione personalizzata.

1. Sfoglia per **[!UICONTROL Administration]** `>` **[!UICONTROL Campaign Management]** `>` **[!UICONTROL Target mappings]** da Adobe Campaign explorer.

1. Crea una nuova mappatura di destinazione e seleziona lo schema personalizzato come dimensione di targeting.

   ![](assets/new-target-mapping.png)


1. Indica i campi in cui sono memorizzate le informazioni del profilo: cognome, nome, e-mail, indirizzo, ecc.

   ![](assets/wf_new_mapping_define_join.png)

1. Specifica i parametri per l’archiviazione delle informazioni, compreso il suffisso degli schemi di estensione affinché siano facilmente identificabili.

   ![](assets/wf_new_mapping_define_names.png)

   Puoi scegliere se memorizzare le esclusioni (**excludelog**), con messaggi (**broadlog**) o in una tabella separata.

   Puoi anche scegliere se gestire il tracciamento per questa mappatura di consegna (**trackinglog**).

1. Quindi seleziona le estensioni da prendere in considerazione. Il tipo di estensione dipende dalle impostazioni e dai componenti aggiuntivi di Campaign.

   ![](assets/wf_new_mapping_define_extensions.png)

   Fai clic su **[!UICONTROL Save]** pulsante per avviare la creazione della mappatura di consegna: tutte le tabelle collegate vengono create automaticamente in base ai parametri selezionati.
