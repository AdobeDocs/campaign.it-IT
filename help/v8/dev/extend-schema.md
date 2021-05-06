---
solution: Campaign Classic
product: campaign
title: Estendere gli schemi di Campaign
description: Scopri come estendere gli schemi di Campaign
translation-type: tm+mt
source-git-commit: 779542ab70f0bf3812358884c698203bab98d1ce
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 5%

---

# Estendi uno schema{#extend-schemas}

Questo articolo descrive come configurare gli schemi di estensione per estendere il modello dati concettuale del database Adobe Campaign.

:lampadina: Per una migliore comprensione delle tabelle integrate di Campaign e della loro interazione, consulta [questa pagina](datamodel.md).

La struttura fisica e logica dei dati trasferiti nell’applicazione è descritta in XML. Obbedisce a una grammatica specifica di Adobe Campaign, denominata **schema**.

Uno schema è un documento XML associato a una tabella di database. Definisce la struttura dati e descrive la definizione SQL della tabella:

* Nome della tabella
* Campi
* Collegamenti ad altre tabelle

Descrive inoltre la struttura XML utilizzata per memorizzare i dati:

* Elementi e attributi
* Gerarchia degli elementi
* Tipi di elementi e attributi
* Valori predefiniti
* Etichette, descrizioni e altre proprietà.

Gli schemi consentono di definire un’entità nel database. Esiste uno schema per ogni entità.

## Sintassi degli schemi {#syntax-of-schemas}

L&#39;elemento principale dello schema è **`<srcschema>`**. Contiene i sottoelementi **`<element>`** e **`<attribute>`** .

Il primo sottoelemento **`<element>`** coincide con il livello principale dell’entità.

```
<srcSchema name="recipient" namespace="cus">
  <element name="recipient">  
    <attribute name="lastName"/>
    <attribute name="email"/>
    <element name="location">
      <attribute name="city"/>
   </element>
  </element>
</srcSchema>
```

>[!NOTE]
>
>L&#39;elemento principale dell&#39;entità ha lo stesso nome dello schema.

![](assets/schema_and_entity.png)

I tag **`<element>`** definiscono i nomi degli elementi di entità. **`<attribute>`** i tag dello schema definiscono i nomi degli attributi nei  **`<element>`** tag a cui sono stati collegati.

## Identificazione di uno schema {#identification-of-a-schema}

Uno schema di dati è identificato dal nome e dallo spazio dei nomi corrispondente.

Uno spazio dei nomi consente di raggruppare un set di schemi per area di interesse. Ad esempio, lo spazio dei nomi **cus** viene utilizzato per la configurazione specifica del cliente (**clienti**).

>[!CAUTION]
>
>Come standard, il nome dello spazio dei nomi deve essere conciso e deve contenere solo caratteri autorizzati in conformità alle regole di denominazione XML.
>
>Gli identificatori non devono iniziare con caratteri numerici.

Alcuni namespace sono riservati per le descrizioni delle entità di sistema necessarie per il funzionamento dell’applicazione Adobe Campaign:

* **xxl**: per quanto riguarda gli schemi di database cloud,
* **xtk**: per quanto riguarda i dati del sistema di piattaforma,
* **nl**: per quanto riguarda l&#39;utilizzazione globale della domanda,
* **nms**: per quanto riguarda la consegna (destinatario, consegna, tracciamento, ecc.),
* **ncm**: per quanto riguarda la gestione dei contenuti,
* **temperatura**: riservato agli schemi temporanei.

La chiave di identificazione di uno schema è una stringa creata utilizzando lo spazio dei nomi e il nome separati da due punti; ad esempio: **nms:recipient**.
