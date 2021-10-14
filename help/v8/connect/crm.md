---
title: Utilizzare Campaign e il CRM
description: Scopri come lavorare con Campaign e il tuo CRM
feature: Overview
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 63b53fb6a7c6ecbfc981c93a723b6758b5736acf
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 25%

---

# Connetti il tuo CRM con Campaign {#gs-crm}

Adobe Campaign fornisce diversi connettori di gestione delle relazioni con i clienti per collegare la piattaforma Adobe Campaign ai sistemi di terze parti. Questi connettori di gestione delle relazioni con i clienti ti consentono di sincronizzare contatti, account, acquisti, ecc. Facilitano l’integrazione dell’applicazione con varie applicazioni di terze parti e aziendali.

Questi connettori consentono un’integrazione rapida e semplice dei dati: Adobe Campaign fornisce un assistente dedicato per la raccolta e la selezione dalle tabelle disponibili nel CRM. Ciò garantisce la sincronizzazione bidirezionale per far sì che i dati siano sempre aggiornati in tutti i sistemi.

>[!NOTE]
>
>Questa funzione è disponibile in Adobe Campaign tramite il pacchetto dedicato **Connettori di gestione delle relazioni con i clienti**.

## Sistemi compatibili {#compatible-crm-systems-and-limitations}

Le versioni e i sistemi di gestione delle relazioni con i clienti supportati sono descritti in dettaglio in Campaign [Matrice di compatibilità](../start/compatibility-matrix.md).

![](../assets/do-not-localize/speech.png)  I connettori di gestione delle relazioni con i clienti funzionano solo con un URL sicuro (https).

## Passaggi di implementazione {#crm-implementation-steps}

![](../assets/do-not-localize/book.png) Scopri la procedura dettagliata per collegare Campaign e Microsoft Dynamics nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-ms-dynamics.html?lang=en#microsoft-dynamics-implementation-steps)

![](../assets/do-not-localize/book.png) Scopri la procedura dettagliata per collegare Campaign e Salesforce nella documentazione di  [Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-sfdc.html?lang=en#getting-started)


La sincronizzazione dei dati tra Adobe Campaign e il CRM viene eseguita tramite un’attività di flusso di lavoro dedicata. Crea i tuoi flussi di lavoro per automatizzare la sincronizzazione tra Campaign e il tuo CRM. Puoi creare un flusso di lavoro che importa i contatti tramite Microsoft Dynamics, sincronizzarli con i dati esistenti di Adobe Campaign, eliminare i contatti duplicati e quindi aggiornare il database Adobe Campaign.

![](../assets/do-not-localize/book.png)[ Ulteriori informazioni sono disponibili nella documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/connectors/crm-connectors/crm-data-sync.html?lang=en#getting-started)
