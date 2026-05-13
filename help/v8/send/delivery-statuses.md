---
title: Stati di consegna
description: Ulteriori informazioni sugli stati disponibili nel dashboard di consegna
feature: Monitoring, Deliverability
role: User
level: Beginner
version: Campaign v8, Campaign Classic v7
exl-id: 90f2b7b2-db9e-42aa-aef2-e90aee5d208e
TQID: https://experienceleague.adobe.com/raVVeGP6V9mukXOtwg84UsZWpPpQsP3v9jpluSpQ6ZY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 15d7b12d07f84356fac7bee2a54a0057c5d00d41
workflow-type: tm+mt
source-wordcount: 557
ht-degree: 5%

---

# Stati di consegna {#delivery-statuses}

Una volta inviata la consegna, il dashboard di consegna visualizza uno stato che consente di monitorare se l’invio è stato eseguito correttamente. I possibili stati sono descritti nella sezione seguente.

![](assets/delivery-status.png)

Per ulteriori dettagli sui diversi errori di consegna riscontrabili e su come risolverli, consulta [Informazioni sugli errori di consegna](delivery-failures.md).

**Argomenti correlati:**

* [Inviare e monitorare le e-mail](send.md)
* [Errori di consegna](delivery-failures.md)
* [Introduzione al recapito messaggi](about-deliverability.md)

## Elenco degli stati di consegna {#list-delivery-statuses}

<table> 
 <thead> 
  <tr> 
   <th> Stato<br /> </th> 
   <th> Definizioni e soluzioni<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Inviato<br /> </td> 
   <td> La consegna è stata inviata correttamente al provider di messaggi (ma il destinatario non l'ha necessariamente ricevuta).<br /> </td> 
  </tr> 
  <tr> 
   <td> Ignorato<br /> </td> 
   <td> La consegna non è stata inviata al destinatario a causa di un errore con il suo indirizzo. Era in fase di inserisco nell'elenco Bloccati di, messo in quarantena, non fornito o duplicato. <br /> </td> 
  </tr> 
  <tr> 
   <td> Non riuscito<br /> </td> 
   <td> La consegna non è riuscita a raggiungere il destinatario a causa, ad esempio, di un indirizzo non valido o di una casella in entrata completa. Può anche essere collegato a un problema con i blocchi di personalizzazione, in quanto possono generare errori quando gli schemi non corrispondono alla mappatura della consegna. Vedi <a href="delivery-failures.md" target="_blank">Informazioni sugli errori di consegna</a><br /> </td> 
  </tr>
  <tr> 
   <td> In sospeso<br /> </td> 
   <td> La consegna è pronta per essere inviata e verrà elaborata dal server di consegna (MTA). Vedi <a href="#pending-status" target="_blank">Stato in sospeso</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Non applicabile<br /> </td> 
   <td> La consegna è stata presa in considerazione dal server (MTA) ma non elaborata.<br /> </td> 
  </tr>  
  <tr> 
   <td> Consegna annullata<br /> </td> 
   <td> Consegna annullata da un operatore.<br /> </td> 
  </tr> 
  <tr> 
   <td> Considerato dal provider di servizi<br /> </td> 
   <td> Per le consegne SMS, il provider del servizio SMS ha ricevuto la consegna.<br /> Per le consegne e-mail, il messaggio è stato inoltrato correttamente da Campaign all’MTA (Mail Transfer Agent).</td> 
  </tr> 
  <tr> 
   <td> Ricevuto su dispositivo mobile<br /> </td> 
   <td> Il destinatario ha ricevuto l'SMS sul proprio dispositivo mobile.<br /> </td> 
  </tr>
  <tr> 
   <td> Inviato al provider di servizi<br /> </td> 
   <td> La consegna è stata inviata al provider di servizi SMS ma non è ancora stata ricevuta.<br />
   </td> 
  </tr> 
  <tr> 
   <td> Preparato<br /> </td> 
   <td> Stato intermedio utilizzato solo per i connettori esterni, ad esempio il canale mobile. Segue lo stato "In sospeso" ed è il connettore esterno che determinerà il seguente stato.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Per informazioni su come ottimizzare il recapito dei messaggi di posta elettronica di Adobe Campaign, consulta [questa sezione](about-deliverability.md). Per informazioni più approfondite sul recapito messaggi, consulta la [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it).

## Stato in sospeso {#pending-status}

Dopo aver confermato la consegna, puoi vedere che lo stato della consegna è **[!UICONTROL Pending]**. Questo stato indica che il processo di esecuzione è in attesa della disponibilità di alcune risorse.

Lo stato **[!UICONTROL Pending]** può indicare che la consegna è stata pianificata ed è in sospeso fino alla data specificata. Per ulteriori informazioni, consulta la sezione [Pianificazione invio consegna](configure-and-send.md#schedule-delivery-sending).

Se la consegna non viene inviata e il suo stato rimane **[!UICONTROL Pending]**, può essere il risultato di:

* **Troppe campagne in esecuzione contemporaneamente**

  Il limite di campagne simultanee è definito nell&#39;opzione **[!UICONTROL NmsOperation_LimitConcurrency]**. Il valore predefinito è 10.

  In qualità di utente di Managed Cloud Services, puoi lavorare con Adobe per regolare questo limite, se necessario. Ulteriori informazioni sulle opzioni nella [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/installing-campaign-classic/appendices/configuring-campaign-options.html){target="_blank"}.

* **Problemi relativi alla disponibilità delle risorse**

  L’MTA (Message Transfer Agent) potrebbe attendere che le risorse siano disponibili prima di elaborare la consegna.

>[!NOTE]
>
>In qualità di utente di Campaign v8 Managed Cloud Services, l’infrastruttura MTA è monitorata e gestita da Adobe. In caso di problemi persistenti con le consegne in sospeso, contatta l’Assistenza clienti di Adobe.

**Argomenti correlati:**

* [Inviare e monitorare le e-mail](send.md#email-monitoring)
* [Errori di consegna](delivery-failures.md)
* [Monitorare l’ambiente Campaign](../start/monitor.md#monitor-deliveries)
