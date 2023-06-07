---
title: Creare un nuovo schema in Campaign
description: Scopri come creare un nuovo schema in Campaign
feature: Schema Extension
role: Developer
level: Intermediate, Experienced
exl-id: 796af848-b537-4b8d-a601-fe0628a1fc83
source-git-commit: 290f4e9a0d13ef49caacb7a128ccc266bafd5e69
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 2%

---

# Crea un nuovo schema{#create-new-schema}

Per modificare, creare e configurare gli schemi, fai clic sul pulsante **[!UICONTROL Administration > Configuration > Data schemas]** della console client di Adobe Campaign.

>[!NOTE]
>
>Gli schemi di dati incorporati possono essere eliminati solo da un amministratore della console Adobe Campaign.

![](assets/schema_navtree.png)

Il **[!UICONTROL Edit]** La scheda mostra il contenuto XML di uno schema:

![](assets/schema_edition.png)

>[!NOTE]
>
>Il controllo di modifica &quot;Nome&quot; consente di immettere la chiave dello schema composta dal nome e dallo spazio dei nomi. Gli attributi &quot;name&quot; e &quot;namespace&quot; dell&#39;elemento principale dello schema vengono aggiornati automaticamente nell&#39;area di modifica XML dello schema. Alcuni spazi dei nomi sono solo interni. [Ulteriori informazioni](schemas.md#reserved-namespaces)

Il **[!UICONTROL Preview]** La scheda genera automaticamente lo schema esteso:

![](assets/schema_edition2.png)

>[!NOTE]
>
>Quando lo schema di origine viene salvato, viene avviata automaticamente la generazione dello schema esteso.

Se devi controllare la struttura completa di uno schema, puoi utilizzare **[!UICONTROL Preview]** scheda. Se lo schema è stato esteso, potrai visualizzarne tutte le estensioni. A titolo complementare, la **[!UICONTROL Documentation]** Nella scheda vengono visualizzati tutti gli attributi e gli elementi dello schema e le relative proprietà (SQL Field, type/length, label, description). Il **[!UICONTROL Documentation]** Questa scheda si applica solo agli schemi generati.

## Caso d’uso: creare una tabella di contratti {#example--creating-a-contract-table}

Nell&#39;esempio seguente viene creata una nuova tabella per **contratti** nel database. Questa tabella consente di memorizzare i nomi e i cognomi e gli indirizzi e-mail dei titolari e dei co-titolari per ogni contratto.

A questo scopo, devi creare lo schema della tabella e aggiornare la struttura del database per generare la tabella corrispondente. Di seguito sono elencati i passaggi dettagliati.

1. Modifica il **[!UICONTROL Administration > Configuration > Data schemas]** nodo della struttura Adobe Campaign e fai clic su **[!UICONTROL New]**.
1. Scegli la **[!UICONTROL Create a new table in the data template]** e fai clic su **[!UICONTROL Next]** .

   ![](assets/create_new_schema.png)

1. Specificare un nome per la tabella e uno spazio dei nomi.

   ![](assets/create_new_param.png)

   >[!NOTE]
   >
   >Per impostazione predefinita, gli schemi creati dagli utenti vengono memorizzati nello spazio dei nomi &quot;cus&quot;. Per ulteriori informazioni, consulta [Identificazione di uno schema](extend-schema.md#identification-of-a-schema).

1. Crea il contenuto della tabella. È consigliabile utilizzare l’assistente dedicato per verificare che non manchino impostazioni. A questo scopo, fai clic su **[!UICONTROL Insert]** e scegliere il tipo di impostazione da aggiungere.

   ![](assets/create_new_content.png)

1. Definire le impostazioni per la tabella dei contratti.

   Come best practice, crea la tabella nel database Cloud aggiungendo la `dataSource="nms:extAccount:ffda"` attributo. Questo attributo viene aggiunto per impostazione predefinita durante la creazione di una nuova tabella.

   ```
   <srcSchema created="YYYY-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" lastModified="YYYY-MM-DD HH:MM:SS.TZ"
           mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

   Aggiungere il tipo di enumerazione dei contratti.

   ```
   <srcSchema created="AA-MM-DD HH:MM:SS.TZ" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png" label="Contracts" labelSingular="Contract" AA-MM-DD HH:MM:SS.TZ"mappingType="sql" name="Contracts" namespace="cus" xtkschema="xtk:srcSchema">
      <enumeration basetype="byte" name="typeContract">
         <value label="Home" name="home" value="0"/>
         <value label="Car" name="car" value="1"/>
         <value label="Health" name="health" value="2"/>
         <value label="Pension fund" name="pension fund" value="2"/>
      </enumeration>
      <element dataSource="nms:extAccount:ffda" desc="Active contracts" img="crm:crm/mscrm/mscrm_account_16x16.png"
           label="Contracts" labelSingular="Contract" name="Contracts">
           <attribute name="holderName" label="Holder last name" type="string"/>
           <attribute name="holderFirstName" label="Holder first name" type="string"/>
           <attribute name="holderEmail" label="Holder email" type="string"/>
           <attribute name="co-holderName" label="Co-holder last name" type="string"/>           
           <attribute name="co-holderFirstName" label="Co-holder first name" type="string"/>           
           <attribute name="co-holderEmail" label="Co-holder email" type="string"/>    
           <attribute name="date" label="Subscription date" type="date"/>     
           <attribute name="noContract" label="Contract number" type="long"/> 
      </element>
   </srcSchema>
   ```

1. Salva lo schema e fai clic su **[!UICONTROL Structure]** per generare la struttura:

   ![](assets/configuration_structure.png)

1. Aggiorna la struttura del database per creare la tabella a cui verrà collegato lo schema. Per ulteriori informazioni al riguardo, consulta [questa sezione](update-database-structure.md).
