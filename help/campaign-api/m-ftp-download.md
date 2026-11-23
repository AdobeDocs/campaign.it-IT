---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 9%
---
# scaricare

Scarica un file dal server in un file locale o in memoria.

```text
download (URL [, append ])
```

## Parametri

**URL** URL del file da scaricare.

**aggiungi** Per impostazione predefinita, se il file scaricato esiste già nel disco locale, verrà sovrascritto dal nuovo file ricevuto. Se il booleano è attivato, Adobe Campaign scriverà il contenuto scaricato nel file con lo stesso nome insieme al contenuto esistente.

## Valore restituito

Nessuno.

## Osservazioni

Per recuperare il file in un file locale, iniziare utilizzando il metodo setFile. Esempio:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.download("ftp://ftp.funet.fi/pub/standards/RFC/rfc2068.txt")
```

## Funzioni

**Metodo di classe:** [FTP](c-ftp.md)

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
