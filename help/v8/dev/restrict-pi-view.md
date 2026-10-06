---
title: Limitare la visualizzazione di dati personali
description: Scopri come limitare la visualizzazione delle PI
feature: PI, Privacy, Configuration
role: Developer
level: Intermediate, Experienced
exl-id: 1b833745-71d7-430d-ac7d-c830c78ea232
TQID: 'https://experienceleague.adobe.com/MRPX97V84a4r1eVIIyrU2Z7ZwiNkn-RHMZGQG3YV9ec'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
    internal-label: Schemas
  - id: a7760dfc-5c44-4d77-bb68-c50b1e265c93
    internal-label: Security and privacy
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
    internal-label: PI
  - id: ac9c0a9c-8a76-4419-bd64-9c34c5782666
    internal-label: Privacy
  - id: a14877cc-63b1-41d9-bf0b-5f97cadd0417
    internal-label: Configuration guidelines
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 7fd43a8d3d6afe9f4d3fb000d925cc6185ba9f40
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 2%
---
# Limitare la visualizzazione di dati personali{#restricting-pii-view}

## Panoramica {#overview}

Se hai bisogno che gli utenti marketing possano accedere ai record di dati ma non desideri che visualizzino le informazioni personali del destinatario (PI), come nome, cognome o indirizzo e-mail, applica le linee guida seguenti per proteggere la privacy e impedire che i dati vengano utilizzati in modo improprio dagli operatori regolari delle campagne.

## Implementazione {#implementation}

Un attributo specifico che può essere applicato a qualsiasi elemento o attributo è stato aggiunto agli schemi. Completa l&#39;attributo esistente **[!UICONTROL visibleIf]**. Attributo: **[!UICONTROL accessibleIf]**. Quando contiene un&#39;espressione XTK correlata al contesto utente corrente, può sfruttare **[!UICONTROL HasNamedRight]** o **[!UICONTROL $(login)]**, ad esempio.

Di seguito è riportato un esempio di estensione dello schema del destinatario, con questo utilizzo:

```
<srcSchema desc="Recipient table (profiles" entitySchema="xtk:srcSchema" extendedSchema="xxl:nmsRecipientXl"
           img="nms:recipient.png" label="Recipients" labelSingular="Recipient"
           name="recipient" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Recipient table (profiles" img="xxl:recipient.png" label="Recipients"
           labelSingular="Recipient" name="recipient">
    <attribute name="firstName" accessibleIf="$(login)=='admin'"/>
    <attribute name="lastName" visibleIf="$(login)=='admin'"/>
    <attribute name="email" accessibleIf="$(login)=='admin'"/>
  </element>
</srcSchema>
```

Le proprietà principali sono:

* **[!UICONTROL visibleIf]**: nasconde i campi dai metadati, pertanto non è possibile accedervi in una visualizzazione schema o in una selezione di colonne oppure in un [Generatore di espressioni](../../v8/start/filter-conditions.md#list-of-functions). Tuttavia, se il nome del campo viene immesso manualmente in un’espressione, il valore non viene nascosto.
* **[!UICONTROL accessibleIf]**: nasconde i dati (sostituendoli con valori vuoti) dalla query risultante. Se visibleIf è vuoto, ottiene la stessa espressione di **[!UICONTROL accessibleIf]**.

Di seguito sono riportate le conseguenze dell’utilizzo di questo attributo in Campaign:

* I dati non verranno visualizzati utilizzando un editor di query generico nella console,
* I dati non saranno visibili negli elenchi di panoramica e negli elenchi di record (console).
* I dati diventeranno di sola lettura nella vista dettagliata.
* I dati saranno utilizzabili solo all’interno dei filtri (il che significa che utilizzando alcune strategie di dicotomia è ancora possibile indovinare i valori).
* Qualsiasi espressione creata utilizzando un campo con restrizioni diventa limitata a: lower(@email) diventa accessibile quanto @email.
* In un flusso di lavoro, puoi aggiungere la colonna con restrizioni alla popolazione target come colonna aggiuntiva della transizione, ma non è ancora accessibile agli utenti di Adobe Campaign.
* Quando si archivia la popolazione target in un gruppo (elenco), le caratteristiche dei campi memorizzati sono le stesse dell’origine dei dati.
* Per impostazione predefinita, i dati non sono accessibili al codice JS.

>[!IMPORTANT]
>
>L&#39;utilizzo dell&#39;attributo **accessibleIf** nei parametri critici (ad esempio quelli nelle chiavi composite) può causare errori per gli utenti che non sono autorizzati a leggere i dati a causa di dati nascosti. Questo può causare errori di query o comportamenti imprevisti. Assicurati che i parametri essenziali siano accessibili per evitare interruzioni.

## Consigli {#recommendations}

In ogni consegna, gli indirizzi e-mail vengono copiati nelle tabelle **[!UICONTROL broadLog]** e **[!UICONTROL forecastLog]**: di conseguenza, anche questi campi devono essere protetti.

Di seguito è riportato un esempio di estensione della tabella di registro per implementare questo:

```
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:broadLogRcp" img="nms:broadLog.png"
           label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:broadLog.png" label="Recipient delivery logs" labelSingular="Recipient delivery log"
           name="broadLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema desc="Delivery messages being prepared." entitySchema="xtk:srcSchema"
           extendedSchema="nms:tmpBroadcast" img="" label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast" namespace="sec" xtkschema="xtk:srcSchema">
  <element desc="Delivery messages being prepared." label="Messages being prepared"
           labelSingular="Message" name="tmpBroadcast">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
<srcSchema entitySchema="xtk:srcSchema" extendedSchema="nms:excludeLogRcp" img="nms:excludeLog.png"
           label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp" namespace="sec" xtkschema="xtk:srcSchema">
  <element img="nms:excludeLog.png" label="Recipient exclusion logs" labelSingular="Recipient exclusion log"
           name="excludeLogRcp">
    <attribute accessibleIf="$(login)=='admin'" name="address"/>
  </element>
</srcSchema>
```

>[!CAUTION]
>
>Questa restrizione si applica solo agli utenti non tecnici e non isola i dati: un utente tecnico, con le relative autorizzazioni, può recuperare i dati.
