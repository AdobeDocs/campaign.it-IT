---
product: campaign
title: Aggiungere un’offerta in una pagina web
description: Scopri come aggiungere un’offerta in una pagina web
exl-id: 1eb0775a-5da9-4a27-aa7b-339372748f9c
source-git-commit: 6de5c93453ffa7761cf185dcbb9f1210abd26a0c
workflow-type: tm+mt
source-wordcount: '1455'
ht-degree: 0%

---

# Aggiungere un’offerta in una pagina web{#add-an-offer-in-web}

Per chiamare il motore di offerta in una pagina web, inserisci una chiamata a un codice JavaScript direttamente nella pagina. Questa chiamata restituisce il contenuto dell&#39;offerta in un elemento con targeting.

Lo script che richiama l’URL si presenta così:

```
<script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=" type="text/javascript"></script>
```

&quot;**env**&quot; riceve il nome interno dell&#39;ambiente live dedicato alle interazioni anonime.

Per presentare un’offerta, è necessario creare un ambiente e uno spazio di offerta in Adobe Campaign, quindi configurare la pagina HTML.

I seguenti casi d’uso descrivono le opzioni possibili per l’integrazione delle offerte tramite JavaScript.

## Opzione 1: Modalità HTML {#html-mode}

### Presentare un’offerta anonima {#presenting-an-anonymous-offer}

**Passaggio 1: Preparare il motore di offerta**

1. Apri l’interfaccia Adobe Campaign e prepara un ambiente anonimo.
1. Crea uno spazio di offerta collegato all’ambiente anonimo.
1. Crea un’offerta e la relativa rappresentazione collegata allo spazio dell’offerta.

**Passaggio 2: Aggiornare il contenuto della pagina HTML**

La pagina HTML deve includere un elemento con un attributo @id con il valore del nome interno dello spazio offerta creato (&quot;spazio nome interno&quot;). L’offerta verrà inserita in questo elemento tramite Interazione.

Nel nostro esempio, l’attributo @id riceve il valore &quot;i_SPC12&quot;, dove &quot;SPC12&quot; è il nome interno dello spazio di offerta creato in precedenza:

```
<div id="i_SPC12"></div>
```

Nel nostro esempio, l’URL per la chiamata dello script è il seguente (&quot;OE3&quot; è il nome interno dell’ambiente live):

```
<script id="interactionProposalScript" src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" type="text/javascript"></script>
```

>[!CAUTION]
>
>La `<script>` Il tag non deve chiudersi automaticamente.

Questa chiamata statica genera automaticamente una chiamata dinamica contenente tutti i parametri necessari al motore di offerta.

Questo comportamento ti consente di utilizzare più spazi di offerta sulla stessa pagina, per essere gestito da una singola chiamata al motore di offerta.

**Passaggio 3: Visualizza i risultati nella pagina HTML**

Il contenuto della rappresentazione dell’offerta viene restituito alla pagina HTML dal motore di offerta:

```
<div id="banner_header">
 <div id="i_SPC12">
   <table>
    <tbody>
        <tr>
            <td><h3>Fly to Japan!</h3></td>
        </tr>
        <tr>
            <td><img width="150px" src="https://instance.adobe.org/res/Track/874fdaf72ddc256b2d8260bb8ec3a104.jpg"></td>
            <td>
            <p>Discover Japan for 2 weeks at an unbelievable price!!</p>
            <p><b>2345 Dollars - All inclusive</b></p>
        </td>
        </tr>
    </tbody>
    </table>
 </div>
<script src="https://instance.adobe.org:8080/nl/interactionProposal.js?env=OE3" id="interactionProposalScript" type="text/javascript"></script>
</div>
```

### Presentare un’offerta identificata {#presenting-an-identified-offer}

Per presentare un&#39;offerta a un contatto identificato, il processo è simile a quello dettagliato [in questa sezione](#presenting-an-anonymous-offer).

Nel contenuto della pagina web, devi aggiungere il seguente script che identificherà il contatto durante la chiamata al motore di offerta:

```
<script type="text/javascript">
  interactionTarget = <contact_identifier>;
</script>
```

1. Vai allo spazio di offerta che verrà richiamato dalla pagina web, fai clic su **[!UICONTROL Advanced parameters]** e aggiungi una o più chiavi di identificazione.

   ![](assets/interaction_htmlmode_001.png)

   In questo esempio, la chiave di identificazione è composita in quanto si basa sia sull’e-mail che sul nome del destinatario.

