---
title: Creare filtri in Adobe Campaign
description: Scopri come filtrare i dati e salvare i filtri in Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 873578f6-6af9-4d0c-8df3-cce320fc6a4e
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '1638'
ht-degree: 1%

---

# Creare e gestire i filtri{#create-filters}

Il filtraggio dei dati è il processo di selezione di una parte più piccola del set di dati, solo dei record che soddisfano determinati criteri e di utilizzo di quel sottoinsieme per azioni specifiche (aggiornamenti, creazione di tipi di pubblico) o per l’analisi.

Quando esplori Campaign dal **[!UICONTROL Explorer]**, i dati vengono visualizzati in elenchi. Puoi utilizzare filtri incorporati esistenti per accedere a un sottoinsieme specifico di questi dati: indirizzi messi in quarantena, destinatari non di destinazione, un intervallo di età specifico o una data di creazione specifica, ad esempio.

Puoi anche creare filtri personalizzati, salvarli per un utilizzo futuro o condividerli con altri utenti di Campaign.

La configurazione del filtro consente di selezionare i dati da un elenco **[!UICONTROL dynamically]**: quando i dati vengono modificati, i dati filtrati vengono aggiornati.

>[!NOTE]
>
>Le impostazioni di configurazione dell’interfaccia utente sono definite localmente a livello di dispositivo. A volte può essere necessario pulire questi dati, in particolare se si verificano problemi durante l’aggiornamento dei dati. A questo scopo, utilizza **[!UICONTROL File > Clear the local cache]** menu.

In Adobe Campaign sono disponibili i seguenti tipi di filtro:

## Filtri preimpostati{#predefined-filters}

I filtri predefiniti sono disponibili nella **Filtri** sopra ogni elenco.

Ad esempio, per i profili sono disponibili i seguenti filtri incorporati:

![](assets/built-in-filters.png)

Puoi accedere ai dettagli dei filtri nella **[!UICONTROL Profiles and Targets > Pre-defined filters]** del nodo Explorer.

>[!NOTE]
>
>Per tutti gli altri elenchi di dati, i filtri predefiniti sono memorizzati nella  **[!UICONTROL Administration > Configuration > Predefined filters]** nodo.

Seleziona un filtro per visualizzarne la definizione.

![](assets/predefined-filter-list.png)

Utilizzare l’ultima scheda per visualizzare in anteprima i dati filtrati.

![](assets/built-in-filter-preview.png)


