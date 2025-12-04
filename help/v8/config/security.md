---
title: Best practice per la sicurezza di Campaign
description: Guida introduttiva alle best practice per la sicurezza di Campaign
feature: Privacy, PI
role: Developer
level: Beginner
exl-id: 1d593c8e-4b32-4902-93a7-7b18cef27cac
version: Campaign v8, Campaign Classic v7
source-git-commit: 3453820bb0eca7847ec55d7e6ea15766a57ab94e
workflow-type: tm+mt
source-wordcount: '2167'
ht-degree: 67%

---

# Best practice per la sicurezza di Campaign {#ac-security}

In Adobe, prendiamo la sicurezza della tua esperienza digitale molto seriamente. Le procedure di sicurezza sono profondamente radicate nei nostri processi e strumenti interni di sviluppo e gestione del software e sono rigorosamente seguite dai nostri team interfunzionali per prevenire, rilevare e rispondere agli incidenti in modo rapido.

Inoltre, il nostro lavoro collaborativo con partner, ricercatori di spicco, istituti di ricerca sulla sicurezza e altre organizzazioni del settore ci aiuta a rimanere aggiornati sulle ultime minacce e vulnerabilità e a incorporare regolarmente tecniche di sicurezza avanzate nei prodotti e nei servizi che offriamo.

## Privacy

Per gestire correttamente la privacy e i dati personali, attieniti alle normative applicabili alle regioni in cui operi. Le funzionalità di Adobe Campaign consentono di rispettare le normative elencate in [questa pagina](../start/privacy.md)

### Privacy di Adobe Experience Cloud {#experience-cloud-privacy}

Adobe Campaign fa parte delle soluzioni Adobe Experience Cloud. Il modo in cui viene gestita la privacy in Campaign rispetta i principi generali di Experience Cloud, come ad esempio quanto segue:

