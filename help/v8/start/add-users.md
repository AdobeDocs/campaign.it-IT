---
title: Concedere le autorizzazioni per Campaign v8
description: Scopri come concedere le autorizzazioni per Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: 5ab598d904bf900bcb4c01680e1b4730881ff8a5
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 2%

---

# Introduzione alle autorizzazioni

In Adobe Campaign, gli utenti sono **operatori** e **gruppi di operatori** rappresenta i ruoli utente.

Un operatore è un utente di Adobe Campaign che dispone delle autorizzazioni per accedere ed eseguire azioni. Per impostazione predefinita, gli operatori vengono memorizzati nella **[!UICONTROL Administration > Access management > Operators]** nodo.

Adobe Campaign viene fornito con gruppi di operatori incorporati, come Campaign Manager o Workflow Supervisors. Ulteriori informazioni sulle autorizzazioni in [questa sezione](../start/gs-permissions.md)

In qualità di membro di un gruppo di operatori, un utente dispone dei diritti per eseguire operazioni, denominate &quot;Diritti denominati&quot;, e ha accesso ai dati, contenuti nelle cartelle in **Esplora** visualizzazione. Un operatore può essere membro di più gruppi di operatori: i diritti e le autorizzazioni di accesso sono additivi.

I diritti denominati concedono le autorizzazioni a:

* Eseguire operazioni Ad esempio, il **Analizza** nell’editor di consegna sia attivato per i membri del gruppo **Operatore di consegna** gruppo che dispone di **Prepara consegna** Denominato a destra

* Accesso alle cartelle L&#39;appartenenza ai gruppi di operatori può concedere o limitare i diritti di accesso alle cartelle modificando le impostazioni di protezione delle cartelle. Ulteriori informazioni in [questa pagina](../start/folder-permissions.md). Ad esempio, può avere un impatto su: **Accesso in scrittura** creare nuove entità (come consegne, profili, ecc.), **Accesso in lettura** per utilizzare le entità, **Elimina accesso** per eliminare le entità.

## Aree di protezione

Ogni operatore deve essere collegato a una zona per accedere a un&#39;istanza e l&#39;IP dell&#39;operatore deve essere incluso negli indirizzi o nei set di indirizzi definiti nell&#39;area di sicurezza. La configurazione dell’area di sicurezza viene eseguita nel file di configurazione del server Adobe Campaign.

Gli operatori sono collegati a un’area di sicurezza dal suo profilo nella console, accessibile nella **[!UICONTROL Administration > Access management > Operators]** nodo.

>[!NOTE]
>
>In qualità di utente di Cloud Service gestiti, Adobe imposta automaticamente le aree di protezione. Per ulteriori informazioni, [Adobe di contatto](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Ulteriori informazioni**

* [Diritti denominati incorporati](../start/gs-permissions.md)

* [Passaggi per impostare le autorizzazioni](../start/manage-permissions.md)
