---
title: Introduzione alle autorizzazioni in Campaign v8
description: Scopri come definire le autorizzazioni in Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 4%

---

# Introduzione alle autorizzazioni{#gs-permissions}

Adobe Campaign ti consente di definire e gestire i diritti assegnati agli utenti. Si tratta di una serie di diritti e restrizioni che autorizzano o negano:

* Accedere a determinate funzionalità
* Accedere a determinati dati
* Accedere a determinate azioni (creazione, modifica, eliminazione)

Queste autorizzazioni vengono definite combinando le autorizzazioni del gruppo di operatori, i diritti denominati e le autorizzazioni per le cartelle.

In Adobe Campaign, gli utenti sono **operatori** e **gruppi di operatori** rappresentano ruoli utente. Un operatore è un utente di Adobe Campaign che dispone delle autorizzazioni per accedere ed eseguire azioni. Gli utenti vengono creati in Admin Console. Le autorizzazioni si applicano ai profili utente o ai gruppi di utenti. È possibile concedere due tipi di autorizzazioni:

* È possibile definire gruppi di operatori a cui si attribuiscono diritti, quindi associare gli operatori a uno o più gruppi. Questo consente di riutilizzare i diritti e rendere più coerenti i profili dell’operatore. Semplifica inoltre la gestione e la manutenzione dei profili utente.
* Puoi assegnare i diritti denominati direttamente agli utenti, in alcuni casi per sovraccaricare i diritti allocati tramite i gruppi.

## Passaggi chiave per concedere le autorizzazioni{#key-steps-permissions}

In qualità di amministratore di prodotto, puoi concedere autorizzazioni agli utenti della tua organizzazione. Le autorizzazioni vengono concesse tramite Adobe Admin Console e la console client di Campaign. Gli utenti accedono ad Adobe Campaign con il proprio Adobe ID. Scopri come connetterti ad Adobe Campaign in [questa pagina](connect.md).

I passaggi chiave sono i seguenti:

* **Passaggio 1**: definisci i gruppi di operatori e assegna loro le autorizzazioni nella console client di Campaign. [Ulteriori informazioni](manage-permissions.md#create-product-profile).
Tieni presente che puoi anche utilizzare i gruppi di operatori incorporati per iniziare con. Questi gruppi predefiniti e le relative autorizzazioni sono elencati in [questa sezione](manage-permissions.md#ootb-productprofiles).
* **Passaggio 2**: creare in Adobe Admin Console profili di prodotto corrispondenti a tali gruppi. [Ulteriori informazioni](manage-permissions.md#create-product-profile).
Puoi utilizzare i profili di prodotto incorporati per iniziare con. [Ulteriori informazioni](manage-permissions.md#ootb-productprofiles).
* **Passaggio 3**: crea utenti in Adobe Admin Console e assegnali a un profilo di prodotto. [Ulteriori informazioni](manage-permissions.md#add-users).
* **Passaggio 4** (facoltativo): assegnare autorizzazioni alle cartelle. [Ulteriori informazioni](manage-permissions.md#ootb-productprofiles).

## Informazioni su Admin Console{#gs-admin-console}

Adobe Admin Console è una posizione centrale per la gestione delle adesioni Adobe in tutta l’organizzazione. È accessibile solo agli amministratori di prodotto.

Utilizza Admin Console per aggiungere utenti, creare e assegnare profili di prodotto (che sono gruppi di ruoli dell’operatore).

Scopri come aggiungere utenti in [questa pagina](manage-permissions.md#add-users).

## Informazioni sui profili di prodotto{#ootb-product-profiles}

I profili di prodotto sono gruppi di prodotti e servizi che puoi assegnare agli utenti. In Adobe Experience Cloud, le autorizzazioni si basano sul profilo di un prodotto, non sull’utente. Tuttavia, puoi delegare i diritti di amministratore a utenti specifici.

In Admin Console, ogni **profilo di prodotto** di Adobe Experience Cloud per Campaign è associato a un **gruppo di operatori** nella console client di Campaign.

Scopri come creare e assegnare profili di prodotto in [questa pagina](manage-permissions.md#create-a-product-profile).

## Diritti denominati della campagna{#named-rights}

In qualità di membro di un profilo di prodotto (ovvero di un gruppo di operatori), un utente dispone dei diritti per eseguire operazioni, denominate &quot;Diritti denominati&quot;, e ha accesso in lettura e/o scrittura ai dati. Un operatore può essere membro di più gruppi di operatori: i diritti e le autorizzazioni di accesso sono additivi.

Ulteriori informazioni sui diritti denominati in [questa sezione](manage-permissions.md#use-named-rights).
