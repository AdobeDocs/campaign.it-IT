---
title: Anteprima e verifica dell’e-mail
description: Scopri come convalidare la consegna prima dell’invio
feature: Personalization
role: User
level: Beginner
exl-id: 5b9fa90c-c23e-47a7-b2ca-de75da4da2ab
source-git-commit: 19c42bcd2a96173f3d33e3e259192107b5e64c6c
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 3%

---

# Anteprima e verifica dell’e-mail {#preview-test}

Una volta definito il contenuto del messaggio, puoi utilizzare i profili di test per visualizzarlo in anteprima e testarlo. Se è stato inserito [contenuti personalizzati](personalize.md), puoi verificare come viene visualizzato questo contenuto nel messaggio, utilizzando i dati del profilo di test. Inoltre, per rilevare eventuali errori nel contenuto del messaggio o nelle impostazioni di personalizzazione, invia bozze ai profili di test. Per convalidare il contenuto più recente, è necessario inviare una bozza ogni volta che viene apportata una modifica.

## Anteprima contenuto{#preview-content}

Prima di inviare le bozze, una best practice consiste nel controllare il contenuto del messaggio nella sezione di anteprima della finestra di consegna.

Per visualizzare in anteprima il contenuto del messaggio, segui i passaggi seguenti:

1. Accedi a **Anteprima** della consegna.
1. Fai clic su **[!UICONTROL Test personalization]** per selezionare un profilo per compilare i dati di personalizzazione. Puoi scegliere un destinatario specifico nel database, un indirizzo di seed o selezionare un profilo dalla popolazione target, se è già stato definito. Puoi anche controllare il contenuto senza personalizzazione.

   ![](assets/test-personalization.png)

1. L’anteprima viene generata in modo da poter controllare il rendering del messaggio. Nell’anteprima del messaggio, gli elementi personalizzati vengono sostituiti dai dati del profilo di test selezionati.

   ![](assets/test-personalization-with-a-recipient.png)

1. Seleziona altri profili di test per visualizzare in anteprima il rendering delle e-mail per ogni variante del messaggio.

## Inviare bozze {#send-proofs}

Per le consegne e-mail, puoi inviare bozze per convalidare il contenuto del messaggio. L’invio di bozze ti consente di controllare il collegamento di rinuncia, la pagina speculare e tutti gli altri collegamenti, convalidare il messaggio, verificare che siano visualizzate le immagini, rilevare eventuali errori, ecc. Puoi anche controllare la progettazione e il rendering su dispositivi diversi.

Una bozza è un messaggio specifico che ti consente di testare un messaggio prima di inviarlo al pubblico principale. I destinatari della bozza hanno il compito di approvare il messaggio: rendering, contenuto, impostazioni di personalizzazione, configurazione.

### Destinatari bozza {#proofs-recipients}

Il target della bozza può essere definito nel modello di consegna o specifico per una consegna. In entrambi i casi, passa alla schermata di definizione del target dal menu **[!UICONTROL To]** e seleziona la **[!UICONTROL Target of the proofs]** scheda.

![](assets/target-of-proofs.png)

Il tipo di destinazione della bozza è selezionato da **[!UICONTROL Targeting mode]** elenco a discesa.

* Utilizza il **[!UICONTROL Definition of a specific proof target]** per selezionare i destinatari nel database come destinazione della bozza.
* Utilizza il **[!UICONTROL Substitution of the address]** opzione per immettere indirizzi e-mail e utilizzare i dati dei destinatari target per convalidare il contenuto. Gli indirizzi di sostituzione possono essere immessi manualmente o selezionati dall&#39;elenco a discesa. L&#39;enumerazione associata è Substitution address (rcpAddress).
Per impostazione predefinita, la sostituzione viene eseguita in modo casuale, ma è possibile selezionare un destinatario specifico dal target principale tramite  **[!UICONTROL Detail]** icona.

  ![](assets/target-of-proofs-substitution-details.png){width="800" align="left"}

  Scegli la **[!UICONTROL Select a profile (must be included in the target)]** e selezionare un destinatario.

  ![](assets/target-of-proofs-substitution.png){width="800" align="left"}


* Utilizza il **[!UICONTROL Seed addresses]**  opzione per utilizzare gli indirizzi seed come destinazione della bozza. Questi indirizzi possono essere importati da un file o immessi manualmente.

  >[!NOTE]
  >
  >Gli indirizzi seed non appartengono alla tabella dei destinatari predefinita (nms:recipient), ma vengono creati in una tabella separata. Se estendi la tabella dei destinatari con nuovi dati, devi estendere anche la tabella degli indirizzi di seed con gli stessi dati.

  Ulteriori informazioni sugli indirizzi di seed in [questa sezione](../audiences/test-profiles.md).

* Utilizza il **[!UICONTROL Specific target and Seed addresses]** opzione per combinare indirizzi seed e indirizzi e-mail specifici. Le configurazioni correlate vengono quindi definite in due schede secondarie separate.

### Inviare una bozza{#proofs-send}

Per inviare bozze dei messaggi, effettua le seguenti operazioni:

1. Nella schermata di definizione del messaggio, fai clic su **[!UICONTROL Send a proof]** pulsante.
1. Dalla sezione **[!UICONTROL Send a proof]** , controlla i destinatari della bozza.
1. Clic **[!UICONTROL Analyze]** per avviare la preparazione dei messaggi di bozza.

   ![](assets/send-proof-analyze.png){width="800" align="left"}

1. Una volta completata la preparazione della consegna, utilizza **[!UICONTROL Confirm delivery]** per iniziare a inviare messaggi di prova.

Accedi a **[!UICONTROL Audit]** scheda della consegna per verificare la consegna delle copie della bozza.

Si consiglia di inviare le bozze dopo ogni modifica al contenuto del messaggio.

>[!NOTE]
>
>Nella bozza inviata, il collegamento alla pagina speculare non è attivo. Viene attivato solo nei messaggi finali.

### Proprietà bozza{#proofs-properties}

Le proprietà della bozza sono impostate in **[!UICONTROL Advanced]** scheda delle finestre delle proprietà di consegna. Accedi a **[!UICONTROL Proof properties...]** per definire i parametri e l’etichetta delle bozze. Puoi scegliere di mantenere:

* Indirizzi duplicati nella bozza
* Indirizzi Inseriti nell&#39;elenco Bloccati nella bozza
* Indirizzi in quarantena nella bozza

Per impostazione predefinita, i messaggi di bozza sono identificati da `Proof #N` menzione nell&#39;oggetto, dove `N` è il numero della bozza. Questo numero viene incrementato con ogni analisi della consegna della bozza. È possibile modificare il `proof` prefisso, se necessario.

![](assets/proof-parameters.png){width="800" align="left"}


## Video dimostrativo {#video-proof}

Scopri come inviare e convalidare una bozza per una consegna e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/333404)
