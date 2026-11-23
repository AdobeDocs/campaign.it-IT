---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 5%
---
# decryptPassword

> Avvertenza:
>
> Questa documentazione è stata aggiornata. Per ulteriori dettagli, consulta questa [pagina](https://experienceleague.adobe.com/en/docs/campaign-classic/using/technotes/gcm-functions#decryptpassword-headding-anchor-decryptpassword-javascript).

Decritta una password archiviata in un account esterno.

```text
decryptPassword (str)
```

## Parametri

**str** Stringa di caratteri crittografati.

## Valore restituito

Restituisce la password in formato testo normale.

## Osservazioni

Questa funzione non può essere chiamata nei flussi di lavoro, nelle applicazioni web, nei rapporti o nelle consegne. Può essere chiamato nelle implementazioni di chiamate JSSP o SOAP. Esempio:

```javascript
          function nms_extAccount_LogonToRemoteInstance(remoteInstanceUrl, login, encryptedPassword) {
          var cnx = null, sessionService = null;
          try
              {
                  var cnx = new HttpSoapConnection(remoteInstanceUrl + '/nl/jsp/soaprouter.jsp', 'utf-8', 0);
                  sessionService = new SoapService(cnx, 'xtk:session');
                  sessionService.addMethod("Logon", "xtk:session#Logon",
                      ["token", "string", "login", "string", "password", "string", "parameters", "NLElement"],
                      ["sessionToken", "string", "sessionInfo", "NLElement", "securityToken", "string"]);
                  return sessionService.Logon("", login, decryptPassword(encryptedPassword), <parameters/>);
              }
          catch( e ) {
          logError(e);
          }
          finally {
          if( sessionService ) sessionService.dispose();
          if( cnx ) cnx.dispose();
          }
          })
      
```

## Funzioni

**Disponibile in:**

* Metodo SOAP
