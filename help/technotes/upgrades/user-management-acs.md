---
title: Migrazione degli utenti tecnici alla console Adobe Developer
description: Scopri come migrare la gestione degli accessi utente da Campaign Standard a Campaign V8
feature: Technote
role: Admin
source-git-commit: ccd60b7ff54bb538ae21693eff41a3943f1c6c88
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 2%

---

# Gestione degli accessi utente da Campaign Standard a Campaign V8 {#user-management-acs}

Sia Adobe Campaign Standard che Adobe Campaign V8 consentono agli utenti di definire e gestire le autorizzazioni per diversi utenti/operatori. Queste autorizzazioni sono costituite da diritti specifici che consentono agli utenti di accedere a varie funzioni del prodotto. Tuttavia, i due prodotti utilizzano approcci e implementazioni distinti per la gestione dell’accesso degli utenti.

I seguenti concetti vengono utilizzati in Adobe Campaign Standard e Campaign V8 per ottenere la gestione degli accessi utente:

| Campaign Standard | Campaign V8 |
|---------|----------|
| Utente | Operatore |
| Ruolo | Denominato a destra |
| Gruppo di sicurezza | Gruppo di operatori |
| Unità organizzativa | Autorizzazione cartella |

## Approccio di migrazione dal gruppo di sicurezza al gruppo di operatori

>[!CAUTION]
>
>Le funzionalità di questi ruoli/diritti denominati possono variare nell’implementazione, causando potenzialmente problemi di autorizzazione (ad esempio, elevazione dei privilegi o interruzioni di funzionalità). Consigliamo agli utenti di rivedere queste mappature dopo la transizione per garantire un corretto controllo degli accessi. [Ulteriori informazioni sulle autorizzazioni](../../v8/start/manage-permissions.md)

La tabella seguente illustra l’approccio di migrazione per i gruppi di ruoli utente durante la transizione da Adobe Campaign Standard a Campaign V8. In Campaign Standard, viene utilizzato un **gruppo di sicurezza**, denominato **gruppo di operatori** in Campaign V8, per assegnare un set di ruoli a un utente. Anche se alcuni gruppi di sicurezza/gruppi di operatori sono predefiniti, gli utenti possono creare nuovi gruppi o modificarne di esistenti, se necessario.

| | **Campaign Standard** | **Campagna V8** |
|---------|----------|---------|
| **Terminologia**  | Gruppo di sicurezza | Gruppo di operatori |

Sia in Adobe Campaign Standard che in Campaign V8, **I gruppi di sicurezza** e **I gruppi di operatori** sono mappati ai profili di prodotto in Admin Console. Se desideri assegnare un **gruppo di sicurezza** o un **gruppo di operatori** a un utente, puoi collegare il **profilo di prodotto** corrispondente in Admin Console. Questa associazione viene sincronizzata al momento dell’accesso dell’utente. [Ulteriori informazioni sul profilo di prodotto](../../v8/start/manage-permissions.md)

| **Gruppo di sicurezza Campaign Standard** | **Gruppo di operatori di Campaign V8** |
|----------|---------|
| Amministratori | Amministratori |
| Supervisori della consegna | Amministratori |
| Supervisori del workflow | Supervisori del workflow  |

## Approccio di migrazione da ruoli utente a diritti denominati

In Adobe Campaign Standard, il termine **Ruolo utente** è indicato come **Diritto denominato** in Campaign V8. La tabella seguente illustra la terminologia utilizzata per **Diritti denominati** in Campaign V8 corrispondenti a **Ruoli utente** in Campaign Standard.

