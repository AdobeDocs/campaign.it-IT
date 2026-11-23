---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 5%
---
# execCommand

> Avvertenza: questa funzione è disponibile per un ambiente locale.

Esegue un comando e acquisisce il codice di errore e l&#39;output standard.

```text
execCommand (command [, bNoThrow ])
```

## Parametri

**comando** Il comando da eseguire con i relativi parametri.

**bNoThrow** true per ottenere l&#39;output e il codice di errore anche se il comando non restituisce zero (false per impostazione predefinita).

## Valore restituito

Restituisce una tabella il cui primo elemento corrisponde al codice restituito dal comando (se il codice restituito è diverso da zero, si verifica un&#39;anomalia) e il secondo elemento è una stringa di caratteri contenente l&#39;output standard prodotto.

## Osservazioni

Senza l&#39;opzione bNothrow, viene generata un&#39;eccezione se il comando non può essere eseguito o se il comando viene eseguito con un errore. Se bNoThrow è uguale a true, viene generata un&#39;eccezione solo se il comando non può essere eseguito. Per utilizzare questa funzione, l&#39;operatore deve disporre dei diritti &#39;createProcess&#39;, altrimenti viene generata un&#39;eccezione. A seconda dell’installazione, alcuni comandi possono trovarsi sull’elenco Bloccati. Ad esempio: ln, dd, openssl, curl, wget, python, python3, perl, ruby, sh, bash, dash, zsh, base64, nlserver, node, phantomjs, java, awk, nc, telnet, ssh, scp, ftp.

## Esempio

```text
var result = execCommand('gpg-exec.sh gpg --no-tty --yes -r CampaignOperations@adobe.com --encrypt "file_to_encrypt"', true);
```

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