I filtri predefiniti incorporati sono:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>Query</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> Aperto<br /> </td> 
   <td> Seleziona i destinatari che hanno aperto una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperto ma non cliccato<br /> </td> 
   <td> Seleziona i destinatari che hanno aperto una consegna ma che non hanno fatto clic su un collegamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatari inattivi<br /> </td> 
   <td> Seleziona i destinatari che non hanno aperto una consegna in X mesi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ultima attività per tipo di dispositivo<br /> </td> 
   <td> Seleziona i destinatari che hanno fatto clic o aperto la consegna Y utilizzando il dispositivo X negli ultimi giorni Z.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ultima attività per tipo di dispositivo (tracciamento)<br /> </td> 
   <td> Seleziona i destinatari che hanno fatto clic o aperto la consegna Y utilizzando il dispositivo X negli ultimi giorni Z.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatari senza targeting<br /> </td> 
   <td> Seleziona destinatari che non sono mai stati oggetto di targeting tramite il canale Y in X mesi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatari molto attivi<br /> </td> 
   <td> Seleziona i destinatari che hanno fatto clic su in una consegna almeno X volte negli ultimi Y mesi.<br /> </td> 
  </tr> 
  <tr> 
 <td> Indirizzo e-mail Inserita nell'elenco Bloccati<br /> </td> 
    <td> Seleziona i destinatari il cui indirizzo e-mail si trova sul elenco Bloccati.<br/> </td>
  </tr> 
  <tr> 
   <td> Indirizzo e-mail in quarantena<br /> </td> 
   <td> Seleziona i destinatari il cui indirizzo e-mail viene messo in quarantena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Indirizzi e-mail duplicati nella cartella<br /> </td> 
   <td> Seleziona i destinatari il cui indirizzo e-mail è duplicato nella cartella.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nessuna apertura né clic<br /> </td> 
   <td> Seleziona i destinatari che non hanno aperto una consegna o che hanno fatto clic su di essa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuovi destinatari (giorni)<br /> </td> 
   <td> Seleziona i destinatari creati negli ultimi X giorni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuovi destinatari (minuti)<br /> </td> 
   <td> Seleziona i destinatari creati negli ultimi X minuti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuovi destinatari (mesi)<br /> </td> 
   <td> Seleziona i destinatari creati negli ultimi X mesi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per abbonamento<br /> </td> 
   <td> Seleziona i destinatari per abbonamento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Facendo clic su un collegamento specifico<br /> </td> 
   <td> Seleziona i destinatari che hanno fatto clic su un particolare URL in una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per comportamento di consegna post<br /> </td> 
   <td> Seleziona i destinatari in base al loro comportamento dopo la ricezione di una consegna.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per data di creazione<br /> </td> 
   <td> Seleziona i destinatari per data di creazione, in un periodo compreso tra X mesi (data corrente meno n mesi) e Y mesi (data corrente meno n mesi).<br /> </td> 
  </tr> 
  <tr> 
   <td> Per elenco<br /> </td> 
   <td> Seleziona i destinatari per elenco.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per numero di clic<br /> </td> 
   <td> Seleziona i destinatari che hanno fatto clic su una consegna negli ultimi X mesi.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per numero di messaggi ricevuti<br /> </td> 
   <td> Seleziona i destinatari in base al numero di messaggi ricevuti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per numero di aperture<br /> </td> 
   <td> Seleziona i destinatari che hanno aperto tra le consegne X e Y per un periodo di tempo pari a Z.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per nome o e-mail<br /> </td> 
   <td> Seleziona i destinatari in base al loro nome o al loro indirizzo e-mail.<br /> </td> 
  </tr> 
  <tr> 
   <td> Per fascia di età<br /> </td> 
   <td> Seleziona i destinatari in base alla loro età.<br /> </td> 
  </tr> 
 </tbody> 
</table>


### Filtri predefiniti{#default-filters}

I campi sopra ogni elenco consentono di utilizzare **filtro predefinito** per questo elenco. Per l’elenco dei destinatari, puoi filtrare il nome e l’indirizzo e-mail per impostazione predefinita.

![](assets/filter-recipient-name.png)


>[!NOTE]
>
>La **%** sostituisce qualsiasi stringa di caratteri. Ad esempio, immetti `%@gmail.com` nel campo E-mail per visualizzare tutti i profili con un indirizzo Gmail. Invio `%@L` nel campo Cognome per visualizzare tutti i profili con una L nel cognome.

Per modificare il filtro predefinito per un elenco di destinatari, passare alla **[!UICONTROL Profiles and Targets > Predefined filters]** nodo.

Per tutti gli altri tipi di dati, configura il filtro predefinito tramite il **[!UICONTROL Administration > Configuration > Predefined filters]** nodo.

Applica i seguenti passaggi:

1. Seleziona il filtro da utilizzare per impostazione predefinita.
1. Fai clic sul pulsante **[!UICONTROL Parameters]** e seleziona **[!UICONTROL Default filter for the associated document type]**.

   ![](assets/change-default-filter.png)

1. Deseleziona la stessa opzione per il filtro predefinito corrente.
1. Fai clic su **[!UICONTROL Save]** per applicare il filtro.
1. Individua la cartella Destinatario e fai clic sul pulsante **[!UICONTROL Remove this filter]** a destra del filtro corrente: è disponibile il nuovo filtro predefinito.
   ![](assets/updated-default-filter.png)


## Filtri rapidi{#quick-filters}

Utilizzare e combinare **Filtri rapidi** per definire filtri per campi specifici.

Una volta aggiunti, i campi del filtro rapido vengono visualizzati sopra l’elenco di dati, uno dopo l’altro. Possono essere cancellati indipendentemente l&#39;uno dall&#39;altro.

I filtri rapidi sono specifici per ogni operatore e vengono reinizializzati ogni volta che l’operatore cancella la cache della console client.

