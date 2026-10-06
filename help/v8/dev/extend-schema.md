---
title: Estendere gli schemi di Campaign
description: Scopri come estendere gli schemi di Campaign
feature: Schema Extension, Data Model
role: Developer
level: Intermediate, Experienced
exl-id: e4dcb228-0683-437a-88cd-bd7ed33da921
TQID: 'https://experienceleague.adobe.com/KxMO1S6yuFZUJAUIeSaF-J-s-SBLoODGWcOxImPONg0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
    internal-label: Schemas
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a72a22e0-8c8d-4019-ba42-3f2644aa91a3
    internal-label: Schema extension
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 2%
---
# Estendere uno schema{#extend-schemas}

In qualità di utente tecnico, puoi personalizzare il modello dati di Campaign per soddisfare le esigenze della tua implementazione: puoi aggiungere elementi a uno schema esistente, modificare un elemento in uno schema o eliminare elementi.

I passaggi chiave per personalizzare il modello dati di Campaign sono:

1. Creare uno schema di estensione
1. Aggiornare il database di Campaign
1. Adattare il modulo di input

>[!CAUTION]
>Lo schema incorporato non deve essere modificato direttamente. Se devi adattare uno schema integrato, devi estenderlo.

Per informazioni sulle tabelle integrate di Campaign e sulla loro interazione, consulta [questa pagina](datamodel.md). Consulta anche i consigli durante la creazione di un nuovo schema in [questa pagina](create-schema.md).

Per estendere uno schema, effettua le seguenti operazioni:

1. Passare alla cartella **[!UICONTROL Administration > Configuration > Data schemas]** in Explorer.
1. Fare clic sul pulsante **Nuovo** e selezionare **[!UICONTROL Extend the data in a table using an extension schema]**.

   ![](assets/extend-schema-option.png)

1. Identifica lo schema integrato da estendere e selezionalo.

   ![](assets/extend-schema-select.png)

   Per convenzione, assegna allo schema di estensione lo stesso nome dello schema incorporato e utilizza uno spazio dei nomi personalizzato.  Alcuni spazi dei nomi sono solo interni. [Ulteriori informazioni](schemas.md#reserved-namespaces)

   ![](assets/extend-schema-validate.png)

1. Una volta nell’editor dello schema, aggiungi gli elementi necessari utilizzando il menu contestuale e salva.

   ![](assets/extend-schema-edit.png)

   Nell&#39;esempio seguente viene aggiunto l&#39;attributo **MembershipYear**, viene inserito un limite di lunghezza per il cognome (questo limite sovrascriverà quello predefinito) e la data di nascita viene rimossa dallo schema predefinito.

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

1. Disconnettersi e riconnettersi a Campaign per verificare l’aggiornamento della struttura dello schema nella scheda **[!UICONTROL Structure]**.

   ![](assets/extend-schema-structure.png)

1. Aggiorna la struttura del database per applicare le modifiche. [Ulteriori informazioni](update-database-structure.md)

1. Una volta implementate le modifiche nel database, è possibile adattare il modulo di input del destinatario per rendere visibili le modifiche. [Ulteriori informazioni](forms.md)
