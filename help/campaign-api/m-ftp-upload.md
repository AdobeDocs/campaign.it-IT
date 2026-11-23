---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 20%
---
# caricare

Scaricare un file da un file locale a un server FTP.

```text
upload (URL)
```

## Parametri

URL del server **URL**.

## Valore restituito

Nessuno.

## Osservazioni

L’URL deve iniziare con &quot;ftp:&#39; Esempio:

```javascript
var ftp = new FTP
ftp.setFile("c:/rfc.txt")
ftp.upload("ftp://ftp.funet.fi/pub/standards/RFC")
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
