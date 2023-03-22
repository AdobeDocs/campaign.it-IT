---
title: Best practice per la sicurezza di Campaign
description: Guida introduttiva alle best practice per la sicurezza di Campaign
feature: Privacy, PI
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
source-git-commit: cfe559b83a7db36ab8d9223d04d348f3afd74730
workflow-type: tm+mt
source-wordcount: '603'
ht-degree: 1%

---

# Best practice per la sicurezza di Campaign {#ac-security}

Ad Adobe, prendiamo la sicurezza della tua esperienza digitale molto seriamente. Le pratiche di sicurezza sono profondamente radicate nei nostri processi e strumenti interni di sviluppo software e operazioni e sono rigorosamente seguite dai nostri team interfunzionali per prevenire, rilevare e rispondere agli incidenti in modo opportuno.

Inoltre, il nostro lavoro collaborativo con partner, ricercatori leader, istituti di ricerca sulla sicurezza e altre organizzazioni del settore ci aiuta a tenerci aggiornati sulle ultime minacce e vulnerabilità e incorporiamo regolarmente tecniche di sicurezza avanzate nei prodotti e nei servizi che offriamo.

## Privacy

La configurazione e l’indurimento della privacy è un elemento chiave dell’ottimizzazione della sicurezza. Seguono alcune best practice per quanto riguarda la privacy:

* Protect le informazioni personali del cliente (PI) utilizzando HTTPS invece di HTTP
* Utilizzo [Restrizione della vista PI](../dev/restrict-pi-view.md) per proteggere la privacy ed evitare che i dati vengano utilizzati in modo improprio
* Assicurati che le password crittografate siano limitate
* Protect le pagine che possono contenere informazioni personali come pagine mirror, applicazioni web, ecc.

![](../assets/do-not-localize/speech.png)  In qualità di utente di Cloud Services gestiti, Adobe collaborerà con te per implementare queste configurazioni nel tuo ambiente.


## Gestione degli accessi

La gestione degli accessi è una parte importante dell&#39;irrigidimento della sicurezza. Di seguito sono riportate alcune delle best practice principali:

* Creare un numero sufficiente di gruppi di sicurezza
* Verificare che ogni operatore disponga dei diritti di accesso appropriati

Ulteriori informazioni sulle autorizzazioni in [questa sezione](../start/gs-permissions.md)

## Linee guida sulla codifica

Nello sviluppo in Adobe Campaign (flussi di lavoro, JavaScript, JSSP, ecc.), segui sempre le seguenti linee guida:

* **Scripting**: cercare di evitare istruzioni SQL, utilizzare funzioni parametrizzate invece della concatenazione di stringhe, evitare l&#39;inserimento di SQL aggiungendo le funzioni SQL da utilizzare nell&#39;elenco consentiti.

* **Proteggere il modello dati**: utilizzare diritti denominati per limitare le azioni dell’operatore, aggiungere filtri di sistema (sysFilter)

* **Aggiunta di sottotitoli nelle applicazioni web**: aggiungi le didascalie nelle pagine di destinazione pubbliche e nelle pagine di abbonamento.

![](../assets/do-not-localize/book.png) Ulteriori informazioni in [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic){target="_blank"}


## Personalizzazione

Quando aggiungi collegamenti personalizzati al contenuto, evita sempre di avere alcuna personalizzazione nella parte dell’URL relativa al nome host per evitare potenziali lacune nella sicurezza. Gli esempi seguenti non devono mai essere utilizzati in tutti gli attributi URL &lt;`a href="">` o `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Restrizione dei dati

Devi accertarti che le password crittografate non siano accessibili da un utente autenticato con privilegi bassi. Per farlo, esistono due modi principali: limita l’accesso ai campi password solo o all’intera entità.

Questa restrizione consente di rimuovere i campi password ma lascia l’account esterno accessibile dall’interfaccia per tutti gli utenti. Per ulteriori informazioni, consulta [questa pagina](../dev/restrict-pi-view.md).

1. Accedi **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. Crea un nuovo **[!UICONTROL Extension of a schema]**.

1. Scegli **[!UICONTROL External Account]** (extAccount).

1. Nell’ultima schermata, puoi modificare il nuovo srcSchema per limitare l’accesso a tutti i campi password:

   Puoi sostituire l’elemento principale (`<element name="extAccount" ... >`) da:

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

   Il tuo srcSchema esteso può avere un aspetto simile a:

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
   >È possibile sostituire `$(loginId) = 0 or $(login) = 'admin'` da `hasNamedRight('admin')` per consentire a tutti gli utenti con diritti di amministratore di vedere queste password.


## Gestione degli accessi

La gestione degli accessi è una parte importante dell&#39;irrigidimento della sicurezza. Di seguito sono riportate alcune delle best practice principali:

* Creare un numero sufficiente di gruppi di sicurezza
* Verificare che ogni operatore disponga dei diritti di accesso appropriati

Ulteriori informazioni sulle autorizzazioni in [in questa sezione](../start/gs-permissions.md).

## Linee guida sulla codifica

Nello sviluppo in Adobe Campaign (flussi di lavoro, JavaScript, JSSP, ecc.), segui sempre le seguenti linee guida:

* **Scripting**: cercare di evitare istruzioni SQL, utilizzare funzioni parametrizzate invece della concatenazione di stringhe, evitare l&#39;inserimento di SQL aggiungendo le funzioni SQL da utilizzare nell&#39;elenco consentiti.

* **Proteggere il modello dati**: utilizzare diritti denominati per limitare le azioni dell’operatore, aggiungere filtri di sistema (sysFilter)

* **Aggiunta di sottotitoli nelle applicazioni web**: aggiungi le didascalie nelle pagine di destinazione pubbliche e nelle pagine di abbonamento.

![](../assets/do-not-localize/book.png) Ulteriori informazioni in [Documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html?lang=en#installing-campaign-classic){target="_blank"}
