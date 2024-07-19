---
title: Utilizzare Campaign e il CRM
description: Scopri come utilizzare Campaign e il CRM
feature: Salesforce Integration, Microsoft CRM Integration
role: Admin, User
level: Beginner
exl-id: c2d34ee9-4427-48e7-a8cf-0ae02a801d50
source-git-commit: f577ee6d303bab9bb07350b60cf0fa6fc9d3a163
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 20%

---

# Collegare il CRM con Campaign {#gs-crm}

Adobe Campaign fornisce diversi connettori di gestione delle relazioni con i clienti per collegare la piattaforma Adobe Campaign ai sistemi di terze parti. Questi connettori di gestione delle relazioni con i clienti ti consentono di sincronizzare contatti, account, acquisti, ecc. Facilitano l’integrazione dell’applicazione con varie applicazioni di terze parti e aziendali.

Questi connettori consentono un’integrazione rapida e semplice dei dati: Adobe Campaign fornisce un assistente dedicato per la raccolta e la selezione dalle tabelle disponibili nella gestione delle relazioni con i clienti. Ciò garantisce la sincronizzazione bidirezionale per far sì che i dati siano sempre aggiornati in tutti i sistemi.

I principali vantaggi sono:

* Messaggistica coerente tra vendite e marketing: l’integrazione di Adobe Campaign con il CRM offre a entrambi i sistemi l’accesso a informazioni sul cliente e alla cronologia di e-mail marketing, consentendo a tutti i messaggi indirizzati al cliente di condividere lo stesso messaggio coerente.

* Vista olistica di tutti i dati cliente e potenziale: integrando Adobe Campaign con il tuo sistema di gestione delle relazioni con i clienti, è possibile condividere e accedere alla cronologia del marketing e-mail su ogni contatto dall’interno del sistema di gestione delle relazioni con i clienti.

* Attiva i dati CRM su qualsiasi canale: con i dati di contatto sincronizzati con Adobe Campaign, le comunicazioni possono essere inviate su qualsiasi canale online o offline con Campaign, incluso mobile push, in-app, e-mail o direct mail.


>[!NOTE]
>
>Questa funzione è disponibile in Adobe Campaign tramite il pacchetto dedicato **Connettori CRM**.

## Sistemi compatibili {#compatible-crm-systems-and-limitations}

Il CRM e le versioni supportate sono descritti in dettaglio nella [Matrice di compatibilità](../start/compatibility-matrix.md) della campagna.

>[!CAUTION]
>
> I connettori CRM per Campaign funzionano solo con un URL protetto (https).

## Passaggi di implementazione {#crm-implementation-steps}

Scopri la procedura dettagliata per connettere Campaign e Microsoft Dynamics in [questa pagina](ac-ms-dyn.md).

Scopri la procedura dettagliata per connettere Campaign e Salesforce.com in [questa pagina](ac-sfdc.md).

La sincronizzazione dei dati tra Adobe Campaign e il sistema CRM viene eseguita tramite un’attività del flusso di lavoro dedicata. Crea i flussi di lavoro per automatizzare la sincronizzazione tra Campaign e il tuo sistema CRM. Puoi creare un flusso di lavoro che importa i contatti tramite Microsoft Dynamics, li sincronizza con i dati esistenti di Adobe Campaign, elimina i contatti duplicati e quindi aggiorna il database di Adobe Campaign. Per ulteriori informazioni, consulta [questa pagina](crm-data-sync.md).