1. Durante la visualizzazione della pagina web, la valutazione dello script ti consente di trasmettere l’ID destinatario al motore dell’offerta. Se l’ID è composito, i tasti vengono visualizzati nella stessa sequenza utilizzata nelle impostazioni avanzate e separati da un |

   Nell’esempio seguente, il contatto ha effettuato l’accesso al sito web ed è stato riconosciuto durante la chiamata al motore di offerta grazie alla relativa e-mail e nome.

   ```
   <script type="text/javascript">
     interactionTarget = myEmail|myName;
   </script>
   ```

### Utilizzare una funzione di rendering di HTML {#using-an-html-rendering-function}

Per generare automaticamente la rappresentazione dell’offerta HTML, puoi utilizzare una funzione di rendering.

1. Passa allo spazio di offerta e fai clic sul pulsante **[!UICONTROL Edit functions]** link.
1. Seleziona **[!UICONTROL Overload the HTML rendering function]**.
1. Vai a **[!UICONTROL HTML rendering]** , quindi inserisci le variabili che corrispondono ai campi definiti per il contenuto dell’offerta nello spazio dell’offerta.

   ![](assets/interaction_htmlmode_002.png)

   In questo esempio, l’offerta viene visualizzata sotto forma di banner in una pagina web, è composta da un’immagine su cui è possibile fare clic e da un titolo che corrisponde ai campi definiti nel contenuto dell’offerta.

## Opzione 2: Modalità XML {#xml-mode}

### Presentare un’offerta {#presenting-an-offer}

Campaign **Interazione** Il modulo ti consente di restituire un nodo XML alla pagina HTML che richiama il motore di offerta. Questo nodo XML può essere elaborato da funzioni da sviluppare sul lato cliente.

La chiamata al motore di offerta si presenta così:

```
<script type="text/javascript" id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=&cb="></script>
```

* &quot;**env**&quot; riceve il nome interno dell&#39;ambiente live.

* &quot;**cb**&quot; riceve il nome della funzione che leggerà il nodo XML restituito dal motore contenente le proposte (callback). Questo parametro è facoltativo.

* &quot;**t**&quot; riceve il valore del target, solo per un&#39;interazione identificata. Questo parametro può essere trasmesso anche con **actionTarget** variabile. Questo parametro è facoltativo.

* &quot;**c**&quot; riceve l&#39;elenco dei nomi interni delle categorie. Questo parametro è facoltativo.

* &quot;**th**&quot; riceve l&#39;elenco dei temi. Questo parametro è facoltativo.

* &quot;**gctx**&quot; riceve i dati della chiamata globali (contestuali) all&#39;intera pagina. Questo parametro è facoltativo.

Il nodo XML restituito si presenta così:

```
<propositions>
 <proposition id="" offer-id="" weight="" rank="" space="" div=""> //proposition identifiers
   ...XML content defined in Adobe Campaign...
 </proposition>
 ...
</propositions>
```

Il caso d’uso riportato di seguito descrive le configurazioni da eseguire in Adobe Campaign per abilitare la modalità XML, quindi mostra il risultato della chiamata al motore nella pagina HTML.

1. **Creare un ambiente e uno spazio di offerta**

   Per ulteriori informazioni sulla creazione di un ambiente, consulta [questa pagina](interaction-env.md).

   Per ulteriori informazioni sulla creazione di uno spazio di offerta, consulta [questa pagina](interaction-offer-spaces.md).

1. **Estendi lo schema delle offerte per aggiungere nuovi campi**

   Questo schema definisce i campi seguenti: Titolo numero 2 e prezzo.

   Il nome dello schema nell&#39;esempio è **cus:offer**

   ```
   <srcSchema _cs="Marketing offers (cus)" created="2013-01-18 17:14:20.762Z" createdBy-id="0"
              desc="" entitySchema="xtk:srcSchema" extendedSchema="nms:offer" img="nms:offer.png"
              label="Marketing offers" labelSingular="Marketing offers" lastModified="2013-01-18 15:20:18.373Z"
              mappingType="sql" md5="F14A7AA009AE1FCE31B0611E72866AC3" modifiedBy-id="0"
              name="offer" namespace="cus" xtkschema="xtk:srcSchema">
     <createdBy _cs="Administrator (admin)"/>
     <modifiedBy _cs="Administrator (admin)"/>
     <element img="nms:offer.png" label="Marketing offers" labelSingular="Marketing offer"
              name="offer">
       <element label="Content" name="view">
         <element label="Price" name="price" type="long" xml="true"/>
         <element label="Title 2" name="title2" type="string" xml="true"/>
   
         <element advanced="true" desc="Price calculation script." label="Script price"
                  name="price_jst" type="CDATA" xml="true"/>
         <element advanced="true" desc="Title calculation script." label="Script title"
                  name="title2_jst" type="CDATA" xml="true"/>
       </element>
     </element>
   </srcSchema>
   ```

   >[!CAUTION]
   >
   >Ogni elemento deve essere definito due volte. Gli elementi di tipo CDATA (&quot;_jst&quot;) possono contenere campi di personalizzazione.
   >
   >Non dimenticare di aggiornare la struttura del database.

   Puoi estendere lo schema delle offerte per aggiungere nuovi campi sia in modalità batch che unitaria, sia in qualsiasi formato (testo, HTML e XML).

