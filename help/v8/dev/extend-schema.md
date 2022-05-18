---
title: Estendere gli schemi di Campaign
description: Scopri come estendere gli schemi di Campaign
exl-id: e4dcb228-0683-437a-88cd-bd7ed33da921
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 2%

---

# Estendere uno schema{#extend-schemas}

In qualità di utente tecnico, puoi personalizzare il modello dati di Campaign per soddisfare le esigenze della tua implementazione: aggiungere elementi a uno schema esistente, modificare un elemento in uno schema o eliminare elementi.

I passaggi chiave per personalizzare il modello dati di Campaign sono i seguenti:

1. Creare uno schema di estensione
1. Aggiorna il database di Campaign
1. Adattare il modulo di input

>[!CAUTION]
>Lo schema predefinito non deve essere modificato direttamente. Se è necessario adattare uno schema incorporato, è necessario estenderlo.

![](../assets/do-not-localize/glass.png) Per una migliore comprensione delle tabelle integrate di Campaign e della loro interazione, consulta [questa pagina](datamodel.md). Vedi anche consigli durante la creazione di un nuovo schema in [questa pagina](create-schema.md).

Per estendere uno schema, segui i passaggi seguenti:

1. Passa a **[!UICONTROL Administration > Configuration > Data schemas]** in Esplora risorse.
1. Fai clic sul pulsante **Nuovo** e seleziona **[!UICONTROL Extend the data in a table using an extension schema]**.

   ![](assets/extend-schema-option.png)

1. Identifica lo schema incorporato da estendere e selezionarlo.

   ![](assets/extend-schema-select.png)

   Per convenzione, denomina lo schema di estensione come lo schema incorporato e utilizza uno spazio dei nomi personalizzato.  Alcuni namespace sono interni solo. [Ulteriori informazioni](schemas.md#reserved-namespaces)

   ![](assets/extend-schema-validate.png)

1. Una volta nell’editor dello schema, aggiungi gli elementi necessari utilizzando il menu contestuale e salva.

   ![](assets/extend-schema-edit.png)

   Nell’esempio seguente, aggiungiamo la variabile **annoIscrizione** inserisci un limite di lunghezza per il cognome (questo limite sovrascrive quello predefinito) e rimuovi la data di nascita dallo schema incorporato.

   ![](assets/extend-schema-sample.png)

   ```
   <srcSchema created="YYYY-MM-DD" desc="Recipient table" extendedSchema="nms:recipient"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient" lastModified="YYYY-MM-DD"
           mappingType="sql" name="recipient" namespace="cus" xtkschema="xtk:srcSchema">
    <element desc="Recipient table" img="nms:recipient.png" label="Recipients" labelSingular="Recipient" name="recipient">
       <attribute label="Member since" name="MembershipYear" type="long"/>
       <attribute length="50" name="lastName"/>
       <attribute _operation="delete" name="birthDate"/>
   </element>
   </srcSchema>
   ```

1. Disconnetti e riconnettiti a Campaign per controllare l’aggiornamento della struttura dello schema nel **[!UICONTROL Structure]** scheda .

   ![](assets/extend-schema-structure.png)

1. Aggiorna la struttura del database per applicare le modifiche. [Ulteriori informazioni](update-database-structure.md)

1. Una volta implementate le modifiche nel database, è possibile adattare il modulo di input del destinatario per rendere visibili le modifiche. [Ulteriori informazioni](forms.md)
