---
title: Tracciare collegamenti personalizzati
description: Scopri come tenere traccia dei collegamenti personalizzati nelle e-mail
feature: Personalization
role: User
level: Beginner
exl-id: d0e00b40-e7dd-4484-b37c-fd3f3ac70fda
source-git-commit: 6e465ec24f72d0b30c4fc287da5d4c4bcaeda05b
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 2%

---

# Tracciare collegamenti personalizzati {#tracking-personalized-links}

I collegamenti nel contenuto delle e-mail che contengono la personalizzazione devono essere tracciati con una sintassi specifica.

L’utilizzo di JavaScript nel contenuto delle e-mail (HTML o Testo) consente di generare e inviare contenuto dinamico ai destinatari, con due limitazioni:

* Lo script non può accedere direttamente al database (funzioni SQL e API non disponibili),
* Adobe Campaign deve essere in grado di rilevare gli URL in modo da poter tenere traccia dei collegamenti.

## Istruzioni di pre-elaborazione {#pre-processing-instructions}

Puoi aggiungere istruzioni di pre-elaborazione specifiche per scrivere lo script dell’URL e tracciarlo. Queste istruzioni devono essere scritte in JavaScript e iniziare con `<%@`.

Ad esempio:

```
<%@ value object="myObject" xpath="@myField" %>
```

Questa istruzione recupera il valore del campo `myField` dall&#39;oggetto `myObject`.

## Rilevamento URL {#url-detection}

Per il rilevamento del tracciamento, Adobe Campaign incorpora [Tidy](https://www.html-tidy.org/) per analizzare l&#39;origine HTML e rilevare il modello. Elenca tutti gli URL del contenuto in modo che possano essere tracciati singolarmente. Adobe Campaign utilizza nuovamente Tidy per sostituire l&#39;URL (`http://myurl.com`) con un URL che punta al server di reindirizzamento di Adobe Campaign.

Ad esempio, nel contenuto iniziale: `http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>` è sostituito per un destinatario particolare con: `http://emailing.customer.com/r/?id=h617791,71ffa3,71ffa8&p1=CustomerName`

Dove:

* &quot;h&quot; significa contenuto HTML (o &quot;t&quot; per contenuto di testo).
* 617791 è l’ID del messaggio/broadLog ID (esadecimale).
* 71ffa3 è l’ID NmsDelivery (esadecimale).
* 71ffa8 è l’ID NmsTrackingUrl (esadecimale).
* p1, p2 e così via sono tutti i parametri da sostituire nell&#39;URL.

### Esempio di non rilevamento {#non-detection-example}

`<%= getURL("http://mynewsletter.com") %>` funziona e invia il contenuto effettivo della pagina Web tramite e-mail ai destinatari. Ma nessuno dei collegamenti viene tracciato. Il motivo è che l&#39;MTA esegue `"<%=getURL(..."` per ogni e-mail prima dell&#39;invio. Può essere diverso per ogni destinatario, pertanto Adobe Campaign non può conoscere gli URL per il tracciamento e assegnare loro un ID tag.

Quando la pagina da scaricare è la stessa per tutti i destinatari, la best practice è quella di utilizzare:

```
<%@ include url="http://mynewsletter.com" %>
```

In tal caso, la pagina viene scaricata durante l’analisi, prima del rilevamento del tracciamento. Consente ad Adobe Campaign di scoprire i collegamenti, assegnare un ID tag e tracciarli.

### Schema consigliato {#recommended-pattern}

Dopo aver elaborato le istruzioni `<%@`, l&#39;URL da tracciare deve avere la seguente sintassi:

```
<a href="http://myurl.com/a.php?param1=aaa&param2=<%=escapeUrl(recipient.xxx)%>&param3=<%=escapeUrl(recipient.xxx)%>">
```

>[!IMPORTANT]
>
>Tutti gli altri modelli non sono supportati da Adobe e devono essere evitati per evitare potenziali lacune di sicurezza.

## Parametri URL {#url-parameters}

Per garantire che gli URL personalizzati vengano tracciati correttamente, è necessario utilizzare la funzione `escapeUrl()` o il metodo di codifica appropriato per i parametri degli URL.

**Esempio:**

```
<a href="http://myurl.com/a.php?name=<%=escapeUrl(recipient.lastName)%>">Click here</a>
```

In questo modo, il parametro personalizzato verrà codificato e tracciato correttamente da Adobe Campaign.

## Ciclo con `<%@ foreach %>` {#foreach}

L&#39;istruzione `<%@ foreach %>` consente di eseguire iterazioni su array di oggetti caricati nella consegna per tenere traccia dei singoli collegamenti correlati agli oggetti.

### Sintassi

```
<%@ foreach object="myObject" xpath="myLink" index="3" item="myItem" %>
  <!-- Content to repeat -->
<%@ end %>
```

**Parametri:**

* **`object`**: nome dell&#39;oggetto da cui iniziare (in genere un oggetto script aggiuntivo, ma può essere una consegna)
* **`xpath`** (facoltativo): XPath della raccolta su cui eseguire il ciclo. Il valore predefinito è &quot;.&quot;, ovvero l&#39;oggetto corrisponde all&#39;array su cui eseguire il ciclo
* **`index`** (facoltativo): se xpath non è &quot;.&quot; e l’oggetto è un array stesso, indice dell’oggetto (inizia da 0)
* **`item`** (facoltativo): nome di un nuovo oggetto accessibile con `<%@ value %>` all&#39;interno del ciclo foreach. Predefinito è il nome del collegamento nello schema

### Esempio

Nelle proprietà/personalizzazione della consegna, carica un array di articoli e una tabella di relazione tra destinatario e articoli.

Puoi visualizzare i collegamenti a questi articoli con il tracciamento individuale:

```
<%@ foreach object="articleList" item="article" %>
  <a href="http://example.com/article.jsp?id=<%@ value object="article" xpath="@id" %>">
    <%@ value object="article" xpath="@title" %>
  </a>
<%@ end %>
```

Questo consente ad Adobe Campaign di tenere traccia dell’articolo specifico su cui ciascun destinatario ha fatto clic, anziché tenere semplicemente traccia del clic su un collegamento di articolo.

## Best practice {#best-practices}

* Utilizza sempre la funzione `escapeUrl()` per i parametri URL dinamici
* Usa `<%@ foreach %>` quando devi tenere traccia di singoli elementi nelle raccolte
* Verifica il tracciamento prima di inviare la consegna per garantire il corretto funzionamento di tutti i collegamenti
* Verifica che i collegamenti personalizzati siano formattati correttamente nel contenuto della consegna
* Controlla i registri di tracciamento per verificare che i parametri personalizzati vengano acquisiti correttamente

## Argomenti correlati {#related-topics}

* [Scopri come configurare i collegamenti tracciati](tracked-links.md)
* [Scopri come configurare le opzioni di tracciamento URL](url-tracking.md)
* [Scopri come aggiungere campi di personalizzazione](personalization-fields.md)

