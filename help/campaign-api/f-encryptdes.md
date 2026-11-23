---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# encryptDES

> Avvertenza:
>
> Questa funzione è obsoleta. Utilizzare [cryptString()](f-cryptstring.md).

Crittografa una stringa con l&#39;algoritmo DES.

```text
encryptDES (key, value [, cipher mode ] [, initialization vector ] [, padding ])
```

## Parametri

**chiave** La chiave rappresentata in formato esadecimale. La chiave deve essere lunga 64 bit, ovvero 16 caratteri esadecimali.

**value** Stringa da crittografare

**modalità cifratura** Il metodo per la codifica dei blocchi. Una stringa di caratteri. ossia &quot;CBC&quot;, &quot;BCE&quot; o &quot;EDE&quot;. Per impostazione predefinita, &quot;CBC&quot;.

**vettore di inizializzazione** vettore di inizializzazione sotto forma di stringa esadecimale. Esattamente 8 ottetti, ovvero 16 caratteri. Una stringa vuota per impostazione predefinita.

**spaziatura** Il tipo di spaziatura. Stringa di caratteri, ad esempio &quot;PKCS5PADDING&quot; o &quot;PKCS7PADDING&quot;. Per impostazione predefinita, una stringa vuota indica che &quot;\\0&quot; viene aggiunto alla fine della stringa da crittografare.

## Valore restituito

Stringa crittografata rappresentata in base 64.

## Osservazioni

* Una chiave DES ha 56 bit utili e 8 bit utilizzati per la parità; questi bit vengono ignorati.
* Il valore effettivamente crittografato dall&#39;algoritmo DES sarà la rappresentazione Windows-1252 a 8 bit della stringa, finendo con un carattere ASCII 0 e imbottito a multipli di 64 bit con zeri binari.
* Il valore crittografato sarà un multiplo di parole a 64 bit.

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
