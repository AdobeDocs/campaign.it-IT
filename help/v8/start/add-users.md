---
title: Concedere le autorizzazioni per Campaign v8
description: Scopri come concedere le autorizzazioni per Campaign v8
feature: Permissions
role: User, Admin
level: Beginner
exl-id: 3d61abac-03df-42d3-a950-37e41a5a7756
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%
---
# Introduzione alle autorizzazioni

In Adobe Campaign, gli utenti sono **operatori** e **gruppi di operatori** rappresentano ruoli utente.

Un operatore è un utente di Adobe Campaign che dispone delle autorizzazioni per accedere ed eseguire azioni. Per impostazione predefinita, gli operatori sono archiviati nel nodo **[!UICONTROL Administration > Access management > Operators]**.

Adobe Campaign viene fornito con gruppi di operatori incorporati, come Campaign Manager o Workflow Supervisors. Ulteriori informazioni sulle autorizzazioni in [questa sezione](../start/gs-permissions.md)

In qualità di membro di un gruppo di operatori, un utente dispone dei diritti per eseguire operazioni, denominate &quot;Diritti denominati&quot;, e ha accesso ai dati, contenuti nelle cartelle della visualizzazione **Explorer**. Un operatore può essere membro di più gruppi di operatori: i diritti e le autorizzazioni di accesso sono additivi.

I diritti denominati concedono le autorizzazioni a:

* Eseguire operazioni
Ad esempio, il pulsante **Analizza** nell&#39;editor di recapito è attivato per i membri del gruppo **Operatore di recapito** che dispongono del diritto denominato **Prepara recapito**

* Accesso alle cartelle
L&#39;appartenenza ai gruppi di operatori può concedere o limitare i diritti di accesso alle cartelle modificando le impostazioni di protezione delle cartelle. Per ulteriori informazioni, consulta [questa pagina](../start/folder-permissions.md). Ad esempio, può influire su: **Accesso in scrittura** per creare nuove entità (come consegne, profili e così via), **Accesso in lettura** per utilizzare le entità, **Accesso in eliminazione** per eliminare le entità.

## Aree di protezione

Ogni operatore deve essere collegato a una zona per accedere a un&#39;istanza e l&#39;IP dell&#39;operatore deve essere incluso negli indirizzi o nei set di indirizzi definiti nell&#39;area di sicurezza. La configurazione dell’area di sicurezza viene eseguita nel file di configurazione del server Adobe Campaign.

Gli operatori sono collegati a un&#39;area di sicurezza dal relativo profilo nella console, accessibile nel nodo **[!UICONTROL Administration > Access management > Operators]**.

>[!NOTE]
>
>In qualità di utente di Managed Cloud Services, Adobe imposta le aree di sicurezza per te. Per ulteriori informazioni, [contattare Adobe](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html){target="_blank"}.

**Ulteriori informazioni**

* [Diritti denominati incorporati](../start/gs-permissions.md)

* [Passaggi per impostare le autorizzazioni](../start/manage-permissions.md)
