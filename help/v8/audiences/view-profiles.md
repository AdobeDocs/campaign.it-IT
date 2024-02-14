---
title: Visualizzare i profili esistenti in Campaign
description: Scopri come accedere ai dati di contatto in Campaign
feature: Audiences, Profiles
role: User
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: b5574ba2d9fa520b701f7af4e34862304b825a66
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 2%

---

# Visualizzare i profili esistenti{#view-profiles}

Sfoglia per **[!UICONTROL Profiles and targets]** per accedere ai destinatari memorizzati nel database di Adobe Campaign.

Da questa pagina è possibile: [crea nuovo destinatario](create-profiles.md), modifica un destinatario esistente e accedi ai relativi dettagli del profilo.

![](assets/profiles-and-targets.png)

Per manipolazioni del profilo più avanzate, accedi alla struttura Campaign da **[!UICONTROL Explorer]** nella home page di Adobe Campaign.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>La schermata Destinatario incorporata viene definita tramite uno schema XML e il relativo modulo associato. Lo schema XML viene memorizzato in **[!UICONTROL Administration > Configuration > Data schemas]** nodo della struttura di Adobe Campaign explorer. Solo gli utenti esperti possono apportare modifiche a questi schemi.
>

## Modificare un profilo{#edit-a-profiles}

Seleziona un profilo per visualizzare i dettagli in una nuova scheda.

![](assets/edit-a-profile.png)

I dati relativi ai profili sono raggruppati in schede. Queste schede e il loro contenuto dipendono dalle impostazioni specifiche e dai pacchetti installati.

Per un destinatario predefinito tipico, puoi accedere alle seguenti schede:

* **[!UICONTROL General]**, per tutti i dati di profilo generali. In particolare, contiene il cognome, il nome, l’indirizzo e-mail, il formato e-mail, ecc.

  Questa scheda memorizza anche **rinuncia** flag per il profilo: quando **[!UICONTROL No longer contact (by any channel)]** è selezionata, il profilo è in fase di inserisco nell&#39;elenco Bloccati. Queste informazioni vengono aggiunte ai dati di contatto se, ad esempio, il destinatario ha fatto clic su un collegamento di annullamento dell’abbonamento in una newsletter. Tale destinatario non è più indirizzato su alcun canale (e-mail, direct mailing, ecc.). Per ulteriori informazioni, consulta [questa pagina](../send/quarantines.md).

* **Informazioni di contatto**, che contiene l’indirizzo di direct mailing del profilo selezionato.

  In questa schermata puoi archiviare l’indice di qualità dell’indirizzo e quanti errori contiene l’indirizzo. Queste informazioni vengono utilizzate direttamente dal provider di direct mailing, in base al numero di errori rilevati durante le consegne precedenti, e non possono essere modificate manualmente.

* **Altro**, per campi specifici che possono essere personalizzati e compilati in base alle tue esigenze.

  Utilizza il **[!UICONTROL Field properties…]** menu contestuale per modificare i nomi dei campi e definirne il formato.

  ![](assets/other-tab-field-properties.png)

  Immetti le nuove impostazioni come segue:

  ![](assets/change-field-properties.png)

  Controlla l’aggiornamento nell’interfaccia utente:

  ![](assets/other-tab-updated.png)


  >[!CAUTION]
  >Le modifiche vengono applicate a tutti i destinatari.
  >


* **Iscrizioni**, per tutti gli abbonamenti attivi ai servizi. Utilizza il **Cronologia** per accedere ai dettagli degli abbonamenti e dei loro annullamenti per questo contatto.

  ![](assets/subscription-tab.png)

  Ulteriori informazioni sugli abbonamenti [in questa sezione](../start/subscriptions.md).

* **Consegne**, per tutti i registri di consegna per il profilo selezionato. Utilizza questa scheda per accedere alla cronologia di marketing del contatto: etichette, date e stato di tutte le azioni di consegna indirizzate al profilo tramite tutti i canali.


* **Tracciamento**, per tutti i registri di tracciamento per il profilo selezionato. Queste informazioni vengono utilizzate per tenere traccia del comportamento del profilo dopo le consegne. Questa scheda mostra il totale cumulativo di tutti gli URL tracciati nelle consegne. L’elenco è configurabile e in genere contiene: l’URL su cui è stato fatto clic, la data e l’ora del clic e il documento che conteneva l’URL

  Ulteriori informazioni sul tracciamento [in questa sezione](../start/tracking.md).


## Profili attivi {#active-profiles}

Un profilo attivo è un profilo con cui il cliente ha tentato di comunicare negli ultimi 12 mesi tramite qualsiasi canale. Le metriche delle licenze si basano sui profili attivi. Ulteriori informazioni in [Descrizione del prodotto Adobe Campaign](https://helpx.adobe.com/it/legal/product-descriptions/adobe-campaign-managed-cloud-services.html){target="_blank"}.

>[!CAUTION]
>
>* Un profilo che è stato oggetto di targeting per diverse consegne viene conteggiato una sola volta.
>
>* I profili target nel contesto di Social marketing su X (precedentemente noti come Twitter) non vengono considerati come profili attivi.

Puoi monitorare il numero di profili attivi nell’istanza direttamente dal Pannello di controllo Campaign Campaign. Per ulteriori informazioni, consulta [Documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html){target="_blank"}.
