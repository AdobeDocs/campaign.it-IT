---
title: Guida introduttiva a profili e tipi di pubblico in Campaign
description: Scopri come creare e gestire profili e pubblico in Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 43483085-8aa6-47e6-89e7-9211e37beaa4
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 20%

---

# Guida introduttiva a profili e tipi di pubblico in Campaign{#gs-profiles-and-audiences}

I profili sono contatti memorizzati nel database di Campaign, ad esempio clienti, abbonati a un servizio o potenziali clienti. Esistono molti possibili meccanismi per l’acquisizione di profili e la creazione di questo database: raccolta online tramite moduli web, importazione manuale o automatica di file di testo, replica con database aziendali o altri sistemi di informazioni. Con Adobe Campaign, puoi incorporare la cronologia di marketing, le informazioni di acquisto, le preferenze, i dati CRM ed eventuali dati PI rilevanti in una vista consolidata per analizzare e intraprendere azioni. I profili contengono tutte le informazioni necessarie per il targeting, la qualifica e il tracciamento dei singoli utenti.

Un profilo è un record nel **nmsRecipient** tabella o tabella esterna che memorizza tutti gli attributi del profilo, ad esempio nome, cognome, indirizzo e-mail, un ID cookie, ID cliente, identificatore mobile o altre informazioni pertinenti a un particolare canale. Altre tabelle collegate alla tabella dei destinatari contengono dati relativi al profilo, ad esempio la tabella dei registri di consegna che contiene i record di tutte le consegne inviate ai destinatari. Ulteriori informazioni sui profili incorporati e sulle tabelle dei destinatari in [questa sezione](../dev/datamodel.md#ootb-profiles).

In Adobe Campaign, **destinatari** sono i profili predefiniti target per l’invio di consegne (e-mail, SMS, ecc.). I dati dei destinatari memorizzati nel database ti consentono di filtrare il target che riceverà una determinata consegna e di aggiungere dati di personalizzazione nel contenuto della consegna. Nel database sono presenti altri tipi di profili. Essi sono progettati per diversi utilizzi. Ad esempio, i profili di seed vengono creati per testare le consegne prima che vengano inviate al target finale.


Per compilare Adobe Campaign con i dati del profilo, puoi:

* [importare file di dati](../start/import.md) da un’origine dati esterna, ad esempio un sistema CRM
* [creare moduli web](../dev/webapps.md) per consentire ai clienti di inserire le proprie informazioni e creare il proprio profilo
* [mappatura su un database esterno](../connect/fda.md) in cui sono memorizzati i profili
* immetti i profili manualmente nella console Client , come segue:

![](assets/create-profile.png)

<!--You can also select your message audience in an external file: recipients are stored not in the database, but in files. These are known as “external” deliveries. These contacts can be imported or not in Adobe Campaign. [Learn more](external-profiles.md).-->
