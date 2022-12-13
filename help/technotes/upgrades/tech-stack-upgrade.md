---
product: campaign
title: Nota tecnica - Aggiornamenti del sistema Adobe Campaign
description: Aggiornamento del sistema Adobe Campaign
hide: true
hidefromtoc: true
exl-id: 78949d94-60b3-44f1-8e5a-d61b5b723e87
source-git-commit: 3535e1e4fcd326412b6378253e5dde1249bce1f2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Aggiornamenti dell’ambiente Adobe Campaign 2023 {#ac-system-upgrade}

L’infrastruttura Campaign si basa su sistemi di terze parti che devono essere aggiornati regolarmente con le versioni e le correzioni più recenti. Questi aggiornamenti sono obbligatori per garantire la continuità del servizio e proteggere gli ambienti Campaign dai rischi per la sicurezza. Inoltre, è necessario un aggiornamento di Campaign per garantire la compatibilità con le modifiche del sistema di terze parti.

Come **Cliente Cloud Services gestiti**, l’Adobe ti informa di questi aggiornamenti quando sono necessari. Per garantire la conformità, è necessario aggiornare gli ambienti in conformità alle raccomandazioni.

Per motivi di sicurezza, l&#39;Adobe deve [installa la build Campaign più recente](#ac-upgrade)e quindi aggiorna il [sistema operativo](#os-upgrade) e/o [Sistema di gestione del database delle relazioni (RDBMS)](#pg-upgrade).

>[!NOTE]
>
>Per qualsiasi domanda su queste modifiche, contatta [Adobe Customer Care](https://helpx.adobe.com/it/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

## Aggiornamento della build di Campaign {#ac-upgrade}

**Sei interessato da questo problema?**

Se sei interessato dal [aggiornamento del sistema operativo](#os-upgrade) e/o [aggiornamento del sistema di database](#pg-upgrade) di seguito, Adobe deve aggiornare gli ambienti Campaign a [l&#39;ultima versione 8.4.3](../../v8/start/release-notes.md), compatibile con tali sistemi.

**Come si esegue l’aggiornamento?**

In qualità di cliente di Cloud Services gestiti, Adobe ti contatterà e aggiornerà la versione Campaign.

## Aggiornamento del sistema operativo {#os-upgrade}

**Sei interessato da questo problema?**

Se utilizzi Campaign su un sistema operativo Debian, per usufruire degli ultimi aggiornamenti sulla sicurezza Debian, Adobe deve spostare l’infrastruttura Campaign in **Debian 11**. Il supporto per la sicurezza per Debian 9 sarà disponibile fino al 30 giugno 2023.

**Come si esegue l’aggiornamento?**

In qualità di cliente di Cloud Services gestiti, Adobe ti contatterà e aggiornerà il tuo ambiente.

## Aggiornamento del sistema del database {#pg-upgrade}

**Sei interessato da questo problema?**

Se il sistema di database per Campaign è PostgreSQL, per beneficiare delle ultime innovazioni PostgreSQL e degli aggiornamenti di sicurezza, è necessario eseguire l’aggiornamento ad Adobe **PostgreSQL 14**. Si noti che PostgreSQL 11 raggiungerà la fine del ciclo di vita il 9 novembre 2023.

**Come si esegue l’aggiornamento?**

* In qualità di cliente di Cloud Services gestiti, Adobe ti contatterà e aggiornerà il tuo sistema di database da PostgreSQL 11 a PostgreSQL 14.
