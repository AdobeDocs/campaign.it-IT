---
title: 'Introduzione al modello dati di Campaign '
description: 'Introduzione al modello dati di Campaign '
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: fbec41a722f71ad91260f1571f6a48383e99b782
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 4%

---

# Introduzione al modello dati di Campaign {#gs-ac-datamodel}

Adobe Campaign viene fornito con un modello dati predefinito. Questa sezione fornisce alcuni dettagli sulle tabelle integrate del modello dati Adobe Campaign e sulla loro interazione. Adobe Campaign si basa su un database Cloud contenente tabelle collegate tra loro.

La struttura di base del modello dati Adobe Campaign può essere descritta come segue:

* **Tabella destinatari**: Il modello dati si basa su una tabella principale che per impostazione predefinita è la tabella Destinatario (nmsRecipient). In questa tabella vengono memorizzati tutti i profili di marketing.

   ![](../assets/do-not-localize/glass.png) Per ulteriori informazioni sulla tabella Destinatario, consulta [questa sezione](#ootb-profiles).

* **Tabella di consegna**: Il modello dati include anche una parte dedicata all’archiviazione di tutte le attività di marketing. Di solito si tratta della tabella Consegna (NmsDelivery). Ogni record in questa tabella rappresenta un&#39;azione di consegna o un modello di consegna. Contiene tutti i parametri necessari per eseguire consegne quali target, contenuto e così via.

* **Tabelle dei registri**: Queste tabelle memorizzano tutti i registri associati all’esecuzione delle campagne.

   I registri di consegna sono tutti i messaggi inviati a destinatari o dispositivi su tutti i canali. La tabella dei registri di consegna principale (NmsBroadLogRcp) contiene i registri di consegna per tutti i destinatari.
La tabella dei registri di tracciamento principale (NmsTrackingLogRcp) memorizza i registri di tracciamento per tutti i destinatari. I registri di tracciamento si riferiscono alle reazioni dei destinatari, ad esempio aperture e clic delle e-mail. Ogni reazione corrisponde a un registro di tracciamento.
I registri di consegna e di tracciamento vengono eliminati dopo un certo periodo, che viene specificato in Adobe Campaign e può essere modificato. Pertanto, si raccomanda vivamente di esportare i registri su base regolare.

* **Tabelle tecniche**: Raccogliere i dati tecnici utilizzati per il processo applicativo, inclusi gli operatori e i diritti utente (xtkGroup), le cartelle (XtkFolder).

>[!NOTE]
>
>Per accedere alla descrizione di ciascuna tabella, vai a Amministratore > Configurazione > Schemi di dati, seleziona una risorsa dall’elenco e fai clic sul pulsante **Documentazione** scheda .

Quando inizi con Adobe Campaign, devi valutare il modello dati predefinito per verificare quale tabella è la più adatta per memorizzare i dati di marketing.

Puoi utilizzare la tabella Destinatario predefinita con i campi predefiniti, come descritto in [questa sezione](#ootb-profiles). Se necessario, puoi estenderlo con due meccanismi:

* [Estendere una tabella esistente](extend-schema.md) con nuovi campi. Ad esempio, puoi aggiungere un nuovo campo &quot;Fedeltà&quot; alla tabella Destinatario.
* [Creare una nuova tabella](create-schema.md), ad esempio una tabella &quot;Acquisto&quot; in cui sono elencati tutti gli acquisti effettuati da ciascun profilo del database e che sono collegati alla tabella Destinatario.

![](../assets/do-not-localize/glass.png) Scopri le best practice per lavorare con il modello dati di Campaign in [questa sezione](datamodel-best-practices.md).

## Tabella dei profili integrata {#ootb-profiles}

La tabella dei destinatari incorporata (nmsrecipient) in Adobe Campaign fornisce un buon punto di partenza per la creazione del modello dati. Dispone di una serie di campi predefiniti e di collegamenti alle tabelle che possono essere facilmente estesi. Questa funzione è particolarmente utile quando esegui principalmente il targeting dei destinatari, perché si adatta a un semplice modello dati incentrato sui destinatari.

I vantaggi dell’utilizzo della tabella dei destinatari standard sono i seguenti:

* Utilizzo di funzionalità chiave come abbonamenti, elenchi di seed e altro ancora
* Fornire un database di marketing con un modello dati incentrato sui destinatari
* Implementazione più rapida
* Manutenzione semplice grazie al supporto e ai partner

È possibile estendere la tabella dei destinatari, ma non ridurre il numero di campi o collegamenti presenti nella tabella.

![](../assets/do-not-localize/glass.png) Scopri come estendere uno schema esistente in [questa sezione](extend-schema.md).

![](../assets/do-not-localize/book.png) Scopri esempi di estensioni integrate della tabella dei destinatari in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=en#extending-a-table){target=&quot;_blank&quot;}

Puoi anche utilizzare una tabella dei destinatari diversa per adattarla meglio ai requisiti aziendali o funzionali. Questo metodo viene fornito con limitazioni e viene descritto in [questa sezione](custom-recipient.md).

## Tabelle di Campaign e database Cloud

Per una migliore comprensione della gestione delle tabelle in Campaign v8, tieni presente che, nel contesto di un [Distribuzione aziendale (FFDA)](../architecture/enterprise-deployment.md), le tabelle vengono replicate tra Campaign e il relativo database Snowflake Cloud.

![](../assets/do-not-localize/glass.png) Ulteriori informazioni sulla strategia e i meccanismi di replica in [questa sezione](../architecture/replication.md).

**Argomenti correlati**

![](../assets/do-not-localize/glass.png) Scopri come importare profili in [questa sezione](../start/import.md)
![](../assets/do-not-localize/glass.png) Ulteriori informazioni sui tipi di pubblico di Campaign in [questa sezione](../start/audiences.md)
