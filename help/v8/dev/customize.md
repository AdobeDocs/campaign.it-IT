---
title: Personalizzare l’istanza
description: Scopri come personalizzare l’istanza
role: Developer
level: Beginner, Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 2ce1ef1e935080a66452c31442f745891b9ab9b3
workflow-type: tm+mt
source-wordcount: '545'
ht-degree: 7%

---

# Personalizzare l’istanza{#gs-ac-custom}

Scopri come **Personalizzare l’istanza Campaign**.

>[!CAUTION]
>
>La personalizzazione Adobe Campaign è riservata solo agli utenti esperti.

## Creazione di nuovi campi di dati e schemi

Adobe Campaign utilizza gli schemi di dati per:

* Definire il modo in cui gli oggetti dati all’interno dell’applicazione sono legati alle tabelle del database sottostanti
* Definire i collegamenti tra i diversi oggetti dati all’interno dell’applicazione Campaign
* Definire e descrivere i singoli campi inclusi in ciascun oggetto

Ad esempio, per aggiungere un campo a una tabella esistente, ad esempio la tabella dei destinatari (nms:recipient), è necessario estendere tale schema.

Sono disponibili due modalità di estensione della tabella:

* Tramite l’interfaccia, utilizzando **Nuovo campo** assistente

   ![](../assets/do-not-localize/book.png) Scopri come aggiungere rapidamente un nuovo campo in Campaign in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic){target="_blank"}

* Programmaticamente, estendendo lo schema

   ![](../assets/do-not-localize/glass.png) Scopri come estendere uno schema esistente in [questa sezione](../dev/extend-schema.md).


Puoi anche creare nuove tabelle nel database Campaign ed estendere il modello dati integrato.

Per aggiungere un tipo completamente nuovo di dati che non esistono preconfigurati in Adobe Campaign (ad esempio, una tabella di contratti), puoi creare direttamente uno schema personalizzato. Per ulteriori informazioni, consulta [questo esempio](../dev/create-schema.md#example--creating-a-contract-table).

**Argomenti correlati**

![](../assets/do-not-localize/book.png) Esempio di modifica dello schema in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic){target="_blank"}

![](../assets/do-not-localize/book.png) Caso d’uso: collegare un campo a una tabella di riferimento esistente in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link){target="_blank"}


## Modificare i moduli di input

I moduli di input per le campagne possono essere adattati alla tua implementazione. È possibile aggiungere o rimuovere campi modulo modificando il contenuto XML.

![](../assets/do-not-localize/glass.png) Scopri come modificare un modulo di input esistente o crearne uno nuovo in [questa sezione](../dev/forms.md).

## Personalizzare le dashboard{#gs-custom-dashboards}

L’interfaccia di Adobe Campaign utilizza molte applicazioni web per accedere, gestire e interagire con destinatari, consegne, campagne, stock, ecc. Vengono visualizzate nell’interfaccia sotto forma di dashboard con una sola pagina.

Le applicazioni web predefinite sono memorizzate nel nodo Amministrazione > Configurazione > Applicazioni web .

![](../assets/do-not-localize/book.png) Scopri come creare una pagina di panoramica in Campaign [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application){target="_blank"}


## Personalizzare gli elenchi e creare filtri {#gs-lists-and-filters}

### Accedere ai dati dalle dashboard

Gli elenchi di campagne sono dotati di filtri predefiniti per facilitare la navigazione e la visualizzazione dei dati.

![](../assets/do-not-localize/book.png) Ulteriori informazioni sulle opzioni di filtro in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering){target="_blank"}


### Accedere ai dati da Esplora risorse

Quando ci si sposta nella struttura di Adobe Campaign Explorer, i dati contenuti nel database vengono visualizzati in elenchi. È possibile filtrare gli elenchi, eseguire ricerche, aggiungere informazioni, filtrare e ordinare i dati.

![](../assets/do-not-localize/book.png) Scopri come configurare gli elenchi e salvare una configurazione di elenco in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started){target="_blank"}


È possibile applicare un filtro a questi elenchi per visualizzare solo i dati necessari all’operatore. Quindi è possibile eseguire azioni sui dati filtrati. La configurazione del filtro consente di selezionare i dati da un elenco in modo dinamico. Se i dati vengono modificati, i dati filtrati vengono aggiornati.

![](../assets/do-not-localize/book.png) Scopri come filtrare i dati in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters){target="_blank"}
