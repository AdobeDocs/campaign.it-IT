---
product: campaign
title: Configurare le regole di controllo
description: Scopri come configurare le regole di controllo
feature: Typology Rules
exl-id: 79e442ea-f856-41bf-b065-25cb2ad2c65b
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 0%

---

# Regole di controllo{#control-rules}

Le regole di controllo ti consentono di garantire la validità e la qualità dei messaggi prima della consegna: visualizzazione dei caratteri, dimensioni dell’SMS, formato dell’indirizzo, ecc.

Una serie di regole pronte all’uso consente di eseguire i controlli standard. Questi controlli (visualizzati in grassetto nell’interfaccia) sono:

* **[!UICONTROL Object approval]** (e-mail): verifica che l’oggetto e l’indirizzo del mittente non contengano caratteri speciali che potrebbero causare problemi a determinati agenti di posta.
* **[!UICONTROL URL label approval]** (e-mail): controlla che ogni URL di tracciamento sia associato a un’etichetta.
* **[!UICONTROL URL approval]** (e-mail): controlla gli URL di tracciamento (presenza del carattere &quot;&amp;&quot;).
* **[!UICONTROL Message size approval]** (mobile): controlla la dimensione dei messaggi SMS.
* **[!UICONTROL Validity period check]** (e-mail): controlla che il periodo di validità della consegna sia sufficientemente lungo da consentire l’invio di tutti i messaggi.
* **[!UICONTROL Proof size check]** (tutti i canali): genera un messaggio di errore se la popolazione target della bozza supera i 100 destinatari.
* **[!UICONTROL Wave scheduling check]** (e-mail): controlla che l’ultimo ciclo di consegne inizi prima della fine del periodo di validità, se la consegna è suddivisa in più cicli.
* **[!UICONTROL Unsubscription link approval]** (e-mail): controlla la presenza di almeno un URL di annullamento dell’abbonamento (rinuncia) in ogni contenuto (HTML e Testo).

## Creare una regola di controllo {#create-a-control-rule}

È possibile creare nuove regole di controllo in base alle tue esigenze. A questo scopo, crea un’ **[!UICONTROL Control]** regola di tipologia e immettere la formula di controllo in SQL nel **[!UICONTROL Code]** scheda.

**Esempio:**

Nell’esempio seguente verrà creata una regola per impedire l’invio di un’offerta SMS a più di 100 destinatari. Questa regola sarà collegata a una tipologia di campagna, quindi alle consegne di SMS per le quali è disponibile l’offerta in questione.

Applica i seguenti passaggi:

1. Creare un **[!UICONTROL Control]** regola di tipologia. Seleziona un **[!UICONTROL Warning]** livello di avviso.

   ![](assets/campaign_opt_create_control_01.png)

1. In **[!UICONTROL Code]** , immetti lo script per applicare la soglia desiderata, come illustrato di seguito:

   ![](assets/campaign_opt_create_control_02.png)

   Questo script attiverà un avviso se il target della consegna supera i 100 contatti:

   ```
   if( delivery.FCP == false && delivery.properties.toDeliver > 100 ) { logWarning("Significant number of SMS to deliver (" + delivery.properties.toDeliver + "). Please make sure the target is correct.") return false; } return true
   ```

1. Collega questa regola a una tipologia di campagna e fai riferimento alla tipologia nell’SMS interessato.

   ![](assets/campaign_opt_create_control_03.png)

1. Durante l’analisi della consegna, la regola viene applicata e viene creato un avviso, se applicabile.

   ![](assets/campaign_opt_create_control_04.png)

   Tuttavia, la consegna sarà ancora pronta per l’invio.

   Se aumenti il livello di avviso, ciò impedirà l’avvio della consegna.

   ![](assets/campaign_opt_create_control_05.png)

   Al termine dell&#39;analisi, la **[!UICONTROL Confirm delivery]** non sarà disponibile.

   ![](assets/campaign_opt_create_control_06.png)
