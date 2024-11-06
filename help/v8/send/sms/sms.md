---
title: Inviare SMS con Adobe Campaign
description: Introduzione agli SMS in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: bb77b915f50b31d8d91e25da6fa86aa15b03bba4
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 17%

---

# Introduzione agli SMS {#gs-sms-channel}

Adobe Campaign ti consente di inviare SMS personalizzati sui dispositivi mobili.

Per i messaggi SMS, puoi creare, modificare e personalizzare i messaggi solo in formato testo. Puoi anche visualizzare in anteprima i messaggi SMS prima che vengano inviati.

>[!NOTE]
>
>Puoi anche utilizzare Adobe Campaign per inviare [LINE](../../send/line.md) messaggi, con testo e/o immagini e collegamenti.

Per inviare SMS a un telefono cellulare con Adobe Campaign, è necessario:

* Un account esterno configurato sul canale **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL LINE]**.
* Un modello di consegna SMS collegato correttamente a questo account esterno.

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
