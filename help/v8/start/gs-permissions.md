---
title: Guida introduttiva alle autorizzazioni in Campaign v8
description: Scopri i passaggi per definire le autorizzazioni in Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: b63dc1616bc7ce1387a7bd0590c289b59f11b33f
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 3%

---

# Introduzione alle autorizzazioni{#gs-permissions}

Adobe Campaign ti consente di definire e gestire i diritti assegnati agli utenti. Si tratta di una serie di diritti e restrizioni che autorizzano o negano:

* Accesso a determinate funzionalità
* Accedere a determinati dati
* Accesso a determinate azioni (creazione, modifica, eliminazione)

Queste autorizzazioni vengono definite combinando le autorizzazioni del gruppo di operatori, i diritti denominati e le autorizzazioni per le cartelle.

In Adobe Campaign, gli utenti sono **operatori** e **gruppi di operatori** rappresentano i ruoli utente. Un operatore è un utente Adobe Campaign che dispone delle autorizzazioni per accedere ed eseguire azioni. Gli utenti vengono creati nell’Admin Console. Le autorizzazioni si applicano ai profili utente o ai gruppi di utenti. Puoi concedere due tipi di autorizzazioni:

* È possibile definire i gruppi di operatori a cui si attribuiscono i diritti, quindi associare gli operatori a uno o più gruppi. Questo consente di riutilizzare i diritti e di rendere i profili dell’operatore più coerenti. Inoltre, facilita la gestione e la manutenzione dei profili utente.
* Puoi assegnare diritti con nome direttamente agli utenti, in alcuni casi per sovraccaricare i diritti assegnati tramite i gruppi.

## Passaggi chiave per concedere le autorizzazioni{#key-steps-permissions}

In qualità di amministratore di prodotto, puoi concedere autorizzazioni agli utenti della tua organizzazione. Le autorizzazioni vengono concesse tramite la console client Adobe Admin Console e Campaign. Gli utenti accedono ad Adobe Campaign con il proprio Adobe ID. Scopri come connettersi ad Adobe Campaign in [questa pagina](connect.md).

I passaggi chiave sono i seguenti:

* **Passaggio 1**: Definisci i gruppi di operatori e assegna loro le autorizzazioni nella console client di Campaign. [Ulteriori informazioni](manage-permissions.md#create-product-profile).
Per iniziare, puoi anche utilizzare i gruppi di operatori incorporati . Questi gruppi predefiniti e le relative autorizzazioni sono elencati in [questa sezione](manage-permissions.md#ootb-productprofiles).
* **Passaggio 2**: Crea nell’Admin Console profili di prodotto che corrispondono a tali gruppi. [Ulteriori informazioni](manage-permissions.md#create-product-profile).
Puoi utilizzare i profili di prodotto incorporati per iniziare. [Ulteriori informazioni](manage-permissions.md#ootb-productprofiles).
* **Passaggio 3**: Crea gli utenti nell’Admin Console e assegnali a un profilo di prodotto. [Ulteriori informazioni](manage-permissions.md#add-users).
* **Passaggio 4** (facoltativo): Assegnare le autorizzazioni alle cartelle. [Ulteriori informazioni](manage-permissions.md#ootb-productprofiles).

## Informazioni sull’Admin Console{#gs-admin-console}

Adobe Admin Console è una posizione centrale per la gestione delle adesioni Adobi in tutta l’organizzazione. È accessibile solo agli amministratori di prodotto.

Utilizza l’Admin Console per aggiungere utenti, creare e assegnare profili di prodotto (che sono gruppi di ruoli operatore).

Scopri come aggiungere gli utenti in [questa pagina](manage-permissions.md#add-users).

## Informazioni sui profili di prodotto{#ootb-product-profiles}

I profili di prodotto sono gruppi di prodotti e servizi che puoi assegnare agli utenti. In Adobe Experience Cloud, le autorizzazioni sono basate sul profilo di un prodotto, non sull’utente. Tuttavia, puoi delegare i diritti amministrativi a utenti specifici.

Nell’Admin Console, ogni Adobe Experience Cloud **profilo di prodotto** per Campaign è associato a un **gruppo di operatori** nella console del client Campaign.

Scopri come creare e assegnare profili di prodotto in [questa pagina](manage-permissions.md#create-a-product-profile).

## Diritti denominati nella campagna{#named-rights}

In qualità di membro di un profilo di prodotto (ad esempio un gruppo di operatori), un utente dispone dei diritti per eseguire operazioni, denominati &quot;Diritti denominati&quot;, e dispone dell’accesso in lettura e/o scrittura ai dati. Un operatore può essere membro di più gruppi di operatori: diritti e autorizzazioni di accesso sono additivi.

Ulteriori informazioni sui diritti denominati in [questa sezione](manage-permissions.md#use-named-rights).