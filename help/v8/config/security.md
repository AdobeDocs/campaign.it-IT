---
title: Best practice per la sicurezza di Campaign
description: Guida introduttiva alle best practice per la sicurezza di Campaign
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: 061197048885a30249bd18af7f8b24cb71def742
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 1%

---

# Best practice per la sicurezza di Campaign {#ac-security}

Ad Adobe, prendiamo molto seriamente la sicurezza della tua esperienza digitale. Le procedure di sicurezza sono profondamente radicate nei nostri processi e strumenti interni di sviluppo e gestione del software e sono rigorosamente seguite dai nostri team interfunzionali per prevenire, rilevare e rispondere agli incidenti in modo rapido.

Inoltre, il nostro lavoro collaborativo con partner, ricercatori di spicco, istituti di ricerca sulla sicurezza e altre organizzazioni del settore ci aiuta a rimanere aggiornati sulle ultime minacce e vulnerabilità e a incorporare regolarmente tecniche di sicurezza avanzate nei prodotti e nei servizi che offriamo.

## Privacy

La configurazione e l’irrigidimento della privacy sono un elemento chiave dell’ottimizzazione della sicurezza. Di seguito sono riportate alcune best practice da seguire relative alla privacy:

* Protect le informazioni personali del cliente (PI) utilizzando HTTPS anziché HTTP
* Utilizzare [Restrizione visualizzazione PI](../dev/restrict-pi-view.md) per proteggere la privacy e impedire l&#39;utilizzo improprio dei dati
* Assicurarsi che le password crittografate siano limitate
* Protect le pagine che potrebbero contenere informazioni personali come pagine mirror, applicazioni web, ecc.

![](../assets/do-not-localize/speech.png)  In qualità di utente di Cloud Service gestiti, Adobe collabora con te per implementare queste configurazioni nel tuo ambiente.


## Gestione degli accessi

La gestione degli accessi è una parte importante della protezione avanzata. Di seguito sono riportate alcune delle best practice principali:

* Creare un numero sufficiente di gruppi di sicurezza
* Verifica che ogni operatore disponga dei diritti di accesso appropriati

Ulteriori informazioni sulle autorizzazioni in [questa sezione](../start/gs-permissions.md)

## Linee guida per la codifica

Durante lo sviluppo in Adobe Campaign (flussi di lavoro, JavaScript, JSSP, ecc.), segui sempre le seguenti linee guida:

* **Scripting**: prova ad evitare le istruzioni SQL, utilizza funzioni con parametri invece della concatenazione di stringhe, evita l’iniezione di SQL aggiungendo le funzioni SQL da utilizzare all’elenco consentiti.

* **Proteggere il modello dati**: utilizzare diritti denominati per limitare le azioni dell’operatore, aggiungere filtri di sistema (sysFilter)

* **Aggiungere captchas nelle applicazioni web**: aggiungi i captcha nelle pagine di destinazione e nelle pagine di abbonamento pubbliche.

Ulteriori informazioni in [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}


## Personalizzazione

Quando aggiungi collegamenti personalizzati al contenuto, evita sempre di includere alcuna personalizzazione nella parte nome host dell’URL per evitare potenziali lacune di sicurezza. Gli esempi seguenti non devono mai essere utilizzati in tutti gli attributi URL &lt;`a href="">` o `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Limitazione dei dati

È necessario assicurarsi che le password crittografate non siano accessibili da un utente autenticato con privilegi limitati. A tal fine, esistono due modi principali: limitare l’accesso solo ai campi password o all’intera entità.

Questa restrizione consente di rimuovere i campi delle password, ma lascia l’account esterno accessibile dall’interfaccia per tutti gli utenti. Per ulteriori informazioni, consulta [questa pagina](../dev/restrict-pi-view.md).

1. Accedi **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. Crea un nuovo **[!UICONTROL Extension of a schema]**.

1. Scegli **[!UICONTROL External Account]** (extAccount).

1. Nell’ultima schermata, puoi modificare il nuovo srcSchema per limitare l’accesso a tutti i campi password:

   È possibile sostituire l&#39;elemento principale (`<element name="extAccount" ... >`) da:

   ```
   <element name="extAccount">
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
       <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
       <element name="s3Account">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
       </element>
       <element name="wapPush">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
       <element name="mms">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
       </element>
   </element>
   ```

   In questo modo lo schema src esteso può essere simile al seguente:

   ```
   <...>
       <element name="extAccount">
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
           <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
   
           <element name="s3Account">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="awsSecret"/>
           </element>
           <element name="wapPush">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
           <element name="mms">
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="password"/>
               <attribute accessibleIf="$(loginId) = 0 or $(login) = 'admin'" name="clientSecret"/>
           </element>
       </element>
   <...> 
   ```

   >[!NOTE]
   >
   >È possibile sostituire `$(loginId) = 0 or $(login) = 'admin'` da `hasNamedRight('admin')` per consentire a tutti gli utenti con diritti di amministratore di visualizzare queste password.


## Gestione degli accessi

La gestione degli accessi è una parte importante della protezione avanzata. Di seguito sono riportate alcune delle best practice principali:

* Creare un numero sufficiente di gruppi di sicurezza
* Verifica che ogni operatore disponga dei diritti di accesso appropriati

Ulteriori informazioni sulle autorizzazioni in [in questa sezione](../start/gs-permissions.md).

## Linee guida per la codifica

Durante lo sviluppo in Adobe Campaign (flussi di lavoro, JavaScript, JSSP, ecc.), segui sempre le seguenti linee guida:

* **Scripting**: prova ad evitare le istruzioni SQL, utilizza funzioni con parametri invece della concatenazione di stringhe, evita l’iniezione di SQL aggiungendo le funzioni SQL da utilizzare all’elenco consentiti.

* **Proteggere il modello dati**: utilizzare diritti denominati per limitare le azioni dell’operatore, aggiungere filtri di sistema (sysFilter)

* **Aggiungere captchas nelle applicazioni web**: aggiungi i captcha nelle pagine di destinazione e nelle pagine di abbonamento pubbliche.

Ulteriori informazioni in [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}
