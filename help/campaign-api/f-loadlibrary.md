---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 11%
---
# loadLibrary

Carica una libreria JavaScript.

```text
loadLibrary (filename [, boolean ])
```

## Parametri

**nomefile** Nome della libreria JavaScript da caricare.

**boolean** Attiva o disattiva la cache di caricamento. Per impostazione predefinita, è true.

> Nota: quando il parametro è impostato su false, è necessario utilizzare la funzione logon() prima che la chiamata loadLibrary sia autenticata come operatore.

## Valore restituito

Nessuno.

## Osservazioni

La cache è attivata per impostazione predefinita. Se la cache è disabilitata, viene eseguita una query sul database per ogni chiamata. Questa query consente di caricare la versione più recente della libreria. Esempio: loadLibrary(&#39;xtk:shared/nl.js&#39;)

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
