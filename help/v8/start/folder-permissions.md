---
title: Concedere e limitare le autorizzazioni per le cartelle di Campaign
description: Scopri come concedere o limitare le autorizzazioni per le cartelle
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 5bd8dbba-7a06-4737-bc5a-60354f91c709
source-git-commit: 4a62c551c43cd5a4866df36cce10e294f35db363
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 0%

---

# Gestire le autorizzazioni cartella{#manage-folder-permissions}

## Limitare l’accesso a una cartella{#restrict-access-to-a-folder}

Utilizza le autorizzazioni sulle cartelle per organizzare e controllare l’accesso ai dati di Campaign.

La gestione delle cartelle è descritta in [questa pagina](../audiences/folders-and-views.md).

Per modificare le autorizzazioni per una cartella Campaign specifica, effettua le seguenti operazioni:

1. Fare clic con il pulsante destro del mouse sulla cartella e selezionare **[!UICONTROL Properties...]**.
1. Passare alla scheda **[!UICONTROL Security]** per visualizzare le autorizzazioni per questa cartella.

   ![](assets/folder-permissions.png)

* Per **autorizzare un gruppo o un operatore**, fare clic sul pulsante **[!UICONTROL Add]** e selezionare il gruppo o l&#39;operatore a cui assegnare le autorizzazioni per la cartella.
* Per **vietare un gruppo o un operatore**, fare clic su **[!UICONTROL Delete]** e selezionare il gruppo o l&#39;operatore per rimuovere l&#39;autorizzazione per la cartella.
* Per **selezionare i diritti assegnati a un gruppo o a un operatore**, selezionare il gruppo o l&#39;operatore, selezionare i diritti di accesso che si desidera concedere e deselezionare gli altri.

>[!NOTE]
>
>Non è possibile creare un oggetto per il quale non si dispone di almeno una cartella con diritti di scrittura.
>
>Per creare i frammenti non è necessario essere un amministratore, ma è necessario disporre dei diritti di scrittura per almeno una cartella &quot;Frammento visivo di contenuto&quot;. In caso contrario, non potrai creare un frammento visivo.

## Propagare le autorizzazioni {#propagate-permissions}

Per propagare autorizzazioni e diritti di accesso, selezionare l&#39;opzione **[!UICONTROL Propagate]** nelle proprietà della cartella.

Le autorizzazioni definite in questa finestra verranno quindi applicate a tutte le sottocartelle del nodo corrente. Puoi sempre sovraccaricare queste autorizzazioni per ciascuna sottocartella.

>[!NOTE]
>
>Se si deseleziona l&#39;opzione **[!UICONTROL Propagate]** per una cartella, questa non viene cancellata per le sottocartelle. È necessario deselezionarla in modo esplicito per ciascuna sottocartella.

## Concedi l’accesso a tutti gli operatori {#grant-access-to-all-operators}

Nella scheda **[!UICONTROL Security]**, selezionare **[!UICONTROL System folder]** per consentire l&#39;accesso a tutti gli operatori, indipendentemente dalle relative autorizzazioni.

Se questa opzione è deselezionata, è necessario aggiungere esplicitamente l’operatore (o il relativo gruppo) all’elenco di autorizzazioni affinché possano accedervi.
