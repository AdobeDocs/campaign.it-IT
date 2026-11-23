---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%
---
# DESencrypt

> Avvertenza:
>
> Questa funzione è obsoleta. Utilizzare [cryptString()](f-cryptstring.md).

Digitalizza una stringa con l&#39;algoritmo DES.

```text
DESencrypt (value [, key ] [, cipher mode ] [, initialization vector ] [, padding ])
```

## Parametri

**value** Stringa da digitalizzare

**chiave** La chiave rappresentata in formato esadecimale. La chiave deve essere lunga 64 bit o 16 caratteri esadecimali. Per impostazione predefinita, viene utilizzato l’identificatore del database.

**modalità crittografia** Il metodo di codifica dei blocchi. Una stringa di caratteri. ossia &quot;CBC&quot;, &quot;BCE&quot; o &quot;EDE&quot;. Per impostazione predefinita, &quot;CBC&quot;.

**vettore di inizializzazione** vettore di inizializzazione sotto forma di stringa esadecimale. Esattamente 8 ottetti, ovvero 16 caratteri. Una stringa vuota per impostazione predefinita.

**spaziatura** Il tipo di spaziatura. Stringa di caratteri, ad esempio &quot;PKCS5PADDING&quot; o &quot;PKCS7PADDING&quot;. Per impostazione predefinita, una stringa vuota indica che alla fine della stringa da crittografare viene aggiunto &quot;\\0&quot;.

## Valore restituito

Stringa digitalizzata rappresentata in base 64.

## Osservazioni

* Una chiave DES ha 56 bit utili e 8 bit utilizzati per la parità; questi bit vengono ignorati.
* Il valore effettivamente crittografato dall&#39;algoritmo DES sarà la rappresentazione Windows-1252 a 8 bit della stringa, finendo con un carattere ASCII 0 e imbottito a multipli di 64 bit con zeri binari.
* Il valore digitalizzato ha un valore a 64 bit a più lunghezze.

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
