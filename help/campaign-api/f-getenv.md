---
source-git-commit: 77f8182ea5b1fda08206021a164b2e0ff827890a
workflow-type: tm+mt
source-wordcount: '72'
ht-degree: 16%
---
# getEnv

>[!WARNING]
>
>Questa funzione è disponibile per un ambiente locale.

>[!NOTE]
>
>È possibile disattivare questa funzione passando l&#39;opzione **XtkSecurity\_Disable\_GetSetEnv** a **true**.

Restituisce il valore di una variabile di ambiente.

```text
getEnv (name [, default ])
```

## Parametri

**nome** Nome della variabile.

**default** Valore predefinito da utilizzare se la variabile di ambiente non è stata trovata.

## Valore restituito

Il valore della variabile.

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
