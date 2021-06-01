---
product: Adobe Campaign
title: Concedere autorizzazioni a Campaign v8
description: Scopri come concedere autorizzazioni a Campaign v8
feature: Tipi di pubblico
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 2%

---

# Introduzione alle autorizzazioni

In Adobe Campaign, gli utenti sono **operatori** e **gruppi di operatori** rappresentano i ruoli utente.

Adobe Campaign viene fornito con gruppi di operatori incorporati, come Campaign Manager o Workflow Supervisors. Tutti i gruppi incorporati sono elencati in [questa pagina](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

In qualità di membro di un gruppo di operatori, un utente dispone dei diritti per eseguire operazioni, denominati &quot;Diritti denominati&quot;, e ha accesso ai dati, contenuti nelle cartelle nella visualizzazione **Esplora risorse**. Un operatore può essere membro di più gruppi di operatori: diritti e autorizzazioni di accesso sono additivi.

Autorizzazioni di concessione diritti denominati per:

* Eseguire operazioni
Ad esempio, il pulsante **Analizza** nell&#39;editor Consegna viene attivato per i membri del gruppo **Operatore consegna** che hanno il nome **Prepara consegna** Destra

* Accesso alle cartelle
L&#39;appartenenza ai gruppi di operatori può concedere o limitare i diritti di accesso alle cartelle modificando le [impostazioni di protezione nelle cartelle](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder). Ad esempio, può avere un impatto: **Accesso in scrittura** per creare nuove entità (come consegne, profili, ecc.), **Accesso in lettura** per utilizzare le entità, **Elimina accesso** per eliminare le entità.

**Ulteriori informazioni**

* [Diritti denominati incorporati](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html)

* [Gruppi di operatori incorporati](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

* [Passaggi per impostare le autorizzazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html)
