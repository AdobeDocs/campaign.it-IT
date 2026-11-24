---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 5%
---
# formatDate

Formatta una data come stringa di caratteri.

```text
formatDate (date, format [, timeZone ])
```

## Parametri

**data** la data da convertire.

**format** Stringa di caratteri che descrive il formato da utilizzare. I caratteri utilizzati per formattare le diverse parti della data sono i seguenti:

* Y - Year
* M - Mese dell’anno (1-12)
* B - Nome mese
* D - Giorno del mese (1-31)
* A - Nome giorno
* J - Giorno dell&#39;anno (1-366)
* W - Settimana dell’anno
* H - Ora (0-23)
* I - Ora (1-12)
* N - Minuti (0-59)
* S - Secondi (0-59)
* P - AM/PM

È possibile specificare un numero davanti ad alcuni di questi caratteri. I caratteri A e B possono essere seguiti da una l per utilizzare il nome completo anziché la versione abbreviata o da una i per utilizzare il nome in inglese. Esempi:

* &quot;%4Y/%2M/%2D&quot; => 2000/01/24.
* &quot;%A %D %B %4Y&quot; => lunedì 24 gennaio 2000.
* &quot;%Al %D %Bl %4Y&quot; => lunedì 24 gennaio 2000.
* &quot;%02H:%02N:%02S&quot; visualizza l&#39;ora, i minuti e i secondi con due cifre.

**fuso orario** Stringa di caratteri corrispondente al fuso orario. I valori possibili sono specificati nello schema di enumerazione xtk:common:timezone.

## Valore restituito

Una stringa di caratteri che rappresenta la data nel formato richiesto.

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
