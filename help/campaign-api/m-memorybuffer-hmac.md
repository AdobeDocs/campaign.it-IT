---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 11%
---
# hmac

Calcola l’hash MD5, SHA-1 o SHA-256 del buffer.

```text
hmac (key [, algo ])
```

## Parametri

Chiave **key**, sotto forma di buffer.

Tipo di hash **algo** da utilizzare. I valori possibili sono &quot;MD5&quot;, &quot;SHA1&quot; o &quot;SHA256&quot;. Poiché non viene fatta distinzione tra maiuscole e minuscole, i valori possono essere immessi in minuscole o maiuscole. Per impostazione predefinita, se il parametro non è specificato, viene selezionato il valore &quot;SHA1&quot;.

## Valore restituito

Hash MD5, SHA-1 o SHA-256 (in base al tipo di hash scelto) del buffer.

## Funzioni

**Metodo di classe:** [MemoryBuffer](c-memorybuffer.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Messaggio di consegna
* Regola di tipologia
* Importazione
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
