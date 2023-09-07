---
title: Migrazione degli operatori di Campaign a Adobe Identity Management System (IMS)
description: Scopri come migrare gli operatori di Campaign a Adobe Identity Management System (IMS)
hide: true
hidefromtoc: true
source-git-commit: 11128dcb26119383b86aa62561ec0ce1a3c138ad
workflow-type: tm+mt
source-wordcount: '792'
ht-degree: 2%

---

# Migrazione degli operatori di Campaign a Adobe Identity Management System (IMS) {#migrate-users-to-ims}

A partire dalla versione 8.6 di Campaign, il processo di autenticazione a Campaign v8 viene migliorato. Tutti gli operatori utilizzeranno [Sistema Adobe Identity Management (IMS)](https://helpx.adobe.com/enterprise/using/identity.html){target="_blank"} solo per connettersi a Campaign. La connessione con l&#39;utente/password non sarà più consentita. L’Adobe consiglia di eseguire questa migrazione in Campaign v8.5.2 per eseguire in modo fluido la migrazione a Campaign v8.6.

Questo articolo descrive i passaggi necessari per migrare un operatore tecnico all’account tecnico nella console Adobe Developer.

## Cosa è cambiato?{#move-to-ims-changes}

Tutti gli utenti regolari di Campaign devono già connettersi alla console client di Adobe Campaign utilizzando il proprio Adobe ID, tramite Adobe Identity Management System (IMS). Tuttavia, con alcune configurazioni precedenti, le connessioni utente/password erano ancora disponibili. Questo non sarà più consentito a partire da Campaign v8.6.

Inoltre, come parte del tentativo di rafforzare la sicurezza e il processo di autenticazione, l’applicazione client di Adobe Campaign ora chiama le API di Campaign direttamente utilizzando il token dell’account tecnico IMS. La migrazione degli operatori tecnici è descritta in un articolo dedicato, disponibile in [questa pagina](ims-migration.md).

Questa modifica è applicabile a partire da Campaign v8.5.2 e sarà **obbligatorio** avvio di Campaign v8.6.


## Sei interessato da questo problema?{#migrate-ims-impacts}

Se gli operatori della tua organizzazione si connettono alla console client di Campaign utilizzando il proprio login/password (alias. autenticazione nativa), sei interessato e devi migrare questi operatori in Adobe IMS come descritto di seguito.

La migrazione IMS è un imperativo di sicurezza per rendere gli ambienti sicuri e standardizzati, in quanto la maggior parte delle altre app Adobe DX sono già su IMS.

## Come effettuare la migrazione?{#ims-migration-procedure}

### Prerequisiti{#ims-migration-prerequisites}

Prima di avviare la procedura di migrazione, è necessario contattare il rappresentante Adobe (Transition Manager) in modo che i team tecnici Adobe possano migrare i gruppi di operatori e i diritti denominati esistenti a Identity Management System (IMS) Adobe.

### Passaggi chiave {#ims-migration-steps}

I passaggi chiave per questa migrazione sono elencati di seguito:

1. Adobe aggiorna gli ambienti a Campaign v8.5.2.
1. Dopo l’aggiornamento, è comunque possibile creare nuovi utenti con entrambi i metodi, come utente nativo o con IMS.
1. L’amministratore di Campaign interno deve aggiungere e-mail univoche a tutti gli utenti nativi nella console client di Campaign e, al termine, confermare l’operazione con il tuo Adobe Transition Manager. Questo passaggio è descritto in [questa sezione](#ims-migration-id).
1. Lavora con Adobe per proteggere una data ad Adobe per eseguire la migrazione automatizzata non tecnica degli utenti (operatori) e dei profili di prodotto. Questo passaggio richiede una finestra temporale senza tempi di inattività per nessuna istanza.
1. L’amministratore di Campaign interno convalida queste modifiche e fornisce l’approvazione. Dopo questa migrazione, non sarà più necessario creare alcun operatore che effettui l’autenticazione con il suo login e la sua password.

Ora puoi pianificare la migrazione degli utenti tecnici a IMS in base a [questa nota tecnica](ims-migration.md), e conferma sul tuo Adobe Transition Manager al termine.
Adobe contrassegna la migrazione come completata e attiva i flag per bloccare la creazione di un nuovo utente nativo e l’accesso dell’utente nativo.

## Domande frequenti? {#ims-migration-faq}

### Quando è possibile avviare la migrazione? {#ims-migration-start}

Un prerequisito per la migrazione ad Adobe Identity Management System (IMS) è aggiornare l’ambiente a Campaign v8.5.2.

Puoi avviare la migrazione IMS nell’ambiente di stage, dopo l’aggiornamento a Campaign v8.5.2, e pianificare di conseguenza l’ambiente di produzione.

### Cosa succede dopo l’aggiornamento della build 8.5.2? {#ims-migration-after-upgrade}

Dopo l’aggiornamento degli ambienti a Campaign v8.5.2, puoi eseguire la migrazione Adobe Identity Management System (IMS).

La creazione di un nuovo utente nativo è ancora consentita fino al completamento della migrazione IMS.

### Quando è stata completata la migrazione? {#ims-migration-end}

Al termine della migrazione degli utenti finali e della migrazione tecnica degli utenti ad Adobe Identity Management System (IMS), devi contattare il tuo Adobe Transition Manager in modo che Adobe possa contrassegnare la migrazione come completata e bloccare la creazione degli utenti dalla console client e l’accesso dell’utente nativo.


### Come creare gli utenti dopo la migrazione? {#ims-migration-native}

Una volta completata la migrazione IMS, Adobe applicherà le restrizioni che impediranno la creazione di nuovi utenti nativi. Queste restrizioni vengono applicate solo dopo il completamento della migrazione IMS.

Per i nuovi clienti: non è consentita la creazione di nuovi utenti nativi fin dall’inizio.

In qualità di amministratore di Campaign, puoi concedere autorizzazioni agli utenti della tua organizzazione tramite Adobe Admin Console e la console client di Campaign. Gli utenti accedono ad Adobe Campaign con il proprio Adobe ID. Per ulteriori informazioni consulta [questa documentazione](../../v8/start/gs-permissions.md).

### Come si aggiungono le e-mail per gli utenti nativi attuali? {#ims-migration-id}

In qualità di amministratore di Campaign, devi aggiungere gli ID e-mail a tutti gli utenti nativi dalla console client. Per farlo, segui la procedura indicata di seguito:

1. Connettiti alla console client e individua **Amministrazione > Gestione degli accessi > Operatori**
1. Selezionare l&#39;operatore da aggiornare nell&#39;elenco degli operatori.
1. Inserisci l’e-mail dell’operatore nel **Punti di contatto** sezione del modulo operatore.
1. Salva le modifiche.


### Come effettuare l’accesso a Campaign tramite IMS? {#ims-migration-log}

Scopri come connetterti a Campaign con il tuo Adobe ID in [questa sezione](../../v8/start/connect.md).