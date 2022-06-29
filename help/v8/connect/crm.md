---
title: Utilizzare Campaign e il CRM
description: Scopri come lavorare con Campaign e il tuo CRM
feature: Salesforce Integration, Microsoft Integration
role: Data Engineer
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: 8eb92dd1cacc321fc79ac4480a791690fc18511c
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Connetti il tuo CRM con Campaign {#gs-crm}

Adobe Campaign fornisce diversi connettori di gestione delle relazioni con i clienti per collegare la piattaforma Adobe Campaign ai sistemi di terze parti. Questi connettori di gestione delle relazioni con i clienti ti consentono di sincronizzare contatti, account, acquisti, ecc. Facilitano l’integrazione dell’applicazione con varie applicazioni di terze parti e aziendali.

Questi connettori consentono un’integrazione rapida e semplice dei dati: Adobe Campaign fornisce un assistente dedicato per la raccolta e la selezione dalle tabelle disponibili nel CRM. Ciò garantisce la sincronizzazione bidirezionale per far sì che i dati siano sempre aggiornati in tutti i sistemi.

I vantaggi principali sono:

* Messaggistica coerente tra vendite e marketing: l’integrazione di Adobe Campaign con il CRM offre a entrambi i sistemi l’accesso alle informazioni sui clienti e alla cronologia delle e-mail marketing, consentendo a tutti i messaggi al cliente di condividere gli stessi messaggi coerenti.

* Vista olistica di tutti i dati relativi a potenziali clienti e clienti: integrando Adobe Campaign con il tuo CRM, è possibile condividere e accedere alla cronologia di marketing e-mail su ogni contatto dal sistema CRM.

* Attiva i dati CRM su qualsiasi canale: con i dati di contatto sincronizzati con Adobe Campaign, le comunicazioni possono essere inviate su qualsiasi canale online o offline con Campaign, compresi push mobile, in-app, e-mail o direct mail.


>[!NOTE]
>
>Questa funzione è disponibile in Adobe Campaign tramite **Connettori CRM** pacchetto dedicato.

## Sistemi compatibili {#compatible-crm-systems-and-limitations}

Il CRM e le versioni supportate sono descritti in dettaglio in Campaign [Matrice di compatibilità](../start/compatibility-matrix.md).

>[!CAUTION]
>
> I connettori di gestione delle relazioni con i clienti di Campaign funzionano solo con un URL sicuro (https).

## Passaggi di implementazione {#crm-implementation-steps}

Scopri la procedura dettagliata per collegare Campaign e Microsoft Dynamics in [questa pagina](ac-ms-dyn.md).

Scopri la procedura dettagliata per collegare Campaign e Salesforce.com in [questa pagina](ac-sfdc.md).

La sincronizzazione dei dati tra Adobe Campaign e il CRM viene eseguita tramite un’attività di flusso di lavoro dedicata. Crea i tuoi flussi di lavoro per automatizzare la sincronizzazione tra Campaign e il tuo CRM. È possibile creare un flusso di lavoro che importa i contatti tramite Microsoft Dynamics, li sincronizza con i dati esistenti di Adobe Campaign, elimina i contatti duplicati e quindi aggiorna il database di Adobe Campaign. Per ulteriori informazioni, consulta [questa pagina](crm-data-sync.md).
