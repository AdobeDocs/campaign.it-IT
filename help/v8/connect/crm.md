---
solution: Campaign v8
product: Adobe Campaign
title: Utilizzare Campaign e il CRM
description: 'Scopri come lavorare con Campaign e il tuo CRM '
feature: Panoramica
role: Data Engineer
level: Beginner
source-git-commit: ab7e458db5ad5696d144c17f6e89e4437a476d11
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 22%

---

# Connetti il tuo CRM con Campaign {#gs-crm}

Adobe Campaign fornisce diversi connettori di gestione delle relazioni con i clienti per collegare la piattaforma Adobe Campaign ai sistemi di terze parti. Questi connettori di gestione delle relazioni con i clienti ti consentono di sincronizzare contatti, account, acquisti, ecc. Facilitano l’integrazione dell’applicazione con varie applicazioni di terze parti e aziendali.

Questi connettori consentono un’integrazione rapida e semplice dei dati: Adobe Campaign fornisce un assistente dedicato per la raccolta e la selezione dalle tabelle disponibili nel CRM. Ciò garantisce la sincronizzazione bidirezionale per far sì che i dati siano sempre aggiornati in tutti i sistemi.

>[!NOTE]
>
>Questa funzione è disponibile in Adobe Campaign tramite il pacchetto dedicato **Connettori di gestione delle relazioni con i clienti**.

## Sistemi compatibili {#compatible-crm-systems-and-limitations}

Le versioni e i sistemi di gestione delle relazioni con i clienti supportati sono descritti in dettaglio in Campaign [Matrice di compatibilità](../start/compatibility-matrix.md).

:speech_balloon: I connettori di gestione delle relazioni con i clienti funzionano solo con un URL sicuro (https).

## Passaggi di implementazione {#crm-implementation-steps}

[!DNL :arrow_upper_right:] Scopri la procedura dettagliata per collegare Campaign e Microsoft Dynamics nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)

[!DNL :arrow_upper_right:] Scopri la procedura dettagliata per collegare Campaign e Salesforce nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


La sincronizzazione dei dati tra Adobe Campaign e il CRM viene eseguita tramite un’attività di flusso di lavoro dedicata. Crea i tuoi flussi di lavoro per automatizzare la sincronizzazione tra Campaign e il tuo CRM. È possibile creare un flusso di lavoro che importa i contatti tramite Microsoft Dynamics, li sincronizza con i dati esistenti di Adobe Campaign, elimina i contatti duplicati e quindi aggiorna il database di Adobe Campaign.

[!DNL :arrow_upper_right:] Ulteriori informazioni nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)

