---
title: Scopri lo spazio di lavoro di Campaign
description: Scopri come sfogliare e utilizzare l’area di lavoro di Campaign
feature: Overview
role: Admin, Developer, User
level: Beginner
exl-id: a7846b95-7570-4dce-b3f4-d3cc23eefcac
source-git-commit: eed3396584940f99a865eef2358887b6bf5c4936
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 9%

---

# Scopri l’interfaccia utente di Campaign

## Accedere all’interfaccia di Campaign{#ui-access}

L’area di lavoro di Campaign è disponibile tramite [Client Console](../architecture/general-architecture.md).

Scopri come installare e configurare la console client di Campaign in [questa sezione](../start/connect.md).

![](assets/home-page.png)

Puoi anche utilizzare un browser web per accedere a Campaign. In questo contesto, sono disponibili solo un sottoinsieme di funzionalità di Campaign. [Ulteriori informazioni](#web-browser)

## Sfogliare l’interfaccia utente{#ui-browse}

Una volta connesso a Campaign, puoi accedere alla home page. Sfoglia i collegamenti per accedere alle funzionalità. Le funzionalità disponibili nell’interfaccia utente dipendono dalle opzioni e dalle autorizzazioni disponibili.

Dalla sezione centrale della home page, utilizza i collegamenti per accedere al materiale di supporto Campaign, alla community e al sito web di supporto.

Utilizza le schede nella sezione superiore per sfogliare le funzionalità chiave di Campaign:

![](assets/overview-home.png)

>[!NOTE]
>
>L’elenco delle funzionalità di base a cui puoi accedere dipende dalle tue autorizzazioni e dall’implementazione.

Per ogni funzionalità, puoi accedere al set di funzioni chiave nel **[!UICONTROL Browsing]** sezione . La **[!UICONTROL More]** link ti consente di accedere a tutti gli altri componenti.

Ad esempio, quando esplori il **[!UICONTROL Profiles and targets]** , puoi accedere agli elenchi dei destinatari, ai servizi di abbonamento, ai flussi di lavoro di targeting esistenti e alle scelte rapide per la creazione di tutti questi componenti.

![](assets/overview-list.png)

Quando selezioni un elemento nella schermata, questo viene caricato in una nuova scheda in modo da poter facilmente sfogliare il contenuto.

![](assets/new-tab.png)

## Creare un elemento {#create-an-element}

Usa le scelte rapide **[!UICONTROL Create]** a sinistra della schermata per aggiungere nuovi elementi. È inoltre possibile utilizzare **[!UICONTROL Create]** per aggiungere nuovi elementi all’elenco corrente.

Ad esempio, nella pagina di consegna, utilizza il **[!UICONTROL Create]** per creare una nuova consegna.

![](assets/new-recipient.png)

## Utilizzare un browser web {#web-browser}

Puoi anche accedere a un sottoinsieme di funzionalità di Campaign tramite un browser web.

L’interfaccia di accesso web è simile a quella della console. Da un browser, puoi utilizzare le stesse funzioni di navigazione e visualizzazione della console, ma puoi eseguire solo un set ridotto di azioni sulle campagne. Ad esempio, puoi visualizzare e annullare le campagne, ma non modificarle.

![](../assets/do-not-localize/glass.png) [Ulteriori informazioni sull’accesso web a Campaign](../start/connect.md#web-access).

## Accedere a Campaign Explorer {#ac-explorer-ui}

Sfoglia Campaign Explorer per accedere a tutte le funzionalità e le impostazioni di Adobe Campaign.

![](assets/explorer.png)

Questa area di lavoro consente di accedere alla struttura ad albero di Esplora risorse per visualizzare tutte le funzionalità e le opzioni.

La sezione a sinistra mostra la struttura ad albero di Campaign Explorer e ti consente di consultare tutti i componenti e le impostazioni dell’istanza, in base alle tue autorizzazioni.

Nella sezione superiore viene visualizzato l&#39;elenco dei record presenti nella cartella corrente. Questi elenchi sono completamente personalizzabili. [Ulteriori informazioni](customize-ui.md)

La sezione inferiore mostra i dettagli del record selezionato.


## Lingue{#languages}

L’interfaccia utente di Campaign v8 è disponibile nelle seguenti lingue:

* Inglese (Regno Unito)
* Inglese (Stati Uniti)
* Francese
* Tedesco
* Giapponese

La lingua viene selezionata durante il processo di installazione.

>[!CAUTION]
>
>Una volta creata l’istanza, non è possibile cambiare la lingua.

La lingua influisce sui formati di data e ora.


Le principali differenze tra inglese americano e inglese britannico sono:

<table> 
 <thead> 
  <tr> 
   <th> Formati<br /> </th> 
   <th> Inglese (Stati Uniti)<br /> </th> 
   <th> Inglese (IT)<br /> </th> 
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
   <td> <p>%2M/%2D/%4Y</p><p><strong>ex: 25/09/2018</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y</p><p><strong>ex: 09/25/2018</strong></p> </td> 
  </tr> 
  <tr> 
   <td> Data breve con ora<br /> </td> 
   <td> <p>%2M/%2D/%4Y %I:%2N:%2S %P</p><p><strong>ex: 25/09/2018 10:47:25</strong></p> </td> 
   <td> <p>%2D/%2M/%4Y %2H:%2N:%2S</p><p><strong>ex: 09/25/2018 22:47:25</strong></p> </td> 
  </tr> 
 </tbody> 
</table>
