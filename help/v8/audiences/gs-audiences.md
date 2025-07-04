---
title: Guida introduttiva a profili e tipi di pubblico in Campaign
description: Scopri come creare e gestire profili e pubblico in Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
version: Campaign v8, Campaign Classic v7
source-git-commit: a2efad26232cd380eea850a589b22b23928253e8
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 20%

---

# Guida introduttiva ai profili e ai tipi di pubblico{#gs-profiles-and-audiences}

I profili sono contatti memorizzati nel database di Campaign, ad esempio clienti, abbonati a un servizio o potenziali clienti. Esistono molti possibili meccanismi per l’acquisizione di profili e la creazione di questo database: raccolta online tramite moduli web, importazione manuale o automatica di file di testo, replica con database aziendali o altri sistemi di informazioni. Con Adobe Campaign, puoi incorporare la cronologia di marketing, le informazioni di acquisto, le preferenze, i dati di gestione delle relazioni con i clienti ed eventuali dati PI rilevanti in una visualizzazione consolidata per analizzare e intraprendere azioni. I profili contengono tutte le informazioni necessarie per il targeting, la qualificazione e il tracciamento dei singoli utenti.



Un profilo è un record nella tabella **nmsRecipient** o in una tabella esterna in cui sono memorizzati tutti gli attributi del profilo, ad esempio nome, cognome, indirizzo e-mail, un ID cookie, un ID cliente, un identificatore mobile o altre informazioni relative a un canale specifico. Altre tabelle collegate alla tabella dei destinatari contengono dati relativi al profilo, ad esempio la tabella dei registri di consegna che contiene i record di tutte le consegne inviate ai destinatari. Ulteriori informazioni sui profili incorporati e sulle tabelle dei destinatari in [questa sezione](../dev/datamodel.md#ootb-profiles).

![](assets/recipients-in-explorer.png)

In Adobe Campaign, **destinatari** sono i profili predefiniti target per l&#39;invio di consegne (e-mail, SMS, ecc.).

I dati dei destinatari memorizzati nel database consentono di filtrare il target che riceverà una determinata consegna e di aggiungere dati di personalizzazione al contenuto della consegna. Nel database sono presenti altri tipi di profili. Essi sono progettati per diversi utilizzi. Ad esempio, i profili di seed vengono creati per testare le consegne prima che vengano inviate al target finale.

Per popolare Adobe Campaign con i dati del profilo, puoi:

* [importa file di dati](../start/import.md) da un&#39;origine dati esterna, ad esempio un sistema CRM o un file flat
* [crea moduli web](../dev/webapps.md) per consentire ai clienti di immettere le proprie informazioni e creare il proprio profilo
* [mappa su un database esterno](../connect/fda.md) in cui sono archiviati i profili
* immetti manualmente i profili nella console client, come segue:

![](assets/create-profile.png)

<!--You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as "external" deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).-->

Una volta importato, puoi creare tipi di pubblico per inviare i messaggi. Scopri come creare tipi di pubblico [in questa sezione](create-audiences.md).