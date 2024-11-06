---
title: Inviare SMS con Adobe Campaign
description: Introduzione agli SMS in Campaign
feature: SMS
role: User, Data Engineer
level: Beginner
exl-id: e2e2922a-2058-4588-b1b5-6997f29ee663
source-git-commit: 19c5a15a0f42285fc3b1a448f3cbf474d741e6e2
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 10%

---

# Introduzione agli SMS {#gs-sms-channel}

Utilizza Adobe Campaign per inviare messaggi di testo ai clienti sui loro dispositivi mobili. Dall’editor SMS puoi creare, personalizzare e visualizzare in anteprima i messaggi in formato testo.

Per inviare SMS ai dispositivi mobili con Adobe Campaign, è necessario:

* Un account esterno configurato sul canale **[!UICONTROL Mobile (SMS)]**. Scopri come configurare il canale SMS nell’infrastruttura [mid-sourcing](sms-mid-sourcing.md). Per questa configurazione, è necessario comprendere i [parametri dell&#39;account esterno SMPP](smpp-external-account.md) e le [caratteristiche del canale SMS](sms-channel.md).
Dopo questa configurazione, controlla la tua connessione SMPP e se necessario, scopri come risolverla con i problemi. [Ulteriori informazioni](smpp-connection.md).

* Un modello di consegna SMS collegato correttamente a questo account esterno.


>[!NOTE]
>
>Puoi anche utilizzare Adobe Campaign per inviare [LINE](../../send/line.md) messaggi, con testo e/o immagini e collegamenti.


<table style="table-layout:fixed"><tr style="border: 0;">
<td>
<a href="create-sms.md">
<img alt="Creare un SMS" src="../../assets/do-not-localize/sms-sending.jpg">
</a>
<div><a href="create-sms.md"><strong>Creare una consegna SMS</strong>
</div>
<p>
</td>
<td>
<a href="sms-content.md">
<img alt="Contenuto SMS" src="../../assets/do-not-localize/sms.jpg">
</a>
<div>
<a href="sms-content.md"><strong>Definire e personalizzare il contenuto</strong></a>
</div>
<p></td>
<td>
<a href="sms-audience.md">
<img alt="Pubblico" src="../../assets/do-not-localize/sms-opt-out.jpg">
</a>
<div>
<a href="sms-audience.md"><strong>Gestione rinuncia</strong></a>
</div>
<p>
</td>
<td>
<a href="smpp-external-account.md">
<img alt="Configurazione" src="../../assets/do-not-localize/sms-config.jpg">
</a>
<div>
<a href="smpp-external-account.md"><strong>Configurare il canale SMS</strong></a>
</div>
<p>
</td>
</tr></table>
