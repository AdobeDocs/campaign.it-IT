---
source-git-commit: ffa29306eb4402ed20c7d04bdbbaffd4dde5bfe4
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%
---
# Accesso

Apre una sessione

```text
[ String sessionToken, sessionInfo sessionInfo, String securityToken ] = Logon ( String login, String password, XML parameters )
```

## Parametri

Account utente **accesso**

Password **password** associata all&#39;accesso utente

**parametri** impostazioni di connessione

## Valore/i restituito/i

Token di sessione **sessionToken**

**sessionInfo** Parametri di sessione

**securityToken** Token di sicurezza

## Configurazione meccanismo di blocco account

Nell’API logon() è disponibile un meccanismo di blocco dell’account. Impedisce ulteriori tentativi di accesso dopo un determinato numero di tentativi consecutivi di accesso non riusciti entro un intervallo di tempo specificato.

Sono disponibili quattro opzioni per configurare il meccanismo di blocco:

* **XtkSecurity\_max\_Unsuccessul\_Attempts\_Allowed**: numero massimo tentativi non riusciti di bloccare una chiave entro la durata specificata. Il valore predefinito è 3.
* **XtkSecurity\_Initial\_Ban\_Duration**: durata per la quale la chiave verrà vietata per la prima volta. La durata predefinita è di 5 minuti.
* **XtkSecurity\_Max\_Ban\_Duration**: durata massima per la quale è possibile vietare una chiave.
* **XtkSecurity\_Examine\_Window**: intervallo di tempo per il rilevamento del numero di tentativi di accesso non riusciti per il divieto di una chiave non valida. La durata predefinita è di 10 minuti.

Ad esempio, se qualcuno tenta di effettuare 3 tentativi falliti in 10 minuti, la chiave viene bloccata per 5 minuti.

## Funzioni

**Schema:** [xtk:session](s-xtk-session.md)

**Statico:**

Sì