* **Quali informazioni vengono raccolte durante l’utilizzo di Adobe Experience Cloud**

  In qualità di azienda che utilizza le soluzioni Adobe Experience Cloud, puoi scegliere quali informazioni raccogliere e inviare all’account Adobe Experience Cloud. Alcuni esempi dei tipi di informazioni che possono essere raccolti includono attività di navigazione web, indirizzi IP, informazioni sulla posizione inviate dai dispositivi mobili, tassi di successo delle campagne, articoli acquistati o inseriti nel carrello, ecc.

  >[!NOTE]
  >
  >Come tutti i prodotti Adobe, Campaign raccoglie informazioni sugli utenti dell’app e del sito web. Per ulteriori informazioni, consulta l’[Informativa sulla privacy di Adobe](https://www.adobe.com/it/privacy/policy.html).

* **Utilizzare Adobe Experience Cloud per raccogliere informazioni**

   * Le soluzioni Adobe Experience Cloud utilizzano cookie e tecnologie simili, come web beacon (noti anche come tag o pixel), per consentirti di raccogliere informazioni. Per ulteriori informazioni sui cookie e sulle funzionalità di tracciamento con Adobe Campaign, consulta [questa sezione](#tracking-capabilities).
   * Puoi anche utilizzare le tecnologie Adobe Experience Cloud nelle tue app mobili. Per ulteriori informazioni sull&#39;invio di consegne per dispositivi mobili con Campaign, consulta [Canale SMS](../send/sms/sms-channel.md) e Canale app mobile.

* **Scelte degli utenti in materia di privacy relative all’utilizzo di Adobe Experience Cloud**

   Adobe richiede che tu fornisca ai clienti le informative sulla privacy che descrivono:

   * Le tue prassi in materia di privacy in relazione ad Adobe Experience Cloud
   * In che modo gli utenti possono impostare le proprie preferenze per la raccolta o l’utilizzo delle proprie informazioni in relazione ad Adobe Experience Cloud

  >[!NOTE]
  >
  >Come per tutti i prodotti di Adobe, gli utenti di Campaign possono scegliere di rinunciare alla condivisione di informazioni raccolte su di loro tramite app e siti web. Per ulteriori informazioni, consulta le [domande frequenti relative all’utilizzo di Adobe Experience Cloud](https://www.adobe.com/it/privacy/experience-cloud-usage-info-faq.html).

Per ulteriori dettagli sulla privacy di Adobe Experience Cloud, consulta [questa pagina](https://www.adobe.com/it/privacy/experience-cloud.html).

## Dati personali e utenti tipo {#personal-data}

Nella gestione della privacy è importante definire quali dati devono essere gestiti con cura e chi si occupa della gestione.
* **I dati personali** sono informazioni che possono identificare direttamente o indirettamente un individuo.
* **I dati personali riservati** sono informazioni relative a etnia, opinioni politiche, credenze religiose, precedenti penali, informazioni genetiche, dati sanitari, orientamento sessuale e informazioni biometriche di un individuo, nonché iscrizioni a sindacati.

È necessario prestare maggiore attenzione alla protezione dei dati personali durante l&#39;integrazione di Campaign con altre soluzioni Experience Cloud in cui i tipi di pubblico possono essere trasferiti da un sistema all&#39;altro, ad esempio [Adobe Analytics](../connect/ac-aa.md), [Experience Cloud Audiences](../start/shared-audiences.md), Campaign Standard o con altre soluzioni tramite [Connettore CRM](../../automation/workflow/crm-connector.md).

Le [normative principali](#privacy-regulations) si riferiscono alle diverse entità che gestiscono i dati come segue:

* Il **titolare del trattamento** è l’autorità che determina i mezzi e lo scopo della raccolta, dell’utilizzo e della condivisione dei dati personali.

* Il **responsabile del trattamento** è qualsiasi individuo o parte che raccoglie, utilizza o condivide dati personali come indicato dal titolare del trattamento.

* L’**interessato** è qualsiasi individuo i cui dati personali vengono raccolti, utilizzati o condivisi e che può essere identificato direttamente o indirettamente in base a tali dati personali.

Pertanto, in quanto azienda che raccoglie e condivide dati personali, ricopri il ruolo di titolare del trattamento, i tuoi clienti costituiscono gli interessati e Adobe Campaign agisce come responsabile del trattamento quando tratta i loro dati personali secondo le istruzioni da te fornite. In quanto titolare del trattamento, sei responsabile della gestione del rapporto con gli interessati, ad esempio durante la gestione delle [richieste di accesso a dati personali](#privacy-requests).

### Scenario del caso d’uso {#use-case-scenario}

Per illustrare il modo in cui interagiscono i diversi utenti tipo, ecco un esempio di un caso d’uso dettagliato di customer experience relativo al GDPR.

In questo esempio, il cliente Adobe Campaign è una compagnia aerea. La compagnia aerea è il **titolare del trattamento** e tutti i suoi clienti sono gli **interessati**. Laura in questo caso particolare è una cliente della compagnia aerea.

Di seguito sono elencati i diversi utenti tipo utilizzati in questo esempio:

* **Laura** è l’**interessato**. È il destinatario che riceve messaggi dalla compagnia aerea. Ammettiamo che Laura sia una viaggiatrice frequente e che a un certo punto decida di non voler ricevere messaggi pubblicitari o di marketing personalizzati da parte della compagnia aerea. Laura chiederà alla compagnia aerea (sulla base del loro processo) di cancellare il suo numero di viaggiatrice frequente.

* **Anne** è il **titolare del trattamento** presso la compagnia aerea. Riceve la richiesta di Laura, recupera gli ID utili richiesti per identificare l’interessato e invia la richiesta in Adobe Campaign.

* **Adobe Campaign** è il **responsabile del trattamento**.

![](assets/privacy-gdpr-flow.png)

Di seguito è riportato il flusso generale relativo a questo caso d’uso:

1. L’**interessato** (Laura) invia una richiesta GDPR al **titolare del trattamento** tramite e-mail, assistenza clienti o un portale web.

1. Il **titolare del trattamento** (Anne) invia la richiesta GDPR a Campaign tramite l’interfaccia o utilizzando un’API.

1. Una volta che il **responsabile del trattamento** (Adobe Campaign) riceve le informazioni, interviene sulla richiesta GDPR e invia una risposta o una conferma al **titolare del trattamento** (Anne).

1. Il **titolare del trattamento** (Anne) esamina le informazioni e le invia nuovamente all’**interessato** (Laura).

## Acquisizione dei dati {#data-acquisition}

 Adobe Campaign ti consente di raccogliere dati, incluse informazioni personali e riservate. È pertanto essenziale ricevere e monitorare il consenso dei destinatari.

* Assicurati che i destinatari ricevano le comunicazioni solo se lo desiderano. Per farlo, accetta al più presto le richieste di rifiuto e verifica il consenso mediante un processo di doppio consenso. Per ulteriori informazioni, consulta [Creare un abbonamento con doppio consenso](https://experienceleague.adobe.com/en/docs/campaign-classic/using/designing-content/web-forms/use-cases-web-forms){target=_blank}.
* Non importare elenchi fraudolenti e utilizza indirizzi di seed per verificare che il file client non venga utilizzato in modo fraudolento. Per ulteriori informazioni, consulta [Informazioni sugli indirizzi di seed](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/using-seed-addresses/about-seed-addresses){target=_blank}.
* Tramite la gestione del consenso e dei diritti puoi tenere traccia delle preferenze dei destinatari e gestire chi all’interno dell’organizzazione può accedere ai dati. Per ulteriori informazioni, consulta [questa sezione](#consent).
* Facilita e gestisci le richieste di accesso a dati personali dei destinatari. Per ulteriori informazioni, consulta [questa sezione](#privacy-requests).

## Gestione della privacy {#privacy-management}

La gestione della privacy si riferisce a tutti i processi e gli strumenti che possono aiutarti a rispettare le normative sulla privacy (GDPR, CCPA, ecc.).

 Adobe Campaign offre varie serie di funzioni dedicate alla gestione della privacy:
* Gestione del consenso, conservazione dei dati e ruoli degli utenti. Vedi [questa sezione](#consent).
* Richieste di accesso a dati personali (diritto di accesso e diritto all’oblio). Vedi [questa sezione](#privacy-requests).
* Rinuncia alla vendita di informazioni personali (specifica per il CCPA).

In [questa sezione](https://helpx.adobe.com/it/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow) sono illustrate le principali funzionalità di Campaign relative alla privacy e un esempio degli utenti tipo coinvolti.

### Consenso, conservazione e ruoli {#consent}

Adobe Campaign offre da sempre funzioni importanti necessarie per la privacy:

* **Gestione del consenso**: attraverso il processo di gestione degli abbonamenti, puoi gestire le preferenze dei destinatari e tenere traccia dei destinatari che hanno acconsentito all’abbonamento e di che tipo di abbonamento si tratta. Per ulteriori informazioni, consulta [Informazioni sugli abbonamenti](../../automation/workflow/subscription-services.md).
* **Conservazione dei dati**: tutte le tabelle di registro standard incorporate dispongono di periodi di conservazione preimpostati, che in genere limitano l’archiviazione dei dati a un massimo di 6 mesi. Puoi impostare ulteriori periodi di conservazione con i flussi di lavoro. Per maggiori informazioni, rivolgiti ai consulenti o agli amministratori tecnici di Adobe.
* **Gestione dei diritti**: Adobe Campaign consente di gestire i diritti assegnati ai vari operatori di Campaign tramite diversi ruoli predefiniti o personalizzati. Questo consente di gestire chi può modificare, esportare o accedere a diversi tipi di dati all’interno dell’azienda. Per ulteriori informazioni, consulta [Informazioni sulla gestione degli accessi](https://experienceleague.adobe.com/en/docs/campaign-classic/using/installing-campaign-classic/security-privacy/access-management){target=_blank}.

### Richieste di accesso a dati personali {#privacy-requests}

 Adobe Campaign offre funzionalità aggiuntive per consentirti di attenerti a determinate richieste di accesso a dati personali in qualità di titolare del trattamento:

* Il **diritto di accesso** è il diritto dell’interessato di ottenere conferma da parte del titolare del trattamento sul fatto che i dati personali che lo riguardano siano trattati o meno, su dove avvenga il trattamento e sullo scopo del trattamento.

* Il **diritto all’oblio** (richiesta di cancellazione) autorizza l’interessato a richiedere che il titolare del trattamento cancelli i suoi dati personali.

Le richieste di **accesso** ed **eliminazione** vengono presentate in [questa sezione](../start/privacy.md).

I passaggi di implementazione per creare queste richieste sono illustrati in [questa sezione](../start/privacy.md).

## Funzionalità di tracciamento {#tracking-capabilities}

### Cookie {#cookies}

Grazie alle sue funzionalità di tracciamento, Adobe Campaign consente di monitorare la navigazione dei destinatari della consegna utilizzando tre tipi di cookie: un cookie di sessione e due cookie permanenti.

* Un cookie di **sessione**: il cookie **nlid** contiene l’identificatore dell’e-mail inviata al contatto (**broadlogId**) e l’identificatore del modello del messaggio (**deliveryId**). Viene aggiunto quando il contatto fa clic su un URL incluso in un’e-mail inviata da Adobe Campaign e ti consente di tracciarne il comportamento sul web. Questo cookie di sessione viene cancellato automaticamente alla chiusura del browser. Il contatto può configurare il browser per rifiutare i cookie.

* Due cookie **permanenti**:
   * Il cookie **UUID** (Universal Unique IDentifier) è condiviso tra le diverse soluzioni Adobe Experience Cloud. Viene impostato una volta fino a quando non scompare dal browser client quando viene generato un nuovo valore. Questo cookie ti consente di identificare gli utenti che interagiscono con le soluzioni Experience Cloud quando visitano un sito web. Può essere depositato da una pagina di destinazione (per associare a un destinatario le attività cliente sconosciute) o da una consegna. La descrizione di questo cookie è disponibile in [questa pagina](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-mc.html#ec-cookies).
   * Il cookie **nllastdelid** (introdotto in Campaign Classic 20.3) è un cookie permanente che contiene il **deliveryId** dell’ultima consegna da cui l’utente ha fatto clic sul collegamento. Questo cookie viene utilizzato quando manca il cookie di sessione, per identificare la tabella di tracciamento che verrà utilizzata.

Normative quali il Regolamento generale sulla protezione dei dati (GDPR) affermano che le aziende necessitano del consenso degli utenti del sito web per installare i cookie.

* Le finestre pop-up dovrebbero essere evitate in quanto spesso sono bloccate dai browser.

### Tracciamento dei messaggi {#message-tracking}

Adobe Campaign ti consente di tenere traccia delle e-mail inviate e del comportamento dei destinatari della consegna: apertura, clic su collegamenti, annullamenti di abbonamenti, ecc. Per ulteriori informazioni, consulta [Informazioni sui messaggi](../start/gs-message.md).

A questo scopo, aggiungi collegamenti tracciati ai messaggi, in modo da poter misurare l’impatto della consegna e il comportamento del destinatario nella scheda Tracking (Tracciamento) del dashboard di consegna. I dati di tracciamento vengono interpretati nel rapporto Indicatori di tracciamento. Per ulteriori informazioni sul tracciamento, consulta [questa pagina](../send/tracking.md).

### Tracciamento web {#web-tracking}

>[!AVAILABILITY]
>
>Il tracciamento web non è disponibile in Campaign v8. Ulteriori informazioni sulle funzionalità non disponibili in [questa pagina](../start/v7-to-v8.md#gs-unavailable-features).

<!--
Privacy configuration and hardening is a key element of security optimization. Here are some best practices to follow regarding privacy:

* Protect your customer Personal Information (PI) by using HTTPS instead of HTTP
* Use [PI view restriction](../dev/restrict-pi-view.md) to protect privacy and prevent data from being misused
* Make sure that encrypted passwords are restricted
* Protect the pages that might contain personal information such as mirror pages, web applications, etc.
-->

>[!NOTE]
>
>In qualità di utente di Managed Cloud Services, Adobe collaborerà con te per implementare queste configurazioni nel tuo ambiente.


## Gestione degli accessi

La gestione degli accessi è una parte importante della protezione avanzata. Di seguito sono riportate alcune delle best practice principali:

* Creare un numero sufficiente di gruppi di sicurezza
* Verifica che ogni operatore disponga dei diritti di accesso appropriati

Ulteriori informazioni sulle autorizzazioni in [questa sezione](../start/gs-permissions.md)

## Linee guida per la codifica

Durante lo sviluppo in Adobe Campaign (flussi di lavoro, JavaScript, JSSP, ecc.), segui sempre le seguenti linee guida:

* **Scripting**: tentare di evitare istruzioni SQL, utilizzare funzioni con parametri anziché concatenare stringhe, evitare l&#39;inserimento di istruzioni SQL aggiungendo le funzioni SQL da utilizzare all&#39;elenco consentiti.

* **Proteggere il modello dati**: utilizzare diritti denominati per limitare le azioni dell&#39;operatore, aggiungere filtri di sistema (sysFilter)

* **Aggiungi captchas nelle applicazioni Web**: aggiungi i captchas nelle pagine di destinazione pubbliche e nelle pagine di abbonamento.

Ulteriori informazioni sono disponibili nella [documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}.


## Personalizzazione

Quando aggiungi collegamenti personalizzati al contenuto, evita sempre di includere alcuna personalizzazione nella parte nome host dell’URL per evitare potenziali lacune di sicurezza. I seguenti esempi non devono mai essere utilizzati in tutti gli attributi URL &lt;`a href="">` o `<img src="">`:

* `<%= url >`
* `https://<%= url >`
* `https://<%= domain >/path`
* `https://<%= sub-domain >.domain.tld/path`
* `https://sub.domain<%= main domain %>/path`

## Limitazione dei dati

È necessario assicurarsi che le password crittografate non siano accessibili da un utente autenticato con privilegi limitati. A tal fine, esistono due modi principali: limitare l’accesso solo ai campi password o all’intera entità.

Questa restrizione consente di rimuovere i campi delle password, ma lascia l’account esterno accessibile dall’interfaccia per tutti gli utenti. Per ulteriori informazioni, consulta [questa pagina](../dev/restrict-pi-view.md).

1. Vai in **[!UICONTROL Administration]** > **[!UICONTROL Configuration]** > **[!UICONTROL Data schemas]**.

1. Crea un nuovo **[!UICONTROL Extension of a schema]**.

1. Scegliere **[!UICONTROL External Account]** (extAccount).

1. Nell’ultima schermata, puoi modificare il nuovo srcSchema per limitare l’accesso a tutti i campi password:

   È possibile sostituire l&#39;elemento principale (`<element name="extAccount" ... >`) con:

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
   >È possibile sostituire `$(loginId) = 0 or $(login) = 'admin'` con `hasNamedRight('admin')` per consentire a tutti gli utenti con diritti di amministratore di visualizzare queste password.


## Gestione degli accessi

La gestione degli accessi è una parte importante della protezione avanzata. Di seguito sono riportate alcune delle best practice principali:

* Creare un numero sufficiente di gruppi di sicurezza
* Verifica che ogni operatore disponga dei diritti di accesso appropriati

Ulteriori informazioni sulle autorizzazioni in [sono disponibili in questa sezione](../start/gs-permissions.md).

## Linee guida per la codifica

Durante lo sviluppo in Adobe Campaign (flussi di lavoro, JavaScript, JSSP, ecc.), segui sempre le seguenti linee guida:

* **Scripting**: tentare di evitare istruzioni SQL, utilizzare funzioni con parametri anziché concatenare stringhe, evitare l&#39;inserimento di istruzioni SQL aggiungendo le funzioni SQL da utilizzare all&#39;elenco consentiti.

* **Proteggere il modello dati**: utilizzare diritti denominati per limitare le azioni dell&#39;operatore, aggiungere filtri di sistema (sysFilter)

* **Aggiungi captchas nelle applicazioni Web**: aggiungi i captchas nelle pagine di destinazione pubbliche e nelle pagine di abbonamento.

Ulteriori informazioni sono disponibili nella [documentazione di Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/security-privacy/scripting-coding-guidelines.html#installing-campaign-classic){target="_blank"}.
