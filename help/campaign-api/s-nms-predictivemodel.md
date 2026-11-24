---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 7%
---
# predictiveModel

Questo schema rappresenta un modello predittivo.

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [BuildScoringFunction](sm-predictivemodel-buildscoringfunction.md) | Genera la funzione di punteggio per il modello. |
| [GetScoringXtkExpr](sm-predictivemodel-getscoringxtkexpr.md) | Fornisce l’espressione XTK che calcola il punteggio. |
| [Addestra](sm-predictivemodel-train.md) | Allena il modello. |

## Metodi generici

| Elemento “method” | Descrizione |
| --- | --- |
| [crea](f-create.md) | Crea una nuova entità corrispondente a uno schema specificato. |
| [carica](f-load.md) | Carica e restituisce un&#39;entità corrispondente a uno schema e a una chiave specifici. |
| [salva](m-entity-save.md) | Salva un&#39;entità nel database. |