1. **Estendi la formula di offerta per modificare nuovi campi e modificare un campo esistente**

   Modifica le **Offerta (nsm)** modulo di input.

   Nella sezione &quot;Visualizzazioni&quot;, inserisci i due nuovi campi con il seguente contenuto:

   ```
   <input label="Title 2" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="title2_jst">
        <form label="Edit title 2" name="editForm" nothingToSave="true">
            <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizeTitle2">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizeTitle2"/>
            </container>
            </input>
        </form>
    </input>
    <input nolabel="true" type="edit" xpath="title2_jst"/>
    <input label="Price" margin-right="5" prebuildSubForm="false" type="subFormLink" xpath="price_jst">
        <form label="Edit price" name="editForm" nothingToSave="true">
        <input nolabel="true" toolbarAlign="horizontal" type="jstEdit" xpath="." xpathInsert="/ignored/customizePrice">
            <container>
                <input menuId="viewMenuBuilder" options="inbound" type="customizeBtn" xpath="/ignored/customizePrice"/>
            </container>
        </input>
        </form>
    </input>
    <input colspan="2" label="Prix" nolabel="true" type="number" xpath="price_jst"/>
   ```

   Aggiungi un commento al campo URL di destinazione:

   ![](assets/interaction_xmlmode_form_001.png)

   >[!CAUTION]
   >
   >I campi del `<input>`) deve puntare agli elementi del tipo CDATA definiti nello schema creato.

   Il rendering nel modulo delle rappresentazioni dell’offerta si presenta così:

   ![](assets/interaction_xmlmode_form.png)

   La **[!UICONTROL Title 2]** e **[!UICONTROL Price]** sono stati aggiunti i campi e **[!UICONTROL Destination URL]** il campo non viene più visualizzato.

1. **Creare un’offerta**

   Per ulteriori informazioni sulla creazione di offerte, consulta [questa pagina](interaction-offer.md).

   Nel seguente caso d’uso, l’offerta viene inserita come segue:

   ![](assets/interaction_xmlmode_offer.png)

1. **Approvare l’offerta**

   Approva un’offerta o fai in modo che venga approvata da un altro utente, quindi attivala nello spazio di offerta creato all’ultimo passaggio in modo che sia disponibile nell’ambiente live collegato.

1. **Chiamate al motore e risultato sulla pagina HTML**

   La chiamata al motore di offerta nella pagina HTML si presenta così:

   ```
   <script id="interactionProposalScript" src="https://<SERVER_URL>/nl/interactionProposal.js?env=OE7&cb=alert" type="text/javascript">
   ```

   Il valore di &quot;**env**&quot; parametro è il nome interno dell&#39;ambiente live.

   Il valore di &quot;**cb**&quot; parameter è il nome della funzione che deve interpretare il nodo XML restituito dal motore. Nel nostro esempio, la funzione chiamata apre una funzione finestra modale (alert() ).

   Il nodo XML restituito dal motore di offerta si presenta così:

   ```
   <propositions>
    <proposition id="a28002" offer-id="10322005" weight="1" rank="1" space="SPC14" div="i_SPC14">
     <xmlOfferView>
      <title>Travel to Russia</title>
      <price>3456</price>
      <description>Discover this vacation package!INCLUDES 10 nights. FEATURES buffet breakfast daily. BONUS 5th night free.</description>
      <image>
       <path>https://myinstance.com/res/Track/ae1d2113ed732d58a3beb441084e5960.jpg</path>
       <alt>Travel to Russia</alt>
      </image>
     </xmlOfferView>
    </proposition>
   </propositions>
   ```

### Utilizzare una funzione di rendering {#using-a-rendering-function-}

È possibile utilizzare una funzione di rendering XML per creare una presentazione di offerta. Questa funzione modifica il nodo XML restituito alla pagina HTML durante la chiamata al motore di offerta.

1. Passa allo spazio di offerta e fai clic sul pulsante **[!UICONTROL Edit functions]** link.
1. Seleziona **[!UICONTROL Overload the XML rendering function]**.
1. Vai a **[!UICONTROL XML rendering]** e inserire la funzione desiderata.

   La funzione può avere questo aspetto:

   ```
   function (proposition) {
     delete proposition.@id;
     proposition.@newAttribute = "newValue";
   } 
   ```

