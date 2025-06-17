---
title: Scoprire l’interfaccia utente di Campaign
description: Scopri come navigare e utilizzare l’interfaccia utente di Campaign
feature: Overview
role: User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: 9d5a2ca1e9858a727377b8afa6bdd7e3761c1b56
workflow-type: ht
source-wordcount: '1072'
ht-degree: 100%

---

# Scoprire l’interfaccia utente {#ui-client-console}

Puoi accedere ad Adobe Campaign tramite la console client o l’interfaccia utente web. Puoi anche utilizzare le API per gestire i dati ed eseguire attività nella piattaforma Campaign.

>[!CAUTION]
>
>Questa documentazione si incentra sull’utilizzo della Console client di Campaign. Se utilizzi l’interfaccia utente di Campaign Web, consulta [questa documentazione](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=it){target="_blank"}.

* **Console client**: la console client di Campaign è un’applicazione nativa che comunica con il server applicazioni di Adobe Campaign tramite protocolli Internet standard, quali SOAP e HTTP. La console client di Campaign centralizza tutte le funzionalità e le impostazioni e richiede una larghezza di banda minima in quanto si basa su una cache locale. Progettata per una semplice implementazione, la console client di Campaign può essere distribuita da un browser Internet, può essere aggiornata automaticamente e non richiede alcuna configurazione di rete specifica perché genera solo traffico HTTP(S). [Ulteriori informazioni](#ui-access)

  Scopri come installare e configurare la console client di Campaign in [questa sezione](../start/connect.md).

* **Interfaccia utente web**: in qualità di utente di Campaign v8, a partire dalla versione v8.6.1, ora puoi accedere a un ambiente web, disponibile tramite l’interfaccia utente centrale di Adobe Experience Cloud. Puoi quindi connetterti ad Adobe Campaign da un browser web. Questa nuova interfaccia consente di creare, gestire ed eseguire azioni di marketing chiave. Tuttavia, tutte le funzionalità di Campaign non sono disponibili. [Ulteriori informazioni](#ac-web-ui).

  >[!AVAILABILITY]
  >
  >L’interfaccia utente di Campaign Web è disponibile solo per gli utenti che si connettono ad Adobe Campaign con il proprio Adobe ID. Ulteriori informazioni su [Adobe Identity Management System (IMS)](https://helpx.adobe.com/it/enterprise/using/identity.html){target="_blank"}.
  >

* **Accesso web**: le funzionalità di accesso web di Adobe Campaign consentono di accedere a un sottoinsieme di funzioni di Campaign con un browser web, utilizzando un’interfaccia utente HTML. Utilizza questa interfaccia web per accedere ai rapporti, verificare e convalidare i messaggi, accedere alle dashboard di monitoraggio e altro ancora.  Ulteriori informazioni sull’accesso a Campaign Web sono disponibili [in questa pagina](../start/connect.md#web-access).

* **API**: per rispondere a un numero maggiore di casi d’uso, è possibile chiamare il sistema da applicazioni esterne utilizzando le API dei servizi web esposte tramite il protocollo SOAP. Ulteriori informazioni sulle API di Campaign sono disponibili [in questa pagina](../dev/api.md).


## Utilizzare la console client {#ui-access}

La console client di Campaign è un’applicazione nativa che comunica con il server applicazioni di Adobe Campaign tramite protocolli Internet standard, quali SOAP e HTTP. La console client di Campaign centralizza tutte le funzionalità e le impostazioni e richiede una larghezza di banda minima in quanto si basa su una cache locale. Progettata per una semplice implementazione, la console client di Campaign può essere distribuita da un browser Internet, può essere aggiornata automaticamente e non richiede alcuna configurazione di rete specifica perché genera solo traffico HTTP(S).  [Ulteriori informazioni sulla console client di Campaign](../start/connect.md). Puoi passare all’interfaccia utente di Campaign Web dalla scheda dedicata nella pagina Home della console client.

![](assets/web-ui.png)


>[!NOTE]
>
>Se la nuova scheda di accesso non viene visualizzata, assicurati che nell’account esterno di Adobe Experience Cloud non siano lasciati vuoti i campi seguenti: **Server**, **Tenant**, **Server di richiamata** e **Indicatore di associazione**.


Puoi anche utilizzare un browser web per accedere a Campaign. In questo contesto, è disponibile solo un sottoinsieme delle funzionalità di Campaign. [Ulteriori informazioni](#web-browser)

### Navigare nell’interfaccia {#ui-browse}

Una volta che hai stabilito la connessione alla console client di Campaign, accedi alla page Home. Sfoglia i collegamenti per accedere alle funzionalità. Il set di funzionalità disponibile nell’interfaccia dipende dalle opzioni e dalle autorizzazioni.

Dalla sezione centrale della page Home, utilizza i collegamenti per accedere ai materiali della guida di Campaign, alla community e al sito web di supporto. Utilizza le schede centrali per navigare nella nuova interfaccia utente Campaign Web e nel Pannello di controllo Campaign.

Sfoglia le schede nella sezione superiore per accedere alle funzionalità chiave di Campaign:

![](assets/overview-home.png)

>[!NOTE]
>
>L’elenco delle funzionalità di base a cui puoi accedere dipende dalle autorizzazioni e dall’implementazione.

Per ogni funzionalità, è possibile accedere al set di funzioni chiave nella sezione **[!UICONTROL Browsing]**. Il collegamento **[!UICONTROL More]** ti consente di accedere a tutti gli altri componenti.

Ad esempio, durante la navigazione nella scheda **[!UICONTROL Profiles and targets]**, è possibile accedere agli elenchi dei destinatari, ai servizi di abbonamento, ai flussi di lavoro di targeting esistenti e alle scelte rapide per la creazione di tutti questi componenti.

![](assets/overview-list.png)

Quando selezioni un elemento nella schermata, questo viene caricato in una nuova scheda in modo da poter sfogliare facilmente il contenuto.

![](assets/new-tab.png)

### Creare un elemento {#create-an-element}

Utilizza le scelte rapide nella sezione **[!UICONTROL Create]** a sinistra della schermata per aggiungere nuovi elementi. Puoi anche utilizzare il pulsante **[!UICONTROL Create]** sopra l’elenco per aggiungere nuovi elementi all’elenco corrente.

Ad esempio, nella pagina della consegna, utilizza il pulsante **[!UICONTROL Create]** per creare una nuova consegna.

![](assets/new-recipient.png)

<!--
## Use a web browser {#web-browser}

You can also access a subset of Campaign capabilities through the a web browser.

The web access interface is similar to the console interface. From a browser, you can use the same navigation and display features as in the console, but you can perform only a reduced set of actions on campaigns. For example, you can view and cancel campaigns, but you cannot modify campaigns. 

[Learn more about Campaign web access](../start/connect.md#web-access).-->

### Accedere a Campaign Explorer {#ac-explorer-ui}

Sfoglia Campaign Explorer per accedere a tutte le funzionalità e le impostazioni di Adobe Campaign.

![](assets/explorer.png)

Questa area di lavoro consente di accedere alla struttura di Explorer per sfogliare tutte le funzioni e le opzioni.

* La sezione a sinistra mostra la struttura di Campaign Explorer e consente di sfogliare tutti i componenti e le impostazioni dell’istanza in base alle autorizzazioni di cui disponi. Puoi aggiungere e personalizzare le cartelle come spiegato in [questa pagina](../audiences/folders-and-views.md).

* Nella sezione superiore viene visualizzato l’elenco dei record della cartella corrente. Questi elenchi sono completamente personalizzabili. [Ulteriori informazioni](../config/ui-settings.md)

* Nella sezione inferiore vengono visualizzati i dettagli del record selezionato.


## Interfaccia utente di Campaign Web {#ac-web-ui}

In qualità di utente della console client di Campaign v8, a partire dalla versione v8.6.1, ora puoi accedere a un ambiente web, disponibile tramite l’interfaccia utente centrale di Adobe Experience Cloud. Experience Cloud è un insieme integrato di applicazioni, prodotti e servizi per il marketing digitale di Adobe. Grazie alla sua interfaccia intuitiva, puoi accedere rapidamente alle applicazioni cloud, alle funzionalità dei prodotti e ai servizi.

![Pagina Home dell’interfaccia utente di Adobe Campaign Web](assets/ac-web-home.png)

>[!AVAILABILITY]
>
>L’interfaccia utente di Campaign Web è disponibile solo per gli utenti che si connettono ad Adobe Campaign con il proprio Adobe ID. Ulteriori informazioni su [Adobe Identity Management System (IMS)](https://helpx.adobe.com/it/enterprise/using/identity.html){target="_blank"}.
>

Ulteriori informazioni sulla nuova interfaccia utente di Campaign Web sono disponibili in [questa documentazione](https://experienceleague.adobe.com/docs/campaign-web/v8/campaign-web-home.html?lang=it){target="_blank"}. Puoi anche visitare la [pagina delle domande frequenti](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/faq){target="_blank"} dedicata, nella documentazione dell’interfaccia utente di Campaign Web.

Funzionalità aggiuntive e avanzate, configurazione e impostazioni sono disponibili solo nella console client. Ulteriori informazioni sulle funzionalità disponibili in entrambe le interfacce utente sono disponibili [nella documentazione dell’interfaccia utente di Campaign Web](https://experienceleague.adobe.com/docs/campaign-web/v8/start/capability-matrix.html?lang=it){target="_blank"}.


## Lingue supportate {#languages}

Le lingue supportate dipendono dall’interfaccia utente.

* Per l’interfaccia della console client di Campaign v8, le lingue supportate sono:

   * Inglese (Regno Unito)
   * Inglese (Stati Uniti)
   * Francese
   * Tedesco
   * Giapponese


  >[!CAUTION]
  >
  >La lingua viene selezionata durante il processo di installazione e non può essere modificata in seguito.

* Per le lingue supportate dall’interfaccia utente di Campaign Web, [consulta questa pagina](https://experienceleague.adobe.com/it/docs/campaign-web/v8/start/connect-to-campaign#language-pref){target="_blank"}.


La lingua influisce sui formati data e ora.

Le principali differenze tra l’inglese (US) e l’inglese (UK) sono:

<table> 
 <thead> 
  <tr> 
   <th> Formati<br /> </th> 
   <th> Inglese (US)<br /> </th> 
   <th> Inglese (UK)<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Data<br /> </td> 
   <td> La settimana inizia la domenica<br /> </td> 
   <td> La settimana inizia il lunedì<br /> </td> 
  </tr> 
  <tr> 
   <td> Data breve<br /> </td> 
   <td> <p>%2M/%2D/%4Y</p><p><strong>es: 09/25/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>es: 25/09/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Data breve con ora<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>es: 09/25/2018 10:47:25 PM</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>es: 25/09/2018 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
