---
product: Adobe Campaign
title: Concedere autorizzazioni a Campaign v8
description: Scopri come concedere autorizzazioni a Campaign v8
feature: Tipi di pubblico
role: Data Engineer
level: Beginner
exl-id: 176cc4f0-8827-4127-9f03-7d75ac8cf917
source-git-commit: 0566d40370a3e14d5205861509f7c1ae8cb4b22d
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 4%

---

# Introduzione alle autorizzazioni

In Adobe Campaign, gli utenti sono **operatori** e **gruppi di operatori** rappresentano i ruoli utente.

Adobe Campaign viene fornito con gruppi di operatori incorporati, come Campaign Manager o Workflow Supervisors. Tutti i gruppi incorporati sono elencati nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups)

In qualità di membro di un gruppo di operatori, un utente dispone dei diritti per eseguire operazioni, denominati &quot;Diritti denominati&quot;, e ha accesso ai dati, contenuti nelle cartelle nella visualizzazione **Esplora risorse**. Un operatore può essere membro di più gruppi di operatori: diritti e autorizzazioni di accesso sono additivi.

Autorizzazioni di concessione diritti denominati per:

* Eseguire operazioni
Ad esempio, il pulsante **Analizza** nell&#39;editor Consegna viene attivato per i membri del gruppo **Operatore consegna** che hanno il nome **Prepara consegna** Destra

* Accesso alle cartelle
L&#39;appartenenza ai gruppi di operatori può concedere o limitare i diritti di accesso alle cartelle modificando le impostazioni di protezione nelle cartelle. [Ulteriori informazioni nella documentazione](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder) di Campaign Classic v7{target=&quot;_blank&quot;}. Ad esempio, può avere un impatto: **Accesso in scrittura** per creare nuove entità (come consegne, profili, ecc.), **Accesso in lettura** per utilizzare le entità, **Elimina accesso** per eliminare le entità.

**** Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7:

[!DNL :arrow_upper_right:] [Diritti](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-named-rights.html) denominati incorporati{target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Gruppi di operatori incorporati](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-groups.html?lang=en#default-groups){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Passaggi per impostare le autorizzazioni](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management.html){target=&quot;_blank&quot;}

[!DNL :arrow_upper_right:] [Impostazioni di protezione nelle cartelle](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-folders.html?lang=en#permissions-on-a-folder){target=&quot;_blank&quot;}