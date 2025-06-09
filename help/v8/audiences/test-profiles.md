---
title: Creare profili di test in Campaign
description: Scopri come creare e gestire i profili di test in Adobe Campaign
feature: Audiences, Profiles, Seed Address, Proofs
role: User
level: Beginner
exl-id: 878b5963-100c-4dd7-97a0-c59a62c493b1
source-git-commit: e4f6c70ecdcf7414b5f49a43933cfd1c967a0905
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 2%

---

# Creare e gestire profili di test {#create-test-profiles}

## Che cos&#39;è un indirizzo di seed? {#gs-seeds}

I profili di test vengono creati come indirizzi seed. Vengono utilizzati per eseguire il targeting di destinatari che non corrispondono ai criteri di target definiti. Gli indirizzi seed ti consentono di visualizzare in anteprima e testare la personalizzazione e il rendering prima di inviare la consegna, inviando loro delle bozze.

Gli indirizzi seed presentano i seguenti vantaggi:

* Sostituzione casuale di campi con dati ottenuti dai profili dei destinatari: ciò ti consente di inserire solo l’indirizzo e-mail, ad esempio nella sezione dell’indirizzo di seed, e di consentire a Campaign di compilare automaticamente gli altri campi del profilo. Ulteriori informazioni sono disponibili nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html?lang=en){target="_blank"}.
* Quando si utilizza un flusso di lavoro con funzionalità di gestione dati, i dati aggiuntivi elaborati nelle consegne possono essere inseriti a livello di indirizzo di seed per forzare i valori: in questo modo si evita la sostituzione casuale dei valori.
* Gli indirizzi di seed vengono automaticamente esclusi dai rapporti delle seguenti statistiche di consegna: **[!UICONTROL Clicks]**, **[!UICONTROL Opens]**, **[!UICONTROL Unsubscriptions]**.

Gli indirizzi di seed vengono aggiunti al target delle consegne importando o creando direttamente nella consegna o nella campagna.

>[!NOTE]
>
>Gli indirizzi di seed non vengono creati nella tabella dei destinatari, ma in una tabella separata. Se estendi la tabella dei destinatari con nuovi dati, devi estendere anche la tabella degli indirizzi di seed con gli stessi dati. In caso contrario, i campi estesi non verranno presi in considerazione per gli indirizzi seed.
>
>Un esempio di come estendere la tabella degli indirizzi di seed è presentato nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.

## Creare indirizzi seed

Gli indirizzi di seed non vengono gestiti tramite profili e destinazioni standard, ma in un nodo dedicato di Adobe Campaign Explorer: **[!UICONTROL Resources > Campaign management > Seed addresses]**. Puoi creare sottocartelle per organizzare gli indirizzi di seed.

