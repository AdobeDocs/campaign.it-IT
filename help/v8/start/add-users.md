---
title: Concedere autorizzazioni a Campaign v8
description: Scopri come concedere autorizzazioni a Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
source-git-commit: ac4d0d0c16f429ca0948a3c3257558c46700baeb
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 6%

---

# Introduzione alle autorizzazioni

In Adobe Campaign, gli utenti sono **operatori** e **gruppi di operatori** rappresentano i ruoli utente.

Un operatore è un utente Adobe Campaign che dispone delle autorizzazioni per accedere ed eseguire azioni. Per impostazione predefinita, gli operatori vengono memorizzati nella **[!UICONTROL Administration > Access management > Operators]** nodo.

Adobe Campaign viene fornito con gruppi di operatori incorporati, come Campaign Manager o Workflow Supervisors. Tutti i gruppi incorporati sono elencati in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target="_blank"}.

In qualità di membro di un gruppo di operatori, un utente dispone dei diritti per eseguire operazioni, denominati &quot;Diritti denominati&quot;, e ha accesso ai dati, contenuti nelle cartelle in **Esplora risorse** visualizza. Un operatore può essere membro di più gruppi di operatori: diritti e autorizzazioni di accesso sono additivi.

Autorizzazioni di concessione diritti denominati per:

* Eseguire operazioni Ad esempio, il **Analizza** nell’editor consegne è attivato per i membri del **Operatore di consegna** gruppo che ha **Preparare la consegna** Denominato a destra

* L&#39;accesso alle cartelle L&#39;appartenenza a gruppi di operatori può concedere o limitare i diritti di accesso alle cartelle modificando le impostazioni di protezione nelle cartelle. [Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target="_blank"}. Ad esempio, può avere un impatto: **Accesso in scrittura** creare nuove entità (come consegne, profili, ecc.), **Accesso in lettura** per utilizzare entità, **Elimina accesso** per eliminare le entità.

## Zone di sicurezza

Ogni operatore deve essere collegato a una zona per accedere a un’istanza e l’IP dell’operatore deve essere incluso negli indirizzi o nei set di indirizzi definiti nella zona di sicurezza. La configurazione dell’area di sicurezza viene eseguita nel file di configurazione del server Adobe Campaign.

Gli operatori sono collegati a un’area di sicurezza dal suo profilo nella console, accessibile nella **[!UICONTROL Administration > Access management > Operators]** nodo.

![](../assets/do-not-localize/speech.png)  In qualità di utente di Cloud Services gestiti, Adobe imposta le aree di protezione. Per ulteriori informazioni, consulta [Adobe di contatto](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7**

* [Diritti denominati incorporati](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html){target="_blank"}

* [Gruppi di operatori incorporati](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target="_blank"}

* [Passaggi per impostare le autorizzazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target="_blank"}
