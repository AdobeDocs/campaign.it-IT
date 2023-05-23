---
title: Introduzione al modello dati di Campaign
description: Inizia a usare il modello dati di Campaign e sfrutta i dati provenienti dalle tue origini per migliorare le comunicazioni e gli output di marketing.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: 65f4da979f0c5884797af0c3a835d948672b4a7c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 6%

---

# Introduzione al modello dati di Campaign {#gs-ac-datamodel}

Adobe Campaign viene fornito con un modello dati predefinito. Questa sezione fornisce alcuni dettagli sulle tabelle integrate del modello dati di Adobe Campaign e sulla loro interazione. Adobe Campaign si basa su un database Cloud contenente tabelle collegate tra loro.

La struttura di base del modello dati di Adobe Campaign può essere descritta come segue:

* **Tabella destinatari**: il modello dati si basa su una tabella principale che è per impostazione predefinita la tabella Destinatario (nmsRecipient). Questa tabella memorizza tutti i profili di marketing.

   ![](../assets/do-not-localize/glass.png) Per ulteriori informazioni sulla tabella Destinatario, consulta [questa sezione](#ootb-profiles).

* **Tabella di consegna**: il modello dati include anche una parte dedicata alla memorizzazione di tutte le attività di marketing. Di solito si tratta della tabella Delivery (NmsDelivery). Ogni record di questa tabella rappresenta un’azione di consegna o un modello di consegna. Contiene tutti i parametri necessari per eseguire le consegne come destinazione, contenuto, ecc.

* **Tabelle dei registri**: queste tabelle memorizzano tutti i registri associati all’esecuzione delle campagne.

   I registri di consegna sono tutti messaggi inviati a destinatari o dispositivi su tutti i canali. La tabella principale dei registri di consegna (NmsBroadLogRcp) contiene i registri di consegna per tutti i destinatari.
La tabella principale dei registri di tracciamento (NmsTrackingLogRcp) memorizza i registri di tracciamento per tutti i destinatari. I registri di tracciamento si riferiscono alle reazioni dei destinatari, ad esempio aperture delle e-mail e clic. Ogni reazione corrisponde a un registro di tracciamento.
I registri di consegna e di tracciamento vengono eliminati dopo un determinato periodo di tempo, specificato in Adobe Campaign, che può essere modificato. Pertanto, si consiglia vivamente di esportare i registri su base regolare.

* **Tabelle tecniche**: raccoglie i dati tecnici utilizzati per il processo applicativo, inclusi gli operatori e i diritti utente (xtkGroup) e le cartelle (XtkFolder).

>[!NOTE]
>
>Per accedere alla descrizione di ciascuna tabella, vai a Amministrazione > Configurazione > Schemi di dati, seleziona una risorsa dall’elenco e fai clic su **Documentazione** scheda.

Quando si inizia con Adobe Campaign, è necessario valutare il modello dati predefinito per verificare quale tabella è più adatta per memorizzare i dati di marketing.

È possibile utilizzare la tabella Destinatario predefinita con i campi predefiniti, come descritto in [questa sezione](#ootb-profiles). Se necessario, è possibile estenderlo con due meccanismi:

* [Estendere una tabella esistente](extend-schema.md) con nuovi campi. Ad esempio, puoi aggiungere un nuovo campo &quot;Fedeltà&quot; alla tabella Destinatario.
* [Crea una nuova tabella](create-schema.md), ad esempio una tabella &quot;Purchase&quot; in cui sono elencati tutti gli acquisti effettuati da ciascun profilo del database, quindi collegarla alla tabella Recipient.

![](../assets/do-not-localize/glass.png) Scopri le best practice per l’utilizzo del modello dati di Campaign in [questa sezione](datamodel-best-practices.md).

## Tabella profilo incorporata {#ootb-profiles}

La tabella dei destinatari incorporata (nmsrecipient) in Adobe Campaign fornisce un buon punto di partenza per la creazione del modello di dati. Dispone di una serie di campi predefiniti e collegamenti alle tabelle che possono essere facilmente estesi. Questa funzione è particolarmente utile quando esegui il targeting principalmente dei destinatari, in quanto si adatta a un semplice modello di dati incentrato sul destinatario.

L’utilizzo della tabella dei destinatari standard offre i seguenti vantaggi:

* Utilizzo di funzionalità chiave quali abbonamenti, elenchi di seed e altro ancora
* Fornire a un database di marketing un modello dati incentrato sui destinatari
* Implementazione più rapida
* Manutenzione semplice grazie al supporto e ai partner

È possibile estendere la tabella dei destinatari, ma non ridurre il numero di campi o collegamenti nella tabella.

![](../assets/do-not-localize/glass.png) Scopri come estendere uno schema esistente in [questa sezione](extend-schema.md).

![](../assets/do-not-localize/book.png) Scopri esempi di estensioni della tabella dei destinatari incorporate in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html#extending-a-table){target="_blank"}

È inoltre possibile utilizzare una tabella dei destinatari diversa per soddisfare meglio i requisiti aziendali o funzionali. Questo metodo presenta limitazioni ed è descritto in [questa sezione](custom-recipient.md).

## Tabelle di Campaign e database cloud

Per una migliore comprensione della gestione delle tabelle in Campaign v8, tieni presente che, nel contesto di un’ [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), le tabelle vengono replicate tra Campaign e il relativo database Cloud di Snowflake.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sulla strategia e sui meccanismi di replica in [questa sezione](../architecture/replication.md).

**Argomenti correlati**

![](../assets/do-not-localize/glass.png) Scopri come importare i profili in [questa sezione](../start/import.md)
![](../assets/do-not-localize/glass.png) Ulteriori informazioni sui tipi di pubblico di Campaign in [questa sezione](../start/audiences.md)