| **Ruolo utente Campaign Standard** | **Campaign V8 denominato a destra** | **Descrizione**  |
|----------|---------|---------|
| Amministrazione | Amministrazione | L’utente con i permessi di amministratore ha accesso completo all’istanza. |
| Modello dati  | Amministrazione | Diritto di eseguire pubblicazioni e creare risorse personalizzate. Funzionalità correlate alla creazione di schemi disponibili per l’amministratore in Campaign V8.  |
| Recapito messaggi  | Amministrazione  | Diritto di approvare le consegne analizzate in precedenza.  |
| Esporta | Esporta | Diritto di esportare i dati.  |
| Accesso ai file  | Accesso ai file  | Diritto di approvare le consegne analizzate in precedenza.  |
| Importazione generica  | Importa  | Diritto per l’importazione di dati generici |
| Preparare le consegne | Preparare le consegne | Diritto di creare, modificare, preparare ed eliminare consegne.  |
| Esecuzione script SQL | Esecuzione script SQL | Diritto di eseguire qualsiasi comando SQL direttamente sul database. |
| Avviare le consegne  | Avviare le consegne  | Diritto di approvare le consegne analizzate in precedenza.  |
| Esecuzione comando di sistema | Esecuzione del programma | Diritto di eseguire comandi di sistema sul server. |
| Flusso di lavoro | Flusso di lavoro | Diritto di gestire l’esecuzione dei flussi di lavoro di avvio, arresto, pausa, ecc. |

## Approccio alla migrazione dall’unità organizzativa

In Adobe Campaign Standard, la **unità organizzativa** t è mappata al modello di gerarchia **Cartella** esistente in Campaign V8 per mantenere un controllo degli accessi simile. [Ulteriori informazioni sulla gestione delle cartelle](../../v8/start/folder-permissions.md)

| | **Campaign Standard** | **Campagna V8** |
|---------|----------|---------|
| **Terminologia**  | Unità organizzativa | Cartella |

## Approccio alla migrazione dal programma

In Campaign V8, **I programmi** sono rappresentati come **Cartelle**. Campaign V8 consente di creare cartelle e di limitarne l’accesso.

Utilizzando **Gruppi** e **Diritti denominati**, è possibile concedere a **Operatori** l&#39;accesso a **Cartelle** specifiche all&#39;interno della gerarchia di navigazione, con la possibilità di assegnare autorizzazioni di lettura, scrittura ed eliminazione. [Ulteriori informazioni sulla gestione delle cartelle](../../v8/start/folder-permissions.md)

Poiché un **Programma** è trattato come una **Cartella** in Campaign V8, il suo accesso può essere gestito nello stesso modo di qualsiasi altra cartella. Dopo la migrazione, gli amministratori di Campaign Standard possono seguire questi passaggi:

1. Da Esplora, fare clic con il pulsante destro del mouse su una cartella e selezionare **[!UICONTROL Properties...]**.
1. Passare alla scheda **[!UICONTROL Security]**.
1. Modifica le autorizzazioni del gruppo di operatori in base al modello di accesso desiderato. 

## Mappatura del profilo di prodotto per accedere alle API REST 

Per accedere alle API transazionali dall&#39;istanza di esecuzione in Campaign V8, è necessario un nuovo **profilo di prodotto**, oltre ai profili di prodotto **Amministratore** e **Centro messaggi**. Questo nuovo **profilo di prodotto** verrà aggiunto agli account tecnici esistenti o precreati in Campaign Standard.

Dopo la migrazione, gli utenti Campaign Standard devono rivedere le **mappature del profilo di prodotto** e assegnare il **profilo di prodotto** appropriato se non desiderano collegare i loro **account tecnici** al profilo di prodotto **Amministratore**. Per le integrazioni future, è consigliabile utilizzare l&#39;ID tenant **di Campaign V8 nell&#39;** URL REST **invece del precedente** ID tenant **del Campaign Standard.**

## Migrazione dell’accesso alle risorse integrate di Campaign per gli operatori Campaign Standard

Gli operatori migrati da Campaign Standard avranno accesso in lettura a specifiche risorse integrate in Campaign V8.

## Ruoli e gruppi di sicurezza non migrati {#non-migrated-groups-roles}

Di seguito è riportato un elenco dei ruoli Campaign Standard che non sono stati trasferiti:

* Account inoltro predefinito 

* Push del Centro messaggi 

Di seguito è riportato un elenco dei mapping dei gruppi di sicurezza di Campaign Standard per i quali non è stata eseguita la transizione.

* Agenti del Centro messaggi

* Agenti push del centro messaggi

* Application manager Adobe Experience Manager

* Account Relay
 


 

 


