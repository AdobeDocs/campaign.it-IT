---
title: Inviare SMS con Adobe Campaign
description: Introduzione agli SMS in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
badge: label="Disponibilità limitata" type="Informative"
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: af1d453179c2d739eca243b435dec90a4b8e2dd5
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 4%

---

# Introduzione agli SMS {#gs-sms-channel}

Utilizza Adobe Campaign per inviare messaggi SMS personalizzati.

>[!IMPORTANT]
>
>Questa documentazione è per Adobe Campaign v8.7.2 e versioni successive.
>
>Per le versioni precedenti, leggere la documentazione di [Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up).

>[!NOTE]
>
>Adobe Campaign consente inoltre di inviare notifiche push su dispositivi mobili tramite l&#39;opzione **Canale app mobile Adobe Campaign (NMAC)**. Per ulteriori informazioni, consulta [questa sezione](../push.md).

La semplicità e la facilità d&#39;uso degli SMS lo rendono un canale di comunicazione molto utile, oltre alla sua robustezza e compatibilità ineguagliabile su miliardi di terminali.

Esistono 2 modi principali per inviare un SMS:

* Invialo manualmente da un telefono. Questo è il modo abituale di comunicare direttamente tra le persone.
* Mandatelo da internet. Questo è il modo in cui Adobe Campaign utilizza per inviare messaggi. A tal fine, è necessario un provider di servizi SMS che crei un ponte da Internet alla rete mobile.

In questa documentazione trovi i passaggi per configurare, inviare e monitorare una consegna SMS:

* **Configurare il canale SMS**

Devi innanzitutto configurare il canale SMS nell&#39;infrastruttura [mid-sourcing](sms-mid-sourcing.md).

<!--The steps depend on the platform: either you have [a standalone instance](sms-standalone-instance.md) or you are in [a mid-sourcing infrastructure](sms-mid-sourcing.md).-->

Per questa configurazione, è necessario comprendere i [parametri dell&#39;account esterno SMPP](smpp-external-account.md) e le [caratteristiche del canale SMS](sms-channel.md).

Dopo questa configurazione, controlla la tua connessione [SMPP e se necessario, scopri come risolverla](smpp-connection.md).

* **Crea la tua prima consegna SMS**

Per iniziare la configurazione della consegna SMS:

1. Crea la consegna e compila le [impostazioni di consegna SMS](sms-delivery-settings.md),

1. [Definisci il contenuto](sms-content.md) della consegna,

1. [Selezionare il pubblico](sms-audience.md).

I passaggi per definire un pubblico sono descritti in dettaglio in [questa pagina](../../audiences/create-audiences.md).

* **Convalidare e inviare SMS**

Dopo la creazione della consegna:

1. [Invia bozze](sms-proofs.md) per convalidare il rendering e il contenuto,

1. Quindi [invia al pubblico finale](sms-send.md).

* **Monitorare e tenere traccia degli SMS**

Dopo l&#39;invio, [scopri come monitorare e tenere traccia dell&#39;SMS](sms-monitor.md).
