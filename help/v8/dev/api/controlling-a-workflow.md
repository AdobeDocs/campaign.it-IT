---
title: Controllo di un flusso di lavoro
description: Scopri come controllare un flusso di lavoro con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
role: Data Engineer
level: Experienced
exl-id: 79eacc31-d5a2-4e13-aa0b-744d7ab7004f
source-git-commit: 5b9793d98d12afb28e987b16bc2e34f0ee72ac5f
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 12%

---

# Controllo di un flusso di lavoro {#controlling-a-workflow}

Puoi controllare un flusso di lavoro direttamente dall’API REST, tramite una richiesta POST contenente l’ID del flusso di lavoro e il comando di esecuzione richiesto:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Se l’ID del flusso di lavoro viene modificato in Adobe Campaign, la richiesta API non funzionerà più.

Per controllare un flusso di lavoro sono disponibili quattro comandi di esecuzione:

* Inizio
* Pausa
* Riprendi
* Interruzione


***Richieste di esempio***

* Avvia un flusso di lavoro.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"start"}'
  ```

  <!-- + réponse -->

* Metti in pausa un flusso di lavoro.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"pause"}'
  ```

  <!-- + réponse -->

* Riprendere un workflow.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"resume"}'
  ```

  <!-- + réponse -->

* Interrompere un flusso di lavoro.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -i
  -d '{"method":"stop"}'
  ```

  <!-- + réponse -->
