---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 73%
---
# sessione

Sessioni al server dell’applicazione

## Elemento “methods”

| Elemento “method” | Descrizione |
| --- | --- |
| [ApplyDuplicateRules](sm-session-applyduplicaterules.md) | Applica le impostazioni di duplicazione (compresi i valori predefiniti) al documento specificato |
| [BearerTokenLogon](sm-session-bearertokenlogon.md) | token di connessione |
| [CambiaPassword](sm-session-changepassword.md) | Modifica password corrente |
| [EliminaRaccolta](sm-session-deletecollection.md) | Eliminare un elenco di entità in base a una condizione |
| [Diff](sm-session-diff.md) | Restituisce la versione corrente e la versione originale di un documento. |
| [Duplicato](sm-session-duplicate.md) | Crea un nuovo documento da un documento di origine |
| [DuplicaIn](sm-session-duplicateto.md) | Duplica un nuovo documento da un documento di origine a una determinata cartella |
| [DuplicateWithMappingId](sm-session-duplicatewithmappingid.md) | Duplica un nuovo documento dal documento di origine con la mappatura ID |
| [Crittografa](sm-session-encrypt.md) | Crittografa la stringa di caratteri con la chiave dell‘istanza. |
| [CrittografaPasswordServer](sm-session-encryptserverpassword.md) | Crittografa la stringa di caratteri con la chiave del server. |
| [FormatDataPolicy](sm-session-formatdatapolicy.md) | Applica una trasformazione alla stringa di caratteri in base al criterio dei dati passato come parametro. Lascia la stringa invariata in caso di errore. |
| [GetActiveApplicationMenus](sm-session-getactiveapplicationmenus.md) | Restituisce un documento contenente i menu delle applicazioni abilitate per l‘accesso corrente |
| [GetCnxInfo](sm-session-getcnxinfo.md) | Recupera le informazioni dalle connessioni correnti. |
| [GetDefaultEntity](sm-session-getdefaultentity.md) | Restituisce un documento contenente un’entità vuota con i relativi valori predefiniti |
| [GetDirtyCacheEntities](sm-session-getdirtycacheentities.md) | Restituisci entità corrotte memorizzate nella cache |
| [GetEntityIfMoreRecent](sm-session-getentityifmorerecent.md) | Carica un’entità se la chiave MD5 è diversa da quella fornita come parametro |
| [GetImages](sm-session-getimages.md) | Carica un elenco di immagini |
| [GetNewIds](sm-session-getnewids.md) | Raccoglie un elenco di identificatori di chiavi interne per il database. |
| [GetNewIdsEx](sm-session-getnewidsex.md) | Ottieni un elenco di identificatori univoci dal database, con un nome di sequenza. |
| [GetOption](sm-session-getoption.md) | Restituisce il valore di un’opzione memorizzata nel database. |
| [GetPkList](sm-session-getpklist.md) | Ottenere l’elenco degli identificatori di istanza |
| [GetServerTime](sm-session-getservertime.md) | Restituisce la data e l’ora del server |
| [GetUserInfo](sm-session-getuserinfo.md) | Informazioni sull‘operatore corrente |
| [HashPassword](sm-session-hashpassword.md) | Digita una password con la chiave server. |
| [ImportCollection](sm-session-importcollection.md) | Aggiornare un elenco di entità mediante un’importazione |
| [KillSession](sm-session-killsession.md) | Chiude la sessione specificata |
| [Carica](sm-session-load.md) | Caricare l’entità |
| [LoadAsText](sm-session-loadastext.md) | Recupera il contenuto dell‘entità come testo |
| [LoadIfExists](sm-session-loadifexists.md) | Caricare l’entità se esiste |
| [Disconnessione](sm-session-logoff.md) | Chiudi sessione corrente |
| [Accesso](sm-session-logon.md) | Apre una sessione |
| [NuovaIstanza](sm-session-newinstance.md) | Creazione di un nuovo documento, preinizializzato ma non salvato |
| [Rimuovi](sm-session-remove.md) | Elimina entità |
| [ArrestoServer](sm-session-servershutdown.md) | Arresto del server richieste |
| [ImpostaValoriPredefiniti](sm-session-setdefaultvalues.md) | Correggi i valori per impostazione predefinita in base a XPath |
| [ImpostazioniPredefinite](sm-session-setdefaults.md) | Imposta valori predefiniti |
| [TestCnx](sm-session-testcnx.md) | Verifica la connessione. |
| [Scrittura](sm-session-write.md) | Aggiorna un’entità |
| [WriteCollection](sm-session-writecollection.md) | Aggiornare un elenco di entità |

## Metodi generici

| Elemento “method” | Descrizione |
| --- | --- |
| [crea](f-create.md) | Crea una nuova entità corrispondente a uno schema specificato. |
| [carica](f-load.md) | Carica e restituisce un&#39;entità corrispondente a uno schema e a una chiave specifici. |
| [salva](m-entity-save.md) | Salva un&#39;entità nel database. |
