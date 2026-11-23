---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%
---
# Schema (classe)

Rappresenta la definizione dello schema.

Uno schema viene ottenuto chiamando il metodo della variabile globale `application`. Un&#39;istanza di questo oggetto ha un oggetto come prototipo e quindi ne eredita i metodi.

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [toDocument](m-schema-todocument.md) | Converte lo schema in un modulo di documento XML. |

## Proprietà

| Proprietà | Descrizione |
| --- | --- |
| [enumerazioni](p-schema-enumerations.md) | Restituisce la tabella che contiene l&#39;elenco di [enumerazioni](c-enumeration.md) definite in questo schema. |
| [id](p-schema-id.md) | L’identificatore dello schema sotto forma di stringa. |
| [isLibrary](p-schema-islibrary.md) | Restituisce un valore booleano che specifica se lo schema è una libreria di componenti. |
| [labelSingular](p-schema-labelsingular.md) | Nome singolare dello schema sotto forma di stringa. |
| [mappingType](p-schema-mappingtype.md) | Natura della mappatura dello schema sotto forma di stringa |
| [md5](p-schema-md5.md) | Il codice MD5 dello schema sotto forma di stringa esadecimale. |
| [spazio dei nomi](p-schema-namespace.md) | Spazio dei nomi dello schema sotto forma di stringa. |
| [radice](p-schema-root.md) | Elemento principale dello schema o null se non è definito. |
| [userDescription](p-schema-userdescription.md) | Descrizione dello schema sotto forma di stringa. |

## Funzioni

**Disponibile in:**

* Gestione dei contenuti
* Proprietà di consegna
* Regola di tipologia
* JSSP
* Metodo SOAP
* WebApp
* Flusso di lavoro
