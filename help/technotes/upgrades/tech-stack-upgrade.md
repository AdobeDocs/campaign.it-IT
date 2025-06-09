---
product: campaign
title: Nota tecnica - Aggiornamenti dei sistemi Adobe Campaign
description: Aggiornamento del sistema Adobe Campaign
hide: true
hidefromtoc: true
exl-id: cc64cce1-2473-4136-aadc-8b13e89ef7f9
source-git-commit: 0f5efba364ef924447324bdd806e15e6db8d799d
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 9%

---

# Aggiornamenti dell’ambiente Adobe Campaign 2023 {#ac-system-upgrade}

L’infrastruttura di Campaign si basa su sistemi di terze parti che devono essere regolarmente aggiornati con le versioni e le correzioni più recenti. Questi aggiornamenti sono obbligatori per garantire la continuità del servizio e la protezione degli ambienti Campaign dai rischi di sicurezza. Inoltre, è necessario un aggiornamento di Campaign per garantire la compatibilità con modifiche al sistema di terze parti.

In qualità di **cliente di Managed Cloud Services**, Adobe ti informa su questi aggiornamenti quando sono necessari. Gli ambienti dovranno essere aggiornati in conformità con le raccomandazioni per garantire la conformità.

Per motivi di sicurezza, Adobe deve [installare la build Campaign più recente](#ac-upgrade), quindi aggiornare il [sistema operativo](#os-upgrade) e/o il [Relation Database Management System (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>Per qualsiasi domanda su queste modifiche, contatta [Adobe Customer Care](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>

## Aggiornamento della build di Campaign {#ac-upgrade}

**Sei interessato da questo problema?**

Se sei interessato dall&#39;[aggiornamento del sistema operativo](#os-upgrade) e/o dall&#39;[aggiornamento del sistema di database](#pg-upgrade) descritto di seguito, Adobe deve aggiornare gli ambienti Campaign alla [versione 8.4.3 più recente](../../v8/start/release-notes.md), compatibile con questi sistemi.

**Come si esegue l’aggiornamento?**

In qualità di cliente di Managed Cloud Services, Adobe ti contatterà e aggiornerà la tua versione di Campaign.

## Aggiornamento del sistema operativo {#os-upgrade}

**Sei interessato da questo problema?**

Se esegui Campaign su un sistema operativo Debian, per beneficiare degli ultimi aggiornamenti di sicurezza Debian, Adobe deve spostare l’infrastruttura di Campaign in **Debian 11**. Tieni presente che il supporto per la sicurezza di Debian 9 sarà disponibile fino al 30 giugno 2023.

**Come si esegue l’aggiornamento?**

In qualità di cliente di Managed Cloud Services, Adobe ti contatterà per aggiornare il tuo ambiente.

## Aggiornamento del sistema del database {#pg-upgrade}

**Sei interessato da questo problema?**

Se il sistema di database per Campaign è PostgreSQL, per beneficiare delle ultime innovazioni PostgreSQL e degli aggiornamenti di sicurezza, Adobe deve eseguire l&#39;aggiornamento a **PostgreSQL 14**. Il 9 novembre 2023 PostgreSQL 11 raggiungerà la fine del ciclo di vita.

**Come si esegue l’aggiornamento?**

In qualità di cliente di Managed Cloud Services, Adobe ti contatterà e aggiornerà il sistema di database da PostgreSQL 11 a PostgreSQL 14.
