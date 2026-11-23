---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%
---
# cryptString

> Avvertenza:
>
> Questa funzione è completamente obsoleta. Per ulteriori dettagli, consulta questa [pagina](https://experienceleague.adobe.com/en/docs/campaign-classic/using/technotes/gcm-functions#deprecated-functions-headding-anchor-depracated-functions).

Crittografa una stringa di caratteri con la chiave dell’istanza o di qualsiasi altra chiave.

```text
cryptString (str [, key ] [, useSalt ])
```

## Parametri

**str** Stringa di caratteri da crittografare.

**chiave** La chiave di crittografia AES è codificata in base 64: 256 bit se la lunghezza della chiave è 32; 192 bit se la lunghezza della chiave è 24; 128 bit se la lunghezza della chiave è 16 o se non è specificata alcuna chiave.

**useSalt** Utilizza un sale dei dati per crittografare. True per impostazione predefinita.

## Valore restituito

Restituisce la stringa di caratteri crittografati

## Osservazioni

La cifratura avviene secondo il seguente metodo:

* La stringa di caratteri Unicode viene trasformata in una stringa UTF-8.
* Alla fine viene aggiunto un carattere di spunta.
* Questa stringa viene crittografata utilizzando l&#39;algoritmo AES in modalità Cipher Block Chaining (CBC) con un vettore di inizializzazione null. Se come parametro non viene fornita alcuna chiave, viene utilizzata la chiave di istanza.
* Il blocco crittografato viene quindi convertito in base 64.

La decrittografia viene eseguita utilizzando la funzione [decryptString](f-decryptstring.md).

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
