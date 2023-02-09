---
title: Concedere e limitare le autorizzazioni sulle cartelle di Campaign
description: Scopri come concedere o limitare le autorizzazioni sulle cartelle
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
source-git-commit: b96ac3bd2365c548d071e626721d606dd33200b5
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---

# Gestisci autorizzazioni cartella{#manage-folder-permissions}

## Limitare l’accesso a una cartella{#restrict-access-to-a-folder}

Utilizza le autorizzazioni nelle cartelle per organizzare e controllare l’accesso ai dati di Campaign.

La gestione delle cartelle è descritta in [questa pagina](../audiences/folders-and-views.md).

Per modificare le autorizzazioni su una cartella Campaign specifica, segui i passaggi seguenti:

1. Fai clic con il pulsante destro del mouse sulla cartella e seleziona **[!UICONTROL Properties...]**.
1. Sfoglia il **[!UICONTROL Security]** per visualizzare le autorizzazioni in questa cartella.

   ![](assets/folder-permissions.png)

* A **autorizzare un gruppo o un operatore**, fai clic su **[!UICONTROL Add]** e selezionare il gruppo o l&#39;operatore per assegnare le autorizzazioni per questa cartella.
* A **vietare un gruppo o un operatore**, fai clic su **[!UICONTROL Delete]** e selezionare il gruppo o l&#39;operatore per rimuovere l&#39;autorizzazione per questa cartella.
* A **selezionare i diritti assegnati a un gruppo o a un operatore**, seleziona il gruppo o l’operatore, seleziona i diritti di accesso che desideri concedere e deseleziona gli altri.

## Propagare le autorizzazioni {#propagate-permissions}

Per propagare le autorizzazioni e i diritti di accesso, seleziona la **[!UICONTROL Propagate]** nelle proprietà della cartella.

Le autorizzazioni definite in questa finestra verranno quindi applicate a tutte le sottocartelle del nodo corrente. Puoi sempre sovraccaricare queste autorizzazioni per ciascuna sottocartella.

>[!NOTE]
>
>Deselezionando la **[!UICONTROL Propagate]** l’opzione per una cartella non la cancella per le sottocartelle: è necessario cancellarlo esplicitamente per ciascuna sottocartella.

## Concedere l’accesso a tutti gli operatori {#grant-access-to-all-operators}

In **[!UICONTROL Security]** seleziona la scheda **[!UICONTROL System folder]** consentire l’accesso a tutti gli operatori, indipendentemente dalle relative autorizzazioni.

Se questa opzione è deselezionata, è necessario reinserire esplicitamente l’operatore (o il relativo gruppo) nell’elenco delle autorizzazioni per consentire loro di accedere.
