---
solution: Campaign
product: Adobe Campaign
title: Concedere autorizzazioni a Campaign v8
description: Scopri come concedere autorizzazioni a Campaign v8
feature: Tipi di pubblico
role: Data Engineer
level: Beginner
source-git-commit: 22f47bed75d78684c85471330aca7dadafb9ed65
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 7%

---

# Introduzione alle autorizzazioni

In Adobe Campaign, gli utenti sono **operatori** e **gruppi di operatori** rappresentano i ruoli utente.

Un operatore è un utente Adobe Campaign che dispone delle autorizzazioni per accedere ed eseguire azioni. Per impostazione predefinita, gli operatori sono memorizzati nel nodo **[!UICONTROL Administration > Access management > Operators]** .

Adobe Campaign viene fornito con gruppi di operatori incorporati, come Campaign Manager o Workflow Supervisors. Tutti i gruppi incorporati sono elencati nella documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}.

In qualità di membro di un gruppo di operatori, un utente dispone dei diritti per eseguire operazioni, denominati &quot;Diritti denominati&quot;, e ha accesso ai dati, contenuti nelle cartelle nella visualizzazione **Esplora risorse**. Un operatore può essere membro di più gruppi di operatori: diritti e autorizzazioni di accesso sono additivi.

Autorizzazioni di concessione diritti denominati per:

* Eseguire operazioni
Ad esempio, il pulsante **Analizza** nell&#39;editor Consegna viene attivato per i membri del gruppo **Operatore consegna** che hanno il nome **Prepara consegna** Destra

* Accesso alle cartelle
L&#39;appartenenza ai gruppi di operatori può concedere o limitare i diritti di accesso alle cartelle modificando le impostazioni di protezione nelle cartelle. [Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}. Ad esempio, può avere un impatto: **Accesso in scrittura** per creare nuove entità (come consegne, profili, ecc.), **Accesso in lettura** per utilizzare le entità, **Elimina accesso** per eliminare le entità.

## Zone di sicurezza

Ogni operatore deve essere collegato a una zona per accedere a un’istanza e l’IP dell’operatore deve essere incluso negli indirizzi o nei set di indirizzi definiti nella zona di sicurezza. La configurazione dell’area di sicurezza viene eseguita nel file di configurazione del server Adobe Campaign.

Gli operatori sono collegati a una zona di sicurezza dal relativo profilo nella console, accessibile nel nodo **[!UICONTROL Administration > Access management > Operators]** .

? In qualità di utente di Cloud Services gestiti, Adobe imposta le aree di protezione. Per ulteriori informazioni, [contattare Adobe](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target=&quot;_blank&quot;}.

**Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7**

* [Diritti](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html) denominati incorporati{target=&quot;_blank&quot;}

* [Gruppi di operatori incorporati](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

* [Passaggi per impostare le autorizzazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}
