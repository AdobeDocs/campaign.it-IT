---
title: Personalizzare l’istanza
description: Scopri come personalizzare l’istanza
feature: Configuration, Application Settings
role: Developer
level: Intermediate, Experienced
exl-id: 18000763-5923-48bd-b62d-cccd3c11016d
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 1%

---

# Personalizzare l’istanza {#gs-ac-custom}

Scopri come **personalizzare la tua istanza di Campaign**.

>[!CAUTION]
>
>La personalizzazione di Adobe Campaign è riservata esclusivamente agli utenti esperti.

## Creare nuovi campi dati e schemi

Adobe Campaign utilizza gli schemi di dati per:

* Definire il modo in cui gli oggetti dati all&#39;interno dell&#39;applicazione sono legati alle tabelle di database sottostanti
* Definire i collegamenti tra i diversi oggetti dati all’interno dell’applicazione Campaign
* Definire e descrivere i singoli campi inclusi in ciascun oggetto

Ad esempio, per aggiungere un campo a una tabella esistente, ad esempio la tabella dei destinatari (nms:recipient), è necessario estendere tale schema.

Sono disponibili due modalità di estensione della tabella:

* Tramite l&#39;interfaccia, utilizzando l&#39;assistente **Nuovo campo**

  Scopri come aggiungere rapidamente un nuovo campo in Campaign nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/new-field-wizard.html?lang=it#configuring-campaign-classic){target="_blank"}

* A livello di programmazione, estendendo lo schema. Scopri come estendere uno schema esistente in [questa sezione](../dev/extend-schema.md).

Puoi anche creare nuove tabelle nel database di Campaign ed estendere il modello dati integrato.

Per aggiungere un tipo di dati completamente nuovo che non esiste come standard in Adobe Campaign (ad esempio, una tabella di contratti) puoi creare direttamente uno schema personalizzato. Per ulteriori informazioni, consulta [questo esempio](../dev/create-schema.md#example--creating-a-contract-table).

**Argomenti correlati**

Esempio di modifica dello schema nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=it#configuring-campaign-classic){target="_blank"}

Caso d&#39;uso: collegare un campo a una tabella di riferimento esistente nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=it#uc-link){target="_blank"}


## Modificare i moduli di input

I moduli di input delle campagne possono essere adattati alla tua implementazione. È possibile aggiungere o rimuovere campi modulo modificando il contenuto XML.

Scopri come modificare un modulo di input esistente o crearne uno nuovo in [questa sezione](../dev/forms.md).

## Personalizzare le dashboard{#gs-custom-dashboards}

L’interfaccia di Adobe Campaign utilizza molte applicazioni web per accedere, gestire e interagire con destinatari, consegne, campagne, scorte e così via. Vengono visualizzati nell’interfaccia sotto forma di dashboard con una sola pagina.

Le applicazioni Web incorporate sono memorizzate nella cartella **Amministrazione > Configurazione > Applicazioni Web** di Explorer.

Scopri come creare una pagina di panoramica in Campaign nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/designing-content/web-applications/use-cases--creating-overviews.html?lang=it#creating-a-single-page-web-application){target="_blank"}


## Personalizzare gli elenchi e creare i filtri {#gs-lists-and-filters}

Gli elenchi delle campagne sono dotati di filtri predefiniti per facilitare la navigazione e la visualizzazione dei dati.

Quando ci si sposta nella struttura di Adobe Campaign Explorer, i dati contenuti nel database vengono visualizzati in elenchi. Puoi filtrare questi elenchi, eseguire ricerche, aggiungere informazioni, filtrare e ordinare i dati.

Scopri come configurare gli elenchi e salvare una configurazione di elenchi in [questa pagina](../start/campaign-ui.md).

Puoi applicare un filtro a questi elenchi per visualizzare solo i dati necessari all’operatore. Quindi è possibile eseguire le azioni sui dati filtrati. La configurazione del filtro consente di selezionare i dati da un elenco in modo dinamico. Se i dati vengono modificati, i dati filtrati vengono aggiornati.

Ulteriori informazioni sulle opzioni di filtro in [questa pagina](../audiences/create-filters.md).