Se devi riutilizzare un filtro, crea un **filtro avanzato** e salvalo. [Ulteriori informazioni](#advanced-filters).

Per creare una **filtro rapido**, segui i passaggi seguenti:

1. Fai clic con il pulsante destro del mouse sul campo da filtrare e seleziona **[!UICONTROL Filter on this field]**.

   ![](assets/quick-filter-on-this-field.png)

   I campi di filtro predefiniti vengono visualizzati sopra l’elenco.

   ![](assets/quick-filter-above-list.png)

1. Selezionare le opzioni del filtro.
1. Se necessario, utilizza l’icona grigia sul lato destro di un filtro per rimuoverlo.
1. Puoi combinare i filtri per perfezionare il filtro.

   ![](assets/add-filter-above-the-list.png)


Se è necessario filtrare un campo che non è disponibile nel modulo, questo verrà inserito nelle colonne e applicato a tale colonna. Per eseguire questa operazione,

1. Fai clic sul pulsante **[!UICONTROL Configure list]** icona.

   ![](assets/configure-list.png)

1. Seleziona la colonna da visualizzare, ad esempio l’età dei destinatari, e fai clic su **Ok**.

   ![](assets/add-age-column.png)

1. Fai clic con il pulsante destro del mouse sul pulsante **Età** nell’elenco dei destinatari e seleziona **[!UICONTROL Filter on this column]**.

   ![](assets/age-filter-on-this-column.png)

   Puoi quindi selezionare le opzioni di filtro della pagina. Aggiungi un altro filtro sulla pagina per definire un intervallo.

   ![](assets/filter-on-age.png)

## Filtri avanzati{#advanced-filters}

Combinare criteri complessi in **Filtri avanzati**. Utilizza questi filtri per creare una query complessa o una combinazione di query sui dati. Questi filtri possono essere salvati e condivisi con altri utenti di Campaign.

### Creare un filtro avanzato{#create-adv-filters}

Per creare un **filtro avanzato**, fai clic su **[!UICONTROL Filters]** e seleziona **[!UICONTROL Advanced filter...]**.

![](assets/adv-filter.png)

Puoi anche fare clic con il pulsante destro del mouse sull’elenco dei dati e selezionare **[!UICONTROL Advanced filter...]**.

Definisci le condizioni di filtro. Nell’esempio seguente, puoi filtrare i destinatari il cui numero di account non inizia con NL e che vivono a Parigi o Los Angeles.

1. Fai clic sul pulsante **[!UICONTROL Edit expression]** dell&#39;icona **[!UICONTROL Expression]** colonna.

   ![](assets/edit-exp.png)

1. Seleziona il campo su cui applicare il filtro.
1. Seleziona l’operatore da applicare dall’elenco a discesa.

   ![](assets/select-operator.png)

1. Seleziona un valore previsto dal **[!UICONTROL Value]** colonna. Puoi combinare diversi filtri per perfezionare la query. Per aggiungere una condizione di filtro, fai clic su **[!UICONTROL Add]**.

   ![](assets/add-an-exp.png)

   >[!NOTE]
   >
   >È possibile assegnare una gerarchia alle espressioni o modificare l’ordine delle espressioni di query utilizzando le frecce della barra degli strumenti.

1. Sono disponibili tre operatori per combinare le espressioni:  **E**, **Oppure**, **Eccetto**. Fai clic sulla freccia a cui passare **Oppure**.

   ![](assets/select-or-operator.png)

1. Fai clic su **[!UICONTROL Ok]** per creare il filtro e applicarlo all’elenco corrente.

Il filtro applicato viene visualizzato sopra l’elenco.

![](assets/adv-filter-link.png)

Per modificare o modificare questo filtro, fai clic sul relativo collegamento di descrizione in blu, sopra l’elenco.


### Salvare un filtro avanzato{#save-adv-filters}

Puoi salvare un filtro avanzato come  [filtro predefinito](#predefined-filters), in modo da poterlo riutilizzare e condividerlo con gli altri utenti di Campaign.

Per salvare un filtro avanzato, segui i passaggi seguenti:

1. Fai clic sulla descrizione del filtro per modificarlo.
1. Fai clic sul pulsante **[!UICONTROL Save as filter]** nella parte superiore destra della finestra.

   ![](assets/save-as-filter.png)

1. Immetti un nome per questo filtro e salvalo.

   ![](assets/application-filter-save.png)

Il filtro viene aggiunto al [filtri predefiniti](#predefined-filters). Può essere aggiornato da questo nodo.

![](assets/added-to-predefined-filters.png)

>[!NOTE]
>
>È possibile aggiungere una scelta rapida per attivare il filtro dalla tastiera.



Questo filtro è disponibile anche dai filtri predefiniti dell’elenco dei destinatari.

![](assets/access-to-new-predefined-filter.png)



### Utilizzare un filtro per definire un segmento {#filter-as-segment}

Puoi utilizzare e combinare i filtri per creare un segmento di popolazione target.

Una volta salvati, sono disponibili filtri avanzati quando selezioni la popolazione target di un messaggio, nella **[!UICONTROL User filters]** sezione .

![](assets/adv-filter-target-type.png)


>[!NOTE]
>
>Utilizza la **[!UICONTROL Exclude recipients from this segment]** per eseguire il targeting solo dei contatti che non corrispondono ai criteri del filtro.


### Utilizzare le funzioni per creare filtri avanzati{#use-functions-adv-filters}

Per eseguire funzionalità di filtro avanzate, utilizza le funzioni per definire il contenuto del filtro. L’editor di filtri avanzato sfrutta tutte le funzionalità dell’editor delle query di Campaign.

Scopri come creare query avanzate in questi esempi end-to-end:

* Scopri come eseguire il targeting su attributi di destinatario semplici in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/wf-activities/targeting-activities/query.html).
* Scopri come filtrare i destinatari non contattati negli ultimi 7 giorni in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/query-many-to-many-relationship.html).
* Scopri come recuperare l’elenco degli operatori che può essere filtrato da account attivi in [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/designing-queries/create-a-filter.html).
* Scopri come creare un pubblico di e-mail di compleanno in  [questa pagina](https://experienceleague.adobe.com/docs/campaign/automation/workflows/use-cases/deliveries/send-a-birthday-email.html?lang=it).


### Parametri avanzati per i filtri predefiniti {#param-for-data-filters}

Per i filtri predefiniti sono disponibili parametri avanzati. Per accedervi, sfoglia fino al **[!UICONTROL Parameters]** scheda del filtro.

* Per visualizzare il filtro per impostazione predefinita per tutti gli elenchi basati su questo tipo di documento, selezionare il **[!UICONTROL Default filter for the associated document type]** opzione .

   Ad esempio, il **[!UICONTROL By name or login]** filtro applicato agli operatori Questa opzione è selezionata, quindi il filtro viene sempre visualizzato su tutti gli elenchi degli operatori.

* Per rendere un filtro disponibile a tutti gli operatori di Campaign, seleziona la  **[!UICONTROL Filter shared with other operators]** opzione .

* Per definire un modulo per la selezione dei criteri di filtro, selezionare la  **[!UICONTROL Use parameter entry form]** opzione . Il modulo deve essere immesso in formato XML **[!UICONTROL Form]** scheda . Ad esempio, il filtro predefinito incorporato **[!UICONTROL Recipients who have opened]**, disponibile nell’elenco dei destinatari, visualizza un campo filtro che ti consente di selezionare la consegna a cui si applica il filtro.

![](assets/predefined-filters-parameters.png)


* La **[!UICONTROL Advanced parameters]** link ti consente di definire impostazioni aggiuntive.

   * È possibile associare una tabella SQL al filtro per renderla comune a tutti gli editor che condividono la tabella.
   * Per evitare che un utente esegua l’override del filtro, seleziona la **[!UICONTROL Do not restrict the filter]** opzione . Ad esempio, questa opzione è attiva per i filtri &quot;Destinatari di una consegna&quot; e &quot;Destinatari di consegne appartenenti a una cartella&quot; disponibili nella procedura guidata di consegna. Questi filtri non possono essere sovraccaricati.
