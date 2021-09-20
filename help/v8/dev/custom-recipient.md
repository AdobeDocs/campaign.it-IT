---
title: Modificare la tabella dei destinatari predefinita
description: Scopri come utilizzare una tabella dei destinatari personalizzata
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 3205b492552afc0aa0514f8995f508439a7a9a0b
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Utilizzare una tabella dei destinatari personalizzata{#gs-ac-custom-recipient}

Adobe Campaign viene fornito con una tabella di profilo integrata: **nmsRecipient**. Questa tabella presenta una serie di campi e tabelle predefiniti che possono essere facilmente estesi. Ulteriori informazioni su questa tabella in [questa pagina](datamodel.md#ootb-profiles).

L’estensione di tabella incorporata offre flessibilità, ma non consente di rimuovere alcuni campi o collegamenti non utilizzati. Di conseguenza, l’utilizzo di una tabella dei destinatari personalizzata può essere una buona opzione quando il modello dati si differenzia drasticamente dalla struttura della tabella dei destinatari integrata in Campaign o se si dispone di un numero elevato di profili.  Tuttavia, questo metodo richiede alcune precauzioni al momento dell&#39;attuazione.

Questa funzionalità consente ad Adobe Campaign di elaborare i dati da un database esterno: questi dati verranno utilizzati come un set di profili per le consegne. L’implementazione di questo processo comporta limitazioni quali:

* Nessun flusso di aggiornamento da e per il database di Campaign Cloud: i dati di questa tabella possono essere aggiornati direttamente tramite il motore di database che li ospita.
* I processi che operano sul database esistente devono essere stabili.
* Utilizzo di un database di profilo con una struttura non standard: possibilità di consegnare a profili salvati in varie tabelle con diverse strutture, utilizzando un’unica istanza.

Questa sezione descrive i punti chiave per mappare le tabelle esistenti in Adobe Campaign e le impostazioni di configurazione da applicare per eseguire consegne in base a qualsiasi tabella. Descrive inoltre come progettare interfacce di query per gli utenti finali.

>[!CAUTION]
>
>La personalizzazione Adobe Campaign è riservata solo agli utenti esperti. Richiede esperienza nella struttura del modulo di input e dello schema.

