---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 18%
---
# InstallPackage

Installa un pacchetto.

```text
InstallPackage ( XML parameters )
```

## Parametri

**parametri** elemento XML contenente il pacchetto da importare.

## Valore/i restituito/i

Nessuno.

## Osservazioni

Un pacchetto generato dal metodo SpecFile.Generate() deve essere incapsulato in un elemento builder. Esempio:

```javascript
var params =
  {builder:
    {package:
      { ... }
    }
  }

NLWS.xtkBuilder.InstallPackage(params)
```

## Funzioni

**Schema:** [xtk:builder](s-xtk-builder.md)

**Statico:**

Sì