Adobe Campaign consente inoltre di creare modelli di indirizzi seed importati in consegne o campagne e adattati in base alle esigenze specifiche delle consegne e delle campagne in questione. Consulta [Creare modelli di indirizzi seed](#creating-seed-address-templates).

### Definire gli indirizzi {#defining-addresses}

Per creare indirizzi di seed, effettua le seguenti operazioni:

1. Fare clic sul pulsante **[!UICONTROL New]** sopra l&#39;elenco degli indirizzi di seed.
1. Immettere i dati collegati all&#39;indirizzo nei campi corrispondenti della scheda **[!UICONTROL Recipient]**. I campi disponibili corrispondono ai campi standard nei profili dei destinatari della consegna (nms:tabella dei destinatari): nome, nome, e-mail, ecc.

   >[!NOTE]
   >
   >L’etichetta dell’indirizzo viene automaticamente compilata con il cognome e il nome definiti.
   >
   >Non è necessario immettere tutti i campi di ciascuna scheda durante la creazione di un indirizzo di seed. Gli elementi di personalizzazione mancanti vengono inseriti in modo casuale durante l’analisi della consegna.

1. Nella scheda **[!UICONTROL Address fields]**, immettere i valori da inserire nei log di consegna durante la fase di analisi, nella tabella **[!UICONTROL nms:broadLog]**.

1. Nella scheda **[!UICONTROL Additional data]**, immetti i dati di personalizzazione utilizzati per le consegne create nei flussi di lavoro di gestione dati e a cui desideri assegnare un valore specifico.

   Verificare che siano stati definiti dati di destinazione aggiuntivi con un alias che inizia con &#39;@&#39; nell&#39;attività del flusso di lavoro **[!UICONTROL Enrichment]**. In caso contrario, non potrai utilizzarli correttamente con gli indirizzi seed nell’attività di consegna.

### Creare modelli di indirizzi seed {#creating-seed-address-templates}

Puoi creare modelli di indirizzo che possono essere importati e modificati per ogni consegna. Il processo è lo stesso utilizzato per definire un nuovo indirizzo di seed. L&#39;unica differenza consiste nel fatto che gli indirizzi dei modelli di indirizzi seed devono essere memorizzati in una cartella di tipo &quot;Modello&quot;.

### Indirizzi seed per le consegne di direct mailing {#direct-mail-seed-addresses}

Per [consegne di direct mailing](../send/direct-mail.md), gli indirizzi di seed vengono aggiunti durante l&#39;estrazione e mescolati nel documento di output.

Per le consegne di direct mailing, il formato del file di estrazione deve rispettare le seguenti limitazioni:

* Non deve utilizzare l&#39;opzione **[!UICONTROL Handle groupings (GROUP BY+HAVING)]**.

* Se vengono estratte le raccolte di elementi, questi campi avranno un valore vuoto per gli indirizzi seed, a meno che non sia selezionata l&#39;opzione **[!UICONTROL Single row (expert user)]**.

## Aggiungere indirizzi di seed in una consegna{#seed-addresses-in-a-delivery}

Per aggiungere indirizzi di seed specifici per una consegna, fai clic sul collegamento **[!UICONTROL To]**, quindi seleziona la scheda **[!UICONTROL Seed addresses]**.

Sono disponibili tre modalità di inserimento:

1. Immetti indirizzi seed singoli.  A tale scopo, fare clic sul pulsante **[!UICONTROL Add]** e definire il contenuto dei campi indirizzo. Ripeti per ogni indirizzo.

1. Importa [modelli di indirizzi seed](#creating-seed-address-template) e adattali in base alle tue esigenze. A tale scopo, fare clic sul collegamento **[!UICONTROL Import seed templates...]** e selezionare la cartella contenente i modelli di indirizzo.

   Se necessario, una volta aggiunti, è possibile fare doppio clic su di essi o fare clic sul pulsante **[!UICONTROL Detail...]** per adattare il contenuto di ciascun indirizzo.

1. Creare una condizione per selezionare dinamicamente gli indirizzi di controllo da inserire. A tale scopo, fare clic sul collegamento **[!UICONTROL Edit the dynamic condition...]**, quindi immettere i parametri di selezione dell&#39;indirizzo di seed. Ad esempio, puoi includere tutti gli indirizzi seed contenuti in una cartella specifica o gli indirizzi seed appartenenti a un reparto specifico della tua organizzazione.

   Un esempio è presentato nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/sending-messages/using-seed-addresses/use-case--selecting-seed-addresses-on-criteria.html){target="_blank"}.

Per le consegne, puoi anche personalizzare il modo in cui gli indirizzi vengono inseriti nel file di estrazione. Per impostazione predefinita, vengono inserite nell’ordine di ordinamento del file di output, ma puoi scegliere di inserirle alla fine o all’inizio del file oppure in modo casuale tra i destinatari del target principale.

## Aggiungere indirizzi di seed in una campagna {#seed-addresses-in-a-campaign}

Per aggiungere indirizzi di seed a una destinazione per una campagna, selezionare l&#39;operazione e fare clic sulla scheda **[!UICONTROL Edit]**.

Fare clic sul collegamento **[!UICONTROL Advanced campaign settings...]** e quindi sulla scheda **[!UICONTROL Seed addresses]**. Gli indirizzi di seed inseriti dalla campagna vengono aggiunti al target di ogni consegna nella campagna.

## Indirizzi seed e tabella personalizzata {#using-an-external-recipient-table}

Se la tabella di consegna è esterna, dovrai effettuare configurazioni aggiuntive. Lo schema **[!UICONTROL nms:seedmember]** deve essere esteso. Agli indirizzi seed viene aggiunta una scheda per definire i campi appropriati

In questo caso, per aggiungere indirizzi di seed alla consegna, inserisci i campi appropriati direttamente nella scheda corrispondente o importa i modelli di indirizzo.

<!--The **nms:seedMember** schema extension is [this section](../../configuration/using/seed-addresses.md).-->
