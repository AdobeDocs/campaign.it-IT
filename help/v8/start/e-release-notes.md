---
title: Note preliminari sulla versione di Campaign v8
description: Versione preliminare di Campaign v8
feature: Release Notes
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: a45f7b22-44c7-4dad-af0a-ae8f683ae3d9
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '586'
ht-degree: 33%

---

# Note preliminari sulla versione {#e-new-release}

Questa pagina descrive i miglioramenti e le correzioni inclusi nella prossima versione di Campaign v8. Questo contenuto è soggetto a modifiche senza preavviso fino alla data di rilascio. Le note ufficiali sulla versione sono disponibili in questa [pagina](../start/release-notes.md).

## Versione 8.5.1 {#release-8-5}

_30 giugno 2023_

**Novità**

<table> 
<thead>
<tr> 
<th> <strong>Servizio di notifica push avanzato</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td><p>Campaign 8.5.1 introduce il servizio di notifica push più recente nella versione 8, basato su un solido framework basato su una tecnologia all’avanguardia. Questo servizio è progettato per sbloccare nuovi livelli di scalabilità, garantendo che le notifiche possano raggiungere un pubblico più ampio con una perfetta efficienza. Con la nostra infrastruttura migliorata e i nostri processi ottimizzati, puoi aspettarti maggiore scalabilità e affidabilità, consentendoti di interagire e connettersi con gli utenti delle app mobili come mai prima d’ora. Questa funzionalità è disponibile solo per un gruppo selezionato di clienti (disponibilità limitata).</p>
</td> 
</tr> 
</tbody> 
</table>

**Aggiornamenti della compatibilità**

* La versione a 32 bit della console client è ora obsoleta. A partire dalla versione 8.6, la Console client sarà disponibile solo a 64 bit. L’aggiornamento alla versione a 64 bit della console client è semplice. Per ulteriori informazioni su come aggiornare il sistema operativo, consulta questa [nota tecnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/console.html?lang=it).
* Ora puoi collegare la tua istanza di Campaign v8 al database esterno della tua Azure synapse. Questa connessione viene gestita tramite un nuovo account esterno.

**Miglioramenti**

* La velocità effettiva degli SMS è stata notevolmente migliorata implementando una serie di ottimizzazioni, con conseguente miglioramento della velocità e dell’efficienza delle comunicazioni SMS.
* A partire dalla versione 8.5.1 di Campaign, il processo di autenticazione per Campaign v8 è stato migliorato. Per connettersi a Campaign, gli operatori tecnici devono utilizzare Adobe Identity Management System (IMS).
* Ora puoi sfruttare le connessioni di destinazione e origine per sincronizzare gli attributi di profilo, come i dati di rinuncia, tra Adobe Experience Platform e il database di Campaign v8.
* La preparazione della consegna è stata ottimizzata.
* È stata aggiunta una nuova opzione di autenticazione basata su chiave per l’account esterno SFTP, insieme al metodo di autenticazione utente/password esistente. Ora gli utenti possono eseguire l’autenticazione in modo sicuro utilizzando una chiave privata, migliorando la sicurezza e fornendo un meccanismo di autenticazione alternativo per l’accesso SFTP.

**Miglioramenti di sicurezza**

* Non è più possibile creare operatori dalla console client. Ora devi utilizzare l’Admin Console. [Ulteriori informazioni](../start/gs-permissions.md).
* Diversi strumenti di terze parti sono stati aggiornati per ottimizzare la sicurezza.

**Patch**

* È stato risolto un problema che poteva causare la codifica errata in diversi browser dei caratteri speciali nel contenuto HTML di una consegna. (NEO-60081)
* È stato risolto un problema che poteva impedire il salvataggio di un rapporto su una distribuzione Campaign v8 Enterprise (FFDA). (NEO-56836)
* È stato risolto un problema che si verificava durante l’inserimento o l’aggiornamento di dati in uno schema FFDA personalizzato tramite un’attività del flusso di lavoro Update Data (Aggiorna dati). (NEO-54708)
* È stato risolto un problema che impediva al flusso di lavoro di pulizia del database di rimuovere gli indirizzi nella tabella nms:address in FFDA. (NEO-54460)
* È stato risolto un problema relativo al flusso di lavoro di fatturazione che poteva non riuscire con un errore di tipo &quot;Memoria di compilazione esaurita&quot;. (NEO-51137)
* È stato risolto un problema che poteva impedire il corretto funzionamento della decrittografia GPG nell’attività del flusso di lavoro Caricamento dati (file). (NEO-50257)
* È stato risolto un problema che impediva l’utilizzo della funzione `JSPContext.sqlExecWithOneParam`. (NEO-50066)
* È stato risolto un problema che causava errori di consegna durante l’utilizzo di caratteri non stampabili nei campi di personalizzazione. (NEO-48588)
* È stato risolto un problema che poteva causare errori di consegna durante l’inserimento di immagini dinamiche Adobe Target. (NEO-62689)
* È stato risolto un problema che impediva ai browser di aggiungere spazi aggiuntivi durante l’utilizzo di contenuto condizionale in una consegna. (NEO-62132)
* È stato risolto un problema che causava l’apertura di una finestra a comparsa quando si faceva clic su un’immagine nell’editor dei contenuti e-mail. (NEO-60752)
* È stato risolto un problema che poteva causare un errore e impedire lo scorrimento durante la modifica del contenuto di una consegna. (NEO-61364)
