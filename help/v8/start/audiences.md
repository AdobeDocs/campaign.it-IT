---
product: Adobe Campaign
title: Introduzione ai tipi di pubblico
description: Introduzione ai tipi di pubblico
feature: Tipi di pubblico
role: Data Engineer
level: Beginner
exl-id: 07baa759-fb0b-4eba-bf8b-ec6cf21df7f8
source-git-commit: 5363950db5092bc7e0a72a0823db1132a17dda33
workflow-type: tm+mt
source-wordcount: '742'
ht-degree: 21%

---

# Introduzione ai tipi di pubblico{#gs-ac-audiences}

## Utilizzare i profili{#gs-ac-profiles}

I profili sono contatti memorizzati nel database di Campaign, inclusi clienti, abbonati e potenziali clienti. Esistono molti possibili meccanismi per l’acquisizione di profili e la creazione di questo database: raccolta on-line tramite moduli web, importazione manuale o automatica di file di testo, replica con database aziendali o altri sistemi di informazioni. Con Adobe Campaign, puoi incorporare la cronologia di marketing, le informazioni di acquisto, le preferenze, i dati CRM ed eventuali dati PI rilevanti in una vista consolidata per analizzare e intraprendere azioni. I profili contengono tutte le informazioni necessarie per il targeting, la qualifica e il tracciamento dei singoli utenti.

Un profilo è un record nella tabella **nmsRecipient** o in una tabella esterna che memorizza tutti gli attributi del profilo, come nome, cognome, indirizzo e-mail, un ID cookie, ID cliente, identificatore mobile o altre informazioni pertinenti a un particolare canale. Altre tabelle collegate alla tabella dei destinatari contengono dati relativi al profilo, ad esempio la tabella dei registri di consegna che contiene i record di tutte le consegne inviate ai destinatari. Ulteriori informazioni sui profili incorporati e sulle tabelle dei destinatari in [questa sezione](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign, **destinatari** sono i profili predefiniti target per l’invio di consegne (e-mail, SMS, ecc.). I dati dei destinatari memorizzati nel database ti consentono di filtrare il target che riceverà una determinata consegna e di aggiungere dati di personalizzazione nel contenuto della consegna. Nel database sono presenti altri tipi di profili. Essi sono progettati per diversi utilizzi. Ad esempio, i profili di seed vengono creati per testare le consegne prima che vengano inviate al target finale.

I profili possono essere raggruppati in elenchi o raccolti eseguendo una query sul database.


Per compilare Campaign con i dati di profilo, puoi:

* [importare ](import.md) file di dati da un’origine dati esterna, ad esempio un sistema CRM
* [creare ](../dev/webapps.md) moduli web per consentire ai clienti di inserire le proprie informazioni e creare il proprio profilo
* [mappatura su un ](../connect/fda.md) database esterno in cui vengono memorizzati i profili
* immetti i profili manualmente utilizzando la console Client , come segue:

![](assets/create-profile.png)


[!DNL :arrow_upper_right:] Scopri come gestire i profili nella documentazione di  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/about-profiles.html).


## Privacy e consenso

Adobe Campaign è un potente strumento per la raccolta e l’elaborazione di un grande volume di dati, inclusi dati personali e sensibili.  Adobe Campaign ti consente di raccogliere dati, incluse informazioni personali e riservate. È pertanto essenziale ricevere e monitorare il consenso dei destinatari.

[!DNL :arrow_upper_right:] Scopri come gestire la privacy e il consenso nella documentazione di  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-and-recommendations.html).

## Creare elenchi

Un elenco è un set statico di profili che possono essere oggetto di targeting nelle azioni di consegna o aggiornati durante le operazioni di importazione o l’esecuzione di un flusso di lavoro. Ad esempio, una popolazione estratta dal database tramite una query può fornire un elenco.

[!DNL :arrow_upper_right:] Scopri come creare e gestire gli elenchi nella documentazione di  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/profile-management/creating-and-managing-lists.html).

## Eseguire una query sul database

Utilizza l’attività **Query** in un flusso di lavoro per eseguire query sul database, segmentare i dati e creare tipi di pubblico complessi.

[!DNL :arrow_upper_right:] Ulteriori informazioni sulle query Campaign nella documentazione di  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/targeting-data.html).

[!DNL :arrow_upper_right:] Tutte le attività di targeting sono elencate nella documentazione di  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/targeting-activities/about-targeting-activities.html)

## Creare un pubblico in un flusso di lavoro

Il targeting può essere creato tramite una combinazione di query in una sequenza grafica in un flusso di lavoro. Puoi creare un pubblico di destinazione in base alle tue esigenze. Per visualizzare l’editor del flusso di lavoro, fai clic sulla scheda **[!UICONTROL Targeting and workflows]** nel dashboard della campagna.

[!DNL :arrow_upper_right:] Scopri come creare un pubblico in un flusso di lavoro della campagna nella documentazione di  [Adobe Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html?lang=en#building-the-main-target-in-a-workflow)


## Profili attivi{#active-profiles}

In base al contratto, a ciascuna istanza di Campaign viene fornito un numero specifico di profili attivi conteggiati a scopo di fatturazione. Per informazioni sul numero di profili attivi acquistati, fai riferimento al contratto più recente.

**** Profiltra significa una registrazione di informazioni (ad esempio: un record nella tabella  [Destinatario ](../dev/datamodel.md) o una tabella esterna contenente un ID cookie, un ID cliente, un identificatore mobile o altre informazioni rilevanti per un particolare canale) che rappresenta un cliente finale, potenziale o lead. I profili sono considerati attivi se sono stati targetizzati o se sono stati comunicati negli ultimi 12 mesi tramite qualsiasi canale.

<!--
You can monitor the number of active profiles used on your instances directly from Campaign Control Panel. 

[!DNL :arrow_upper_right:] For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
-->

**Argomenti correlati**

[!DNL :arrow_upper_right:] [Progettazione ed esecuzione di un flusso di lavoro specifico per la campagna](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/building-a-workflow.html)

[!DNL :arrow_upper_right:] [Scopri come selezionare il pubblico di una campagna](https://experienceleague.adobe.com/docs/campaign-classic/using/orchestrating-campaigns/orchestrate-campaigns/marketing-campaign-target.html)

[!DNL :arrow_upper_right:] [Introduzione ai flussi di lavoro](https://experienceleague.adobe.com/docs/campaign-classic/using/automating-with-workflows/introduction/about-workflows.html)
