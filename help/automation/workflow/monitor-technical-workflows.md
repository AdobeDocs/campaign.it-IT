---
product: campaign
title: Monitorare i flussi di lavoro tecnici
description: Monitorare i flussi di lavoro tecnici
feature: Workflows
role: Admin
exl-id: 8524d916-8af7-4641-b047-9c348f1017fd
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 5%

---

# Monitorare i flussi di lavoro tecnici {#monitoring-technical-workflows}

I flussi di lavoro tecnici devono essere monitorati e, in caso di errore, è necessario intervenire.

## Dashboard di monitoraggio delle istanze {#instance-monitoring-dashboard}

È possibile accedere al dashboard di monitoraggio delle istanze tramite la scheda **[!UICONTROL Monitoring]**.

![](assets/monitoring_technical_workflows1.png)

In Indicatori di sistema e file di base, verificare che nessun indicatore sia evidenziato in rosso. Se questo è il caso e alcuni sono, dovresti:

* Verificare che i processi necessari siano sempre in esecuzione,
* Verificare che nessuno dei processi sia troppo vecchio,
* Verificare che i file di registro dei diversi processi non contengano errori allarmanti e ricorrenti.

## Flussi di lavoro tecnici {#technical-workflows}

I flussi di lavoro tecnici sono disponibili da **[!UICONTROL Administration]** > **[!UICONTROL Production]** > **[!UICONTROL Technical workflows]**.

A seconda del flusso di lavoro tecnico, segui i passaggi descritti di seguito per assicurarti che tutto funzioni come previsto.

Per comprendere meglio le funzioni di ogni flusso di lavoro tecnico, consulta questa [sezione](technical-workflows.md).

Per **[!UICONTROL Database Cleanup workflow ('cleanup')]**:

Controlla il giornale di registrazione per verificare che il tempo trascorso sia relativamente costante nel tempo e non interferisca con altri flussi di lavoro.

Per **[!UICONTROL Tracking workflow ('tracking')]**:

Verificare che il flusso di lavoro di tracciamento venga eseguito come pianificato (ogni ora per impostazione predefinita) e che il giornale di registrazione non evidenzi gli errori ricorrenti. Per ulteriori informazioni, consulta questa [sezione](delivery.md).

Per **[!UICONTROL Deliverability update ('deliverabilityUpdate')]**:

1. Verificare che il flusso di lavoro **[!UICONTROL Deliverability update]** venga eseguito e completato correttamente ogni giorno.
1. Verifica nel giornale di registrazione che le regole vengano aggiornate regolarmente.

Per **[!UICONTROL Campaign process ('operationMgt', 'deliveryMgt', ...)]**:

1. Esaminare tutti i flussi di lavoro presenti nella cartella **[!UICONTROL Campaign process]**. Per ulteriori informazioni, consulta questa [pagina](technical-workflows.md).
1. Verificare che i flussi di lavoro vengano eseguiti come pianificato e che il giornale di registrazione non evidenzi gli errori ricorrenti.

## Supervisione del flusso di lavoro {#workflow-supervision}

Il gruppo **[!UICONTROL Workflow supervisors]** deve contenere operatori che devono essere tenuti informati degli errori e che possono intervenire in tempo.

![](assets/monitoring_technical_workflows3.png)

In caso di problemi, genera un avviso che deve essere inviato al gruppo corretto.

Assicurati che ogni operatore disponga di un indirizzo e-mail valido.

Qualsiasi flusso di lavoro che deve essere in esecuzione per mantenere funzionante la piattaforma, ad esempio le importazioni di dati giornaliere, deve essere dichiarato come &quot;Produzione&quot; (casella di controllo) e visualizzato in grassetto.

## Elenco manutenzione flusso di lavoro {#workflow-maintenance-list}

Tutti i flussi di lavoro tecnici personalizzati devono essere documentati in un foglio di lavoro che contiene:

* Nome e posizione del flusso di lavoro.
* Scopo.
* Pianificazione e dipendenze.
* Operatore incaricato del monitoraggio.
* Istruzioni su cosa fare in caso di errore.

![](assets/monitoring_technical_workflows4.png)

## Pianificazione e automazione del monitoraggio {#planning-and-automation-of-monitoring}

La pianificazione del monitoraggio del flusso di lavoro migliora l&#39;efficienza. Alcune attività devono essere eseguite ogni giorno, mentre altre possono essere eseguite ogni settimana o ogni mese.

L’impostazione dei flussi di lavoro nelle cartelle denominate per ricorrenza e ordinate in base alla pianificazione di esecuzione migliora l’efficienza del monitoraggio.

L&#39;automazione del monitoraggio riduce il sovraccarico delle risorse e garantisce che le attività vengano pianificate con la frequenza appropriata.

Puoi creare un flusso di lavoro di monitoraggio per inviare un’e-mail ogni volta che alcune attività non riescono o quando una tabella critica diventa troppo grande.

È possibile creare una vista in modo da poter monitorare tutti i flussi di lavoro in un’area funzionale o a livello di sistema.

Puoi anche utilizzare la funzionalità per job o report di Adobe Campaign per creare la documentazione su richiesta, sempre aggiornata.
