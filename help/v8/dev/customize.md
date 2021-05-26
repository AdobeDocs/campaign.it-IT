---
solution: Campaign v8
product: Adobe Campaign
title: Personalizza l’istanza
description: Scopri come personalizzare l’istanza
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: 167730cc3e81ee47f02bcdbc2c39fe793a99c534
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 6%

---

# Personalizza la tua istanza{#gs-ac-custom}

Scopri come **personalizzare l’istanza Campaign**

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

* Tramite l&#39;interfaccia, utilizzando l&#39;assistente **Nuovo campo**

   [!DNL :arrow_upper_right:] Scopri come aggiungere rapidamente un nuovo campo in Campaign nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=en#configuring-campaign-classic)

* Programmaticamente, estendendo lo schema

   [!DNL :bulb:] Scopri come estendere uno schema esistente in  [questa sezione](../dev/extend-schema.md).


Puoi anche creare nuove tabelle nel database Campaign ed estendere il modello dati integrato.

Per aggiungere un tipo completamente nuovo di dati che non esistono preconfigurati in Adobe Campaign (ad esempio, una tabella di contratti), puoi creare direttamente uno schema personalizzato. Per ulteriori informazioni, consulta [questo esempio](../dev/create-schema.md#example--creating-a-contract-table).

**Argomenti correlati**

:[!DNL :arrow_upper_right:]: Esempio di modifica dello schema nella documentazione [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#configuring-campaign-classic)

:[!DNL :arrow_upper_right:]: Caso d’uso: collegare un campo a una tabella di riferimento esistente nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#uc-link)[


## Modificare i moduli di input

I moduli di input per le campagne possono essere adattati alla tua implementazione. È possibile aggiungere o rimuovere campi modulo modificando il contenuto XML.

[!DNL :bulb:] Scopri come modificare un modulo di input esistente o crearne uno nuovo in  [questa sezione](../dev/forms.md).

## Personalizzare le dashboard{#gs-custom-dashboards}

L’interfaccia di Adobe Campaign utilizza molte applicazioni web per accedere, gestire e interagire con destinatari, consegne, campagne, stock, ecc. Vengono visualizzate nell’interfaccia sotto forma di dashboard con una sola pagina.

Le applicazioni web predefinite sono memorizzate nel nodo Amministrazione > Configurazione > Applicazioni web .

:[!DNL :arrow_upper_right:]: Scopri come creare una pagina di panoramica in Campaign nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=en#creating-a-single-page-web-application)


## Personalizzare gli elenchi e creare filtri {#gs-lists-and-filters}

### Accedere ai dati dalle dashboard

Gli elenchi di campagne sono dotati di filtri predefiniti per facilitare la navigazione e la visualizzazione dei dati.

:[!DNL :arrow_upper_right:]: Ulteriori informazioni sulle opzioni di filtro nella documentazione di [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/filtering-options.html?lang=en#about-filtering)


### Accedere ai dati da Esplora risorse

Quando ci si sposta nella struttura di Adobe Campaign Explorer, i dati contenuti nel database vengono visualizzati in elenchi. È possibile filtrare gli elenchi, eseguire ricerche, aggiungere informazioni, filtrare e ordinare i dati.

:[!DNL :arrow_upper_right:]: Scopri come configurare gli elenchi e salvare una configurazione di elenco nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/starting-with-adobe-campaign/campaign-workspace/adobe-campaign-ui-lists.html?lang=en#getting-started)


È possibile applicare un filtro a questi elenchi per visualizzare solo i dati necessari all’operatore. Quindi è possibile eseguire azioni sui dati filtrati. La configurazione del filtro consente di selezionare i dati da un elenco in modo dinamico. Se i dati vengono modificati, i dati filtrati vengono aggiornati.

:[!DNL :arrow_upper_right:]: Scopri come filtrare i dati nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/filtering-data/creating-filters.html?lang=en#typology-of-available-filters)
