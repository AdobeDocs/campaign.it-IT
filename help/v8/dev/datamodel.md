---
title: Introduzione al modello dati di Campaign
description: Inizia a usare il modello dati di Campaign e sfrutta i dati provenienti dalle tue origini per migliorare le comunicazioni e gli output di marketing.
feature: Data Model
role: Data Engineer
level: Beginner
exl-id: 200b60f1-04ae-4c3e-892f-3dd2bd22b896
source-git-commit: be085eaf7e1e7ded5986fdb6100045daba4d88fe
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 5%

---

# Introduzione al modello dati di Campaign {#gs-ac-datamodel}

Adobe Campaign viene fornito con un modello dati predefinito. Questa sezione fornisce alcuni dettagli sulle tabelle integrate del modello dati di Adobe Campaign e sulla loro interazione. Adobe Campaign si basa su un database Cloud contenente tabelle collegate tra loro.

La struttura di base del modello dati di Adobe Campaign può essere descritta come segue:

* **Tabella destinatari**: il modello dati si basa su una tabella principale che per impostazione predefinita è la tabella destinatari (**nmsRecipient**). Questa tabella memorizza tutti i profili di marketing. Ulteriori informazioni sulla tabella dei destinatari in [questa sezione](#ootb-profiles).

* **Tabella di consegna**: in questa tabella viene memorizzato un record per azione di consegna. Di solito si tratta della tabella di consegna (**NmsDelivery**). in questa tabella rappresenta un’azione di consegna o un modello di consegna. Contiene tutti i parametri necessari per eseguire le consegne come destinazione, contenuto, ecc. Ogni record viene aggiornato diverse volte per riflettere l’avanzamento della consegna

* **Tabelle dei registri**: queste tabelle memorizzano tutti i registri associati all&#39;esecuzione delle campagne.

   * I registri di consegna sono tutti messaggi inviati a destinatari o dispositivi su tutti i canali. La tabella principale dei registri di consegna (**NmsBroadLogRcp**) contiene i registri di consegna per tutti i destinatari.
   * La tabella **nmsBroadlog** è la più grande del sistema. Memorizza un record per messaggio inviato e questi record vengono inseriti, aggiornati per tenere traccia dello stato di consegna ed eliminati quando la cronologia viene eliminata.
   * La tabella principale dei registri di tracciamento (**NmsTrackingLogRcp**) memorizza i registri di tracciamento per tutti i destinatari. I registri di tracciamento si riferiscono alle reazioni dei destinatari, ad esempio aperture delle e-mail e clic. Ogni reazione corrisponde a un registro di tracciamento.

  I registri di consegna e di tracciamento vengono eliminati dopo un determinato periodo di tempo, specificato in Adobe Campaign, che può essere modificato. Pertanto, si consiglia vivamente di esportare i registri su base regolare.

* **Tabelle tecniche**: raccogliere i dati tecnici utilizzati per il processo applicativo, inclusi gli operatori e i diritti utente (**xtkGroup**), le sessioni utente (**xtkSessionInfo**), le cartelle nella struttura dell&#39;elenco delle cartelle (**XtkFolder**), i flussi di lavoro (**xtkWorkflow**) e altro ancora.

>[!NOTE]
>
>Per accedere alla descrizione di ogni tabella, passa a **Amministrazione > Configurazione > Schemi dati**, seleziona una risorsa dall&#39;elenco e fai clic sulla scheda **Documentazione**.

Quando si inizia con Adobe Campaign, è necessario valutare il modello dati predefinito per verificare quale tabella è più adatta per memorizzare i dati di marketing.

È possibile utilizzare la tabella Destinatario predefinita con i campi predefiniti, come descritto in [questa sezione](#ootb-profiles). Se necessario, è possibile estenderlo con due meccanismi:

* [Estendere una tabella esistente](extend-schema.md) con nuovi campi. Ad esempio, puoi aggiungere un nuovo campo &quot;Fedeltà&quot; alla tabella Destinatario.
* [Creare una nuova tabella](create-schema.md), ad esempio una tabella &quot;Acquisti&quot; in cui sono elencati tutti gli acquisti effettuati da ciascun profilo del database e collegarla alla tabella Destinatario.

Scopri le best practice per l&#39;utilizzo del modello dati di Campaign in [questa sezione](datamodel-best-practices.md).

## Tabella profilo incorporata {#ootb-profiles}

La tabella dei destinatari incorporata (nmsrecipient) in Adobe Campaign fornisce un buon punto di partenza per la creazione del modello di dati. Dispone di una serie di campi predefiniti e collegamenti alle tabelle che possono essere facilmente estesi. Questa funzione è particolarmente utile quando esegui il targeting principalmente dei destinatari, in quanto si adatta a un semplice modello di dati incentrato sul destinatario.

L’utilizzo della tabella dei destinatari standard offre i seguenti vantaggi:

* Utilizzo di funzionalità chiave quali abbonamenti, elenchi di seed e altro ancora
* Fornire a un database di marketing un modello dati incentrato sui destinatari
* Implementazione più rapida
* Manutenzione semplice grazie al supporto e ai partner

È possibile estendere la tabella dei destinatari, ma non ridurre il numero di campi o collegamenti nella tabella.

Scopri come estendere uno schema esistente in [questa sezione](extend-schema.md).

Scopri alcuni esempi di estensioni della tabella dei destinatari incorporate nella documentazione di [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/configuring-campaign-classic/editing-schemas/examples-of-schemas-edition.html?lang=it#extending-a-table){target="_blank"}

È inoltre possibile utilizzare una tabella dei destinatari diversa per soddisfare meglio i requisiti aziendali o funzionali. Questo metodo presenta limitazioni ed è descritto in [questa sezione](custom-recipient.md).

## Tabelle di Campaign e database cloud

Per comprendere meglio la gestione delle tabelle in Campaign v8, tieni presente che, nel contesto di una distribuzione [Enterprise (FFDA)](../architecture/enterprise-deployment.md), le tabelle vengono replicate tra Campaign e il relativo database Snowflake Cloud.

Ulteriori informazioni sulla strategia e sui meccanismi di replica sono disponibili in [questa sezione](../architecture/replication.md).

**Argomenti correlati**

Scopri come importare i profili in [questa sezione](../start/import.md)
Ulteriori informazioni sui tipi di pubblico di Campaign in [questa sezione](../start/audiences.md)
