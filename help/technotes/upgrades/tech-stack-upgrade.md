---
product: campaign
title: Nota tecnica - Aggiornamenti dei sistemi Adobe Campaign
description: Aggiornamento del sistema Adobe Campaign
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: f1e963a880e8499dbbb16c44831a4ce1b537601f
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 11%

---

# Aggiornamenti dell’ambiente Adobe Campaign 2023 {#ac-system-upgrade}

L’infrastruttura di Campaign si basa su sistemi di terze parti che devono essere regolarmente aggiornati con le versioni e le correzioni più recenti. Questi aggiornamenti sono obbligatori per garantire la continuità del servizio e la protezione degli ambienti Campaign dai rischi di sicurezza. Inoltre, è necessario un aggiornamento di Campaign per garantire la compatibilità con modifiche al sistema di terze parti.

As a **Cliente Cloud Service gestiti**, Adobe fornisce informazioni su questi aggiornamenti quando sono necessari. Gli ambienti dovranno essere aggiornati in conformità con le raccomandazioni per garantire la conformità.

Per motivi di sicurezza, l’Adobe deve [installare la build Campaign più recente](#ac-upgrade), quindi aggiornare il [sistema operativo](#os-upgrade) e/o [Sistema di gestione del database relazionale (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>Per qualsiasi domanda su queste modifiche, contatta [Adobe Customer Care](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>

## Aggiornamento della build di Campaign {#ac-upgrade}

**Sei interessato da questo problema?**

Se è interessato da [aggiornamento del sistema operativo](#os-upgrade) e/o [aggiornamento del sistema del database](#pg-upgrade) descritto di seguito, l’Adobe deve aggiornare gli ambienti Campaign a [la versione 8.4.3 più recente](../../v8/start/release-notes.md), compatibile con questi sistemi.

**Come si esegue l’aggiornamento?**

In qualità di cliente di Cloud Service gestiti, Adobe ti contatterà e aggiornerà la tua versione di Campaign.

## Aggiornamento del sistema operativo {#os-upgrade}

**Sei interessato da questo problema?**

Se esegui Campaign su un sistema operativo Debian, per beneficiare degli ultimi aggiornamenti di sicurezza Debian, Adobe deve spostare l’infrastruttura Campaign in **Debian 11**. Tieni presente che il supporto per la sicurezza di Debian 9 sarà disponibile fino al 30 giugno 2023.

**Come si esegue l’aggiornamento?**

In qualità di cliente di Cloud Service gestiti, Adobe ti contatterà per aggiornare il tuo ambiente.

## Aggiornamento del sistema del database {#pg-upgrade}

**Sei interessato da questo problema?**

Se il sistema di database per Campaign è PostgreSQL, per beneficiare delle ultime innovazioni PostgreSQL e degli aggiornamenti di sicurezza, Adobe deve effettuare l’aggiornamento a **PostgreSQL 14**. Il 9 novembre 2023 PostgreSQL 11 raggiungerà la fine del ciclo di vita.

**Come si esegue l’aggiornamento?**

In qualità di cliente di Cloud Service gestiti, Adobe contatterà l&#39;utente e aggiornerà il database system da PostgreSQL 11 a PostgreSQL 14.
