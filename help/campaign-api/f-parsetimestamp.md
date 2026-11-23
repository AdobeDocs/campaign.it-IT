---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 9%
---
# parseTimeStamp

Converte una stringa di caratteri contenente una data formulata in base a una versione semplificata dello standard ISO 8601 in un oggetto di tipo Data.

```text
parseTimeStamp (aString)
```

## Parametri

**aString** La data sotto forma di stringa di caratteri in formato ISO 8601.

## Valore restituito

Oggetto di tipo Date che corrisponde alla data impostata come parametro.

## Osservazioni

La sintassi è la seguente:

```javascript
              date
              time[time-zone]
            
```

o

```javascript
              dateTtime[time-zone]
            
```

La data deve avere il seguente formato:

```javascript
YYYY-MM-DD
```

Per motivi di compatibilità, viene accettato anche il seguente formato:

```javascript
YYYY/MM/DD
```

L’ora deve avere il seguente formato:

```javascript
hh:mm:ss
hh:mm:ss.nnn
```

Il fuso orario, se specificato, deve avere il seguente formato:

```javascript
Z
+hh:mm
-hh:mm
+hh
-hh
```

Se il fuso orario non è specificato, la data verrà convertita nel fuso orario corrente (a seconda del contesto). Esempi:

```javascript
2005-03-02 00:00:00
2005-03-02
2005-03-02T14:32:26
2005-03-02T14:32:26.0000
2005-03-02T14:32:26.0000000+01:00
2005-03-02T14:32:26+01:00
2005-03-02T14:32:26Z
2005-03-02T14:32:26.0005Z
2005/03/02 14:32:25
```

Se il formato della data non è valido, viene generata un&#39;eccezione.

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
