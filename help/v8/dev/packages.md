---
title: Utilizzo dei pacchetti di dati
description: Utilizzo dei pacchetti di dati
feature: Data Management, Package Export/Import
role: Developer
level: Intermediate, Experienced
source-git-commit: 8b537c723335ea98eb39bfbc3a4f1df09861aaea
workflow-type: tm+mt
source-wordcount: '1963'
ht-degree: 0%

---

# Utilizzare i pacchetti di dati{#data-packages}

## Introduzione ai pacchetti {#gs-data-packages}

Puoi utilizzare i pacchetti di dati per esportare e importare le impostazioni e i dati personalizzati della piattaforma. Un pacchetto può contenere diversi tipi di configurazioni e componenti, filtrati o meno.

Nei pacchetti di dati di Campaign, le entità del database Adobe Campaign vengono visualizzate in file XML. In un pacchetto, ogni entità è rappresentata con tutti i suoi dati.

Il principio di **pacchetti di dati** esporta una configurazione di dati e la integra in un altro ambiente Adobe Campaign. Scopri come mantenere un set coerente di pacchetti di dati in questo [sezione](#data-package-best-practices).

### Tipi di pacchetti {#types-of-packages}

In Adobe Campaign puoi utilizzare tre tipi di pacchetti: pacchetti utente, pacchetti piattaforma e pacchetti amministratore.

* A **pacchetto utente** consente di selezionare l&#39;elenco di entità da esportare. Questo tipo di pacchetto gestisce le dipendenze e controlla gli errori.
* A **pacchetto piattaforma** include tutte le risorse tecniche aggiunte (non standard): schemi, codice JavaScript, ecc.
* Un **pacchetto di amministrazione** include tutti i modelli e gli oggetti business aggiunti (non standard): modelli, librerie, ecc.

>[!CAUTION]
>
>Il **piattaforma** e **admin** i pacchetti contengono un elenco predefinito di entità da esportare. Ogni entità è collegata a condizioni di filtro che consentono di rimuovere le risorse pronte all’uso del pacchetto creato.

## Struttura dei dati {#data-structure}

La descrizione di un pacchetto di dati è un documento XML strutturato conforme alla grammatica del **xrk:navtree** schema dati, come nell’esempio seguente:

```xml
<package>
  <entities schema="nms:recipient">
    <recipient email="john.smith@adobe.com" lastName="Smith" firstName="John">      
      <folder _operation="none" name="nmsRootFolder"/>      
      <company _operation="none" name="Adobe"/>
    </recipient>
  </entities>
  <entities schema="sfa:company">
    <company name="Adobe">
      <location city="London" zipCode="W11 2BQ"/>
    </company>
  </entities>
</package>
```

Il documento XML deve iniziare e terminare con `<package>` elemento. Qualsiasi `<entities>` elementi che seguono distribuiscono i dati per tipo di documento. Un `<entities>` contiene i dati del pacchetto nel formato dello schema di dati immesso nel **schema** attributo. I dati in un pacchetto non devono contenere chiavi interne non compatibili tra le basi, ad esempio chiavi generate automaticamente (**autopk** opzionale).

Nel nostro esempio, i join sul `folder` e `company` i collegamenti sono stati sostituiti dai tasti &quot;di alto livello&quot; nelle tabelle di destinazione:

```xml
<recipient>
  <folder _operation="none" name="nmsRootFolder"/>
  <company _operation="none" name="Adobe"/>
</recipient>
```

Il `operation` attributo con il valore `none` definisce un collegamento di riconciliazione.

Un pacchetto di dati può essere creato manualmente da qualsiasi editor di testo. È necessario assicurarsi che la struttura del documento XML sia conforme `xtk:navtree` schema dati. La console client dispone di un modulo di esportazione e importazione del pacchetto dati.

## Esporta pacchetti {#export-packages}

I pacchetti possono essere esportati in tre modi diversi:

* Utilizza il **[!UICONTROL Package Export]** assistente per esportare un set di oggetti in un singolo pacchetto. [Ulteriori informazioni](#export-a-set-of-objects-in-a-package)
* Per esportare un **oggetto singolo**, fai clic con il pulsante destro del mouse su di esso e seleziona **[!UICONTROL Actions > Export in a package]**.
* Utilizza il **Definizioni dei pacchetti** per creare una struttura di package in cui aggiungere oggetti da esportare successivamente in un package. [Ulteriori informazioni](#manage-package-definitions)

Una volta esportato un pacchetto, puoi importarlo insieme a tutte le entità aggiunte in un’altra istanza di Campaign.

### Esportare un set di oggetti in un pacchetto {#export-a-set-of-objects-in-a-package}

Per esportare un set di oggetti in un pacchetto di dati, eseguire la procedura seguente:

1. Passa all’assistente per l’esportazione del pacchetto tramite **[!UICONTROL Tools > Advanced > Export package...]** menu dell&#39;explorer.
1. Seleziona la [tipi di colli](#types-of-packages).

   ![](assets/package_type.png)

1. Fai clic su **Aggiungi** per selezionare le entità da esportare come pacchetto.

   >[!CAUTION]
   >
   >Se si esporta un **[!UICONTROL Offer category]**, **[!UICONTROL Offer environment]**, **[!UICONTROL Program]** o **[!UICONTROL Plan]** digita la cartella, non selezionare mai la cartella **xtk:cartella** poiché alcuni dati potrebbero andare persi. Seleziona l’entità che corrisponde alla cartella: **nms:offerCategory** per le categorie di offerta, **nms:offerEnv** per gli ambienti di offerta, **nms:programma** per i programmi, e **nms:piano** per i piani.

   Il meccanismo di dipendenza controlla la sequenza di esportazione delle entità. Per ulteriori informazioni, consulta [Gestione delle dipendenze](#managing-dependencies).

1. Clic **[!UICONTROL Next]** e definiscono la query di filtro in base al tipo di documento da estrarre. È necessario configurare la clausola di filtro per l&#39;estrazione dei dati.

   >[!NOTE]
   >
   >L’editor delle query viene presentato in [questa sezione](../../platform/using/about-queries-in-campaign.md).

1. Clic **[!UICONTROL Next]** e selezionare l&#39;ordinamento dei dati esportati.

1. Visualizza l’anteprima dei dati da estrarre per verificare la configurazione.

1. L’ultima pagina dell’assistente all’esportazione del pacchetto ti consente di avviare l’esportazione. I dati verranno memorizzati nel file indicato nella **[!UICONTROL File]** campo.

### Gestire le dipendenze {#manage-dependencies}

Il processo di esportazione tiene traccia dei collegamenti tra i vari elementi esportati. Questo meccanismo è definito da due regole:

* oggetti collegati a un collegamento con un `own` o `owncopy` l&#39;integrità del tipo viene esportata nello stesso pacchetto dell&#39;oggetto esportato.
* oggetti collegati a un collegamento con un `neutral` o `define` l&#39;integrità del tipo (collegamento definito) deve essere esportata separatamente.

>[!NOTE]
>
>I tipi di integrità collegati agli elementi dello schema sono definiti in [questa pagina](database-links.md).

#### Esportare una campagna {#export-a-campaign}

Di seguito è riportato un esempio di come esportare una campagna. La campagna di marketing da esportare contiene:
* a `MyTask`attività
* a `campaignWorkflow` workflow nella cartella seguente: **[!UICONTROL Administration > Production > Technical workflows > Campaign processes > MyWorkflow]**.

L’attività e il flusso di lavoro vengono esportati nello stesso pacchetto della campagna, in quanto gli schemi corrispondenti sono collegati da collegamenti con un `own` integrità del tipo.

Il contenuto del pacchetto è:

```xml
<?xml version='1.0'?>
<package author="Administrator (admin)" buildNumber="7974" buildVersion="7.1" img=""
label="" name="" namespace="" vendor="">
 <desc></desc>
 <version buildDate="2013-01-09 10:30:18.954Z"/>
 <entities schema="nms:operation">
  <operation duration="432000" end="2013-01-14" internalName="OP1" label="MyCampaign"
  modelName="opEmpty" start="2013-01-09">
   <controlGroup>
    <where filteringSchema=""/>
   </controlGroup>
   <seedList>
    <where filteringSchema="nms:seedMember"></where>
    <seedMember internalName="SDM1"></seedMember>
   </seedList>
   <parameter useAsset="1" useBudget="1" useControlGroup="1" useDeliveryOutline="1"
   useDocument="1" useFCPValidation="0" useSeedMember="1" useTask="1"
   useValidation="1" useWorkflow="1"></parameter>
   <fcpSeed>
    <where filteringSchema="nms:seedMember"></where>
   </fcpSeed>
   <owner _operation="none" name="admin" type="0"/>
   <program _operation="none" name="nmsOperations"/>
   <task end="2013-01-17 10:07:51.000Z" label="MyTask" name="TSK2" start="2013-01-16 10:07:51.000Z"
   status="1">
    <owner _operation="none" name="admin" type="0"/>
    <operation _operation="none" internalName="OP1"/>
    <folder _operation="none" name="nmsTask"/>
   </task>
   <workflow internalName="WKF12" label="CampaignWorkflow" modelName="newOpEmpty"
   order="8982" scenario-cs="Notification of the workflow supervisor (notifySupervisor)"
   schema="nms:recipient">
    <scenario internalName="notifySupervisor"/>
    <desc></desc>
    <folder _operation="none" name="Folder4"/>
    <operation _operation="none" internalName="OP1"/>
   </workflow>
  </operation>
 </entities>
</package>   
```

L’affiliazione a un tipo di pacchetto è definita in uno schema con `@pkgAdmin and @pkgPlatform` attributo. Entrambi questi attributi ricevono un’espressione XTK che definisce le condizioni di affiliazione al pacchetto.

```xml
<element name="offerEnv" img="nms:offerEnv.png" 
template="xtk:folder" pkgAdmin="@id != 0">
```

Infine, la `@pkgStatus` attribute consente di definire le regole di esportazione per questi elementi o attributi. A seconda del valore dell’attributo, l’elemento o l’attributo si trova nel pacchetto esportato. I tre valori possibili per questo attributo sono:

* `never`: non esporta il campo o il collegamento
* `always`: forza l’esportazione per questo campo
* `preCreate`: autorizza la creazione dell’entità collegata

>[!NOTE]
>
>Il `preCreate` il valore è ammesso solo per gli eventi di tipo collegamento. Ti consente di creare o puntare a un’entità non ancora caricata nel pacchetto esportato.

## Gestire le definizioni dei pacchetti {#manage-package-definitions}

Le definizioni dei pacchetti consentono di creare una struttura di pacchetti in cui aggiungere entità che verranno esportate successivamente in un singolo pacchetto. Potrai quindi importare questo pacchetto e tutte le entità aggiunte in un’altra istanza di Campaign.

**Argomenti correlati:**

* [Creare una definizione di pacchetto](#create-a-package-definition)
* [Aggiungere entità a una definizione di pacchetto](#add-entities-to-a-package-definition)
* [Configurare la generazione delle definizioni dei pacchetti](#configure-package-definitions-generation)
* [Esportare pacchetti da una definizione di pacchetto](#export-packages-from-a-package-definition)

### Creare una definizione di pacchetto {#create-a-package-definition}

È possibile accedere alle definizioni dei pacchetti da **[!UICONTROL Administration > Configuration > Package management > Package definitions]** menu.

Per creare una definizione di pacchetto, fare clic su **[!UICONTROL New]** , quindi inserire le informazioni generali sulla definizione del pacchetto.

![](assets/packagedefinition_create.png)

È quindi possibile aggiungere entità alla definizione del pacchetto ed esportarla in un pacchetto di file XML.

**Argomenti correlati:**

* [Aggiungere entità a una definizione di pacchetto](#add-entities-to-a-package-definition)
* [Configurare la generazione delle definizioni dei pacchetti](#configure-package-definitions-generation)
* [Esportare pacchetti da una definizione di pacchetto](#export-packages-from-a-package-definition)

### Aggiungere entità a una definizione di pacchetto {#add-entities-to-a-package-definition}

In **[!UICONTROL Content]** , fare clic sulla scheda **[!UICONTROL Add]** per selezionare le entità da esportare con il pacchetto. Le best practice per la selezione delle entità sono presentate in [questa sezione](#export-a-set-of-objects-in-a-package).

![](assets/packagedefinition_addentities.png)

Le entità possono essere aggiunte a una definizione di pacchetto direttamente dalla loro posizione nell’istanza. A questo scopo, segui la procedura indicata di seguito:

1. Fai clic con il pulsante destro del mouse sull’entità desiderata, quindi seleziona **[!UICONTROL Actions > Export in a package]**.

1. Seleziona **[!UICONTROL Add to a package definition]**, quindi seleziona la definizione del pacchetto a cui desideri aggiungere l’entità.

1. L’entità viene aggiunta alla definizione del pacchetto, verrà esportata con il pacchetto (vedi [questa sezione](#export-packages-from-a-package-definition)).

### Configurare la generazione delle definizioni dei pacchetti {#configure-package-definitions-generation}

La generazione del pacchetto può essere configurata dalla definizione del pacchetto **[!UICONTROL Content]** scheda. A questo scopo, fai clic su **[!UICONTROL Generation parameters]** collegamento.

![](assets/packagedefinition_generationparameters.png)

* Utilizza il **[!UICONTROL Include the definition]** per includere la definizione attualmente utilizzata nella definizione del pacchetto.
* Utilizza il **[!UICONTROL Include an installation script]** opzione per aggiungere uno script javascript da eseguire all’importazione del pacchetto. Se selezionata, **[!UICONTROL Script]** viene aggiunta nella schermata di definizione del pacchetto.
* Utilizza il **[!UICONTROL Include default values]** per aggiungere i valori di tutti gli attributi delle entità al pacchetto.

  Questa opzione non è selezionata per impostazione predefinita, al fine di evitare lunghe esportazioni. Ciò significa che, per impostazione predefinita, gli attributi delle entità con valori predefiniti (&quot;stringa vuota&quot;, &quot;0&quot; e &quot;false&quot; se non sono definiti altrimenti nello schema) non vengono aggiunti al pacchetto e quindi non esportati.

  >[!CAUTION]
  >
  >Se l’istanza in cui viene importato il pacchetto contiene entità identiche a quelle del pacchetto (ad esempio con lo stesso ID esterno), i relativi attributi non verranno aggiornati. Ciò può verificarsi se gli attributi dell’istanza precedente dispongono di valori predefiniti, in quanto non sono inclusi nel pacchetto. In tal caso, selezionare **[!UICONTROL Include default values]** L’opzione impediva l’unione delle versioni, in quanto tutti gli attributi dell’istanza precedente venivano esportati con il pacchetto.

### Esportare pacchetti da una definizione di pacchetto {#export-packages-from-a-package-definition}

Per esportare un pacchetto da una definizione di pacchetto, effettua le seguenti operazioni:

1. Seleziona la definizione del pacchetto da esportare, fai clic su **[!UICONTROL Actions]** e selezionare **[!UICONTROL Export the package]**.
1. Controllare il nome e il percorso del file esportato.
1. Fai clic su **[!UICONTROL Start]** per avviare l&#39;esportazione.

## Importazione dei pacchetti {#import-packages}

L’assistente all’importazione del pacchetto è accessibile tramite il menu principale **[!UICONTROL Tools > Advanced > Import package]** della console client.

### Installare un pacchetto da un file {#install-a-package-from-a-file}

Per importare un pacchetto di dati esistente, effettua le seguenti operazioni:

1. Accedere all&#39;Assistente all&#39;importazione tramite il menu principale **[!UICONTROL Tools > Advanced > Import package]** della console client.
1. Selezionare il file XML e fare clic su **[!UICONTROL Open]**.

Il contenuto del pacchetto da importare viene quindi visualizzato nella sezione centrale dell’editor.

Clic **[!UICONTROL Next]** e **[!UICONTROL Start]** per avviare l&#39;importazione.

### Installare un pacchetto integrato {#install-a-standard-package}

Pacchetti incorporati (alias pacchetti standard) quando Adobe Campaign è configurato. A seconda delle autorizzazioni, del modello di distribuzione e dell’offerta di prodotto, puoi importare nuovi pacchetti standard.

Fare riferimento al contratto di licenza per verificare quali pacchetti è possibile installare.

## Best practice relative ai pacchetti dati {#data-package-best-practices}

Questa sezione descrive come organizzare i pacchetti di dati in modo coerente per l’intera durata del progetto.


### Versioni

È sempre necessario importare all’interno della stessa versione della piattaforma. Devi verificare di distribuire i pacchetti tra due istanze che hanno la stessa build. Non forzare mai l’importazione e aggiorna sempre prima la piattaforma (se la build è diversa).

>[!IMPORTANT]
>
>L’importazione tra versioni diverse non è supportata da Adobe.

Presta attenzione allo schema e alla struttura del database. L’importazione di un pacchetto con schema deve essere seguita dalla generazione dello schema.

### Tipi di pacchetti {#package-types}

Per iniziare, definisci diversi tipi di pacchetti. Vengono utilizzati solo quattro tipi:

**Entità**

* Tutti gli elementi specifici &quot;xtk&quot; e &quot;nms&quot; in Adobe Campaign come schemi, moduli, cartelle, modelli di consegna, ecc.
* Puoi considerare un’entità sia come elemento &quot;admin&quot; che come elemento &quot;platform&quot;.
* Non includere più di un’entità in un pacchetto durante il caricamento in un’istanza Campaign.

Se devi distribuire la configurazione su una nuova istanza, puoi importare tutti i pacchetti di entità.

**Funzioni**

Questo tipo di pacchetto:
* Risponde a un requisito/specifica del cliente.
* Contiene una o più funzionalità.
* Deve contenere tutte le dipendenze per poter eseguire la funzionalità senza altri pacchetti.

**Campagne**

Questo pacchetto non è obbligatorio. A volte è utile creare un tipo specifico per tutte le campagne, anche se una campagna può essere vista come una funzione.

**Aggiornamenti**

Una volta configurata, una funzione può essere esportata in un altro ambiente. Ad esempio, il pacchetto può essere esportato da un ambiente di sviluppo a un ambiente di test. In questo test, viene rilevato un difetto. Innanzitutto, deve essere corretto nell’ambiente di sviluppo. Applicare quindi il cerotto sulla piattaforma di prova.

La prima soluzione consiste nell&#39;esportare di nuovo l&#39;intera funzionalità. Tuttavia, per evitare qualsiasi rischio (aggiornamento di elementi indesiderati), è più sicuro disporre di un pacchetto contenente solo la correzione.

Ecco perché consigliamo di creare un pacchetto di &quot;aggiornamento&quot; contenente un solo tipo di entità della funzione.

Un aggiornamento potrebbe non essere solo una correzione, ma anche un nuovo elemento del pacchetto entità/funzione/campagna. Per evitare di distribuire l’intero pacchetto, puoi esportare un pacchetto di aggiornamento.

### Convenzioni di denominazione {#data-package-naming}

Ora che i tipi sono definiti, è necessario specificare una convenzione di denominazione. Adobe Campaign non consente di creare sottocartelle per le specifiche dei pacchetti, il che significa che i numeri sono la soluzione migliore per rimanere organizzati. I numeri precedono i nomi dei pacchetti.

Ad esempio, puoi utilizzare la seguente convenzione:

* Entità: da 1 a 99
* Effigie: da 100 a 199
* Campagna: da 200 a 299
* Aggiornamento: da 5000 a 5999

#### Ordine pacchetti entità {#entity-packages-order}

Per facilitare l’importazione, i pacchetti di entità devono essere ordinati così come devono essere importati.

Ad esempio:

* 001 - Schema
* 002 - Modulo
* 003 - Immagini
* ecc.

>[!NOTE]
>
>Forms deve essere importato solo **dopo** aggiornamenti dello schema.


#### Documentazione del pacchetto {#package-documentation}

Quando aggiorni un pacchetto, devi sempre inserire un commento nel campo di descrizione per descrivere nel dettaglio eventuali modifiche e motivi (ad esempio, &quot;aggiungere un nuovo schema&quot; o &quot;correggere un difetto&quot;).

Si consiglia inoltre di immettere la data dell’aggiornamento.

>[!IMPORTANT]
>
>Il campo descrizione può contenere solo un massimo di 2.000 caratteri.

