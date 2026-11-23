---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 8%
---
# decryptDES

> Avvertenza:
>
> Funzione obsoleta. Utilizzare [decryptString()](f-decryptstring.md).

Annulla la crittografia di una stringa con l&#39;algoritmo DES.

```text
decryptDES (key, value [, cipher mode ] [, initialization vector ])
```

## Parametri

**chiave** La chiave rappresentata in formato esadecimale. La chiave deve contenere 64 bit o 16 caratteri esadecimali.

**value** I dati da crittografare rappresentati nella base 64.

**modalità cifratura** Il metodo per la codifica dei blocchi. Una stringa di caratteri. ossia &quot;CBC&quot;, &quot;BCE&quot; o &quot;EDE&quot;. Per impostazione predefinita, &quot;CBC&quot;.

**vettore di inizializzazione** vettore di inizializzazione sotto forma di stringa esadecimale. Esattamente 8 ottetti, ovvero 16 caratteri. Una stringa vuota per impostazione predefinita.

## Valore restituito

Stringa di caratteri in testo non crittografato.

## Osservazioni

* Una chiave DES ha 56 bit utili e 8 bit utilizzati per la parità; questi bit vengono ignorati.
* I dati verranno decrittografati come stringa a 8 bit nella tabella codici di Windows-1252.
* I dati crittografati devono essere lunghi più di 64 bit.

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
