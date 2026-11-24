---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 6%
---
# hmacStr

Calcola l’hash MD5, SHA-1 o SHA-256 di una stringa di caratteri. La stringa viene codificata automaticamente in UTF-8 prima del calcolo.

```text
hmacStr (string [, key ] [, algo ])
```

## Parametri

**stringa** Stringa in cui deve essere calcolato l&#39;hash.

Chiave **key**, sotto forma di stringa di caratteri. Viene automaticamente convertito in UTF-8. Se la chiave non è presente, il server utilizzerà una chiave che dipende dall&#39;istanza ed è valida solo per questa istanza.

**algo** Tipo di hash da utilizzare. I valori possibili sono &quot;MD5&quot;, &quot;SHA1&quot; o &quot;SHA256&quot;. La distinzione tra maiuscole e minuscole viene ignorata, pertanto è possibile immettere i valori in lettere minuscole o maiuscole. Se non viene specificato alcun parametro, il valore &quot;SHA1&quot; viene selezionato per impostazione predefinita.

## Valore restituito

L’hash MD5, SHA-1 o SHA-256 (a seconda del tipo di hash selezionato) della stringa passata come parametro.

## Osservazioni

Per i tipi MD5 e SHA-1, la chiave può contenere fino a 64 caratteri (512 bit) dopo la conversione in UTF-8. Per il tipo SHA-256, la chiave può contenere fino a 32 caratteri (256 bit) dopo la conversione in UTF-8.

## Funzioni

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