![](assets/interaction_xmlmode_001.png)

## Configurare un’integrazione SOAP

I servizi Web SOAP forniti per la gestione delle offerte sono diversi da quelli generalmente utilizzati in Adobe Campaign. È possibile accedervi tramite l’URL di interazione descritto nella sezione precedente e consentire di presentare o aggiornare le offerte per un determinato contatto.

### Proposta di offerte {#offer-proposition}

Per una proposta di offerta tramite SOAP, aggiungi la **nms:proposition#Propose** seguito dai seguenti parametri:

* **targetId**: chiave primaria del destinatario (può essere una chiave composita).
* **maxCount**: specifica il numero di proposte di offerta per il contatto.
* **contesto**: consente di aggiungere informazioni contestuali nello schema dello spazio. Se lo schema utilizzato è **nms:interazione**, **`<empty>`** devono essere aggiunti.
* **categorie**: specifica le categorie a cui devono appartenere le offerte.
* **temi**: specifica i temi a cui devono appartenere le offerte.
* **uuid**: valore del cookie permanente di Adobe Campaign (&quot;uuid230&quot;).
* **nli**: valore del cookie di sessione di Adobe Campaign (&quot;nlid&quot;).
* **noProp**: utilizza il valore &quot;true&quot; per disattivare l&#39;inserimento della proposta.

>[!NOTE]
>
>La **targetId** e **maxCount** le impostazioni sono obbligatorie. Gli altri sono facoltativi.

In risposta alla query, il servizio SOAP restituirà i seguenti parametri:

* **actionId**: ID dell’interazione.
* **proposizioni**: Elemento XML, contiene l&#39;elenco delle proposte, ciascuna con il proprio ID e la propria rappresentazione HTML.

### Aggiornamento dell’offerta {#offer-update}

Aggiungi il **nms:interazione#UpdateStatus** all&#39;URL, seguito dai seguenti parametri:

* **proposta**: stringa di caratteri, contiene l&#39;ID della proposta fornito come output durante una proposta di offerta. Fai riferimento a [Proposta di offerta](#offer-proposition).
* **status**: tipo di stringa specifica il nuovo stato dell&#39;offerta. I valori possibili sono elencati nella **propositionStatus** enumerazione, **nms:common** schema. Ad esempio, preconfigurato, il numero 3 corrisponde al **Accettato** stato.
* **contesto**: Elemento XML, consente di aggiungere informazioni contestuali nello schema dello spazio. Se lo schema utilizzato è **nms:interazione**, **`<empty>`** devono essere aggiunti.

### Esempio di utilizzo di una chiamata SOAP {#example-using-a-soap-call}

Ecco un esempio di codice per una chiamata SOAP:

```
<%
  var space = request.parameters.sp
  var cnx = new HttpSoapConnection(
    "https://" + request.serverName + ":" + request.serverPort + "/interaction/" + env + "/" + space,
    "utf-8",
    HttpSoapConnection.SOAP_12)
  var session = new SoapService(cnx, "nms:interaction")
  var action = request.parameters.a
  if( action == undefined )
    action = 'propose'

  try
  {
    switch( action )
    {
    case "update":
      var proposition = request.parameters.p
      var status      = request.parameters.st
      session.addMethod("UpdateStatus", "nms:interaction#UpdateStatus",
       ["proposition", "string",
        "status",      "string",
        "context",     "NLElement"],
       [])
      session.UpdateStatus(proposition, status, <undef/>)
      var redirect = request.parameters.r
      if( redirect != undefined )
        response.sendRedirect(redirect)
      break;

    case "propose":
      var count = request.parameters.n
      var target = request.parameters.t
      var categorie = request.parameters.c
      var theme = request.parameters.th
      var layout = request.parameters.l
      if( count == undefined )
        count = 1
      session.addMethod("Propose", "nms:proposition#Propose",
       ["targetId",      "string",
        "maxCount",      "string",
         "categories",    "string",
         "themes",        "string",
        "context",       "NLElement"],
       ["interactionId", "string",
        "propositions",  "NLElement"])
      response.setContentType("text/html")
      var result = session.Propose(target, count, category, theme, <empty/>)
      var props = result[1]
  %><table><tr><%
      for each( var propHtml in props.proposition.*.mdSource )
      {
        %><td><%=propHtml%></td><%
      }
  %></tr></table><%
      break;
    }
  }
  catch( e )
  {
  }
  %>
```
