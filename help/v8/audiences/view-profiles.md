---
title: Visualizzare i profili esistenti in Campaign
description: Scopri come accedere ai dati di contatto in Campaign
feature: Audiences, Profiles
role: Data Engineer
level: Beginner
exl-id: 03f7a736-e0b9-4216-9550-507f10e6fcf6
source-git-commit: c316da3c431e42860c46b5a23c73a7c129abf3ac
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 2%

---

# Visualizzare i profili esistenti{#view-profiles}

Sfoglia per **[!UICONTROL Profiles and targets]** per accedere ai destinatari memorizzati nel database Adobe Campaign.

Da questa pagina puoi [crea nuovo destinatario](create-profiles.md), modifica un destinatario esistente e accedi ai relativi dettagli di profilo.

![](assets/profiles-and-targets.png)

Per manipolazioni di profilo più avanzate, accedi alla struttura ad albero di Campaign dal **[!UICONTROL Explorer]** nella home page di Adobe Campaign.

![](assets/recipients-in-explorer.png)


>[!CAUTION]
>
>La schermata Destinatario incorporata viene definita tramite uno schema XML e il relativo modulo associato. Lo schema XML viene memorizzato nel **[!UICONTROL Administration > Configuration > Data schemas]** nodo della struttura ad albero di Adobe Campaign explorer. Solo gli utenti esperti possono apportare modifiche a tali schemi.

## Modificare un profilo{#edit-a-profiles}

Seleziona un profilo per visualizzare i dettagli in una nuova scheda.

![](assets/edit-a-profile.png)

I dati relativi ai profili sono raggruppati in schede. Queste schede e il loro contenuto dipendono dalle impostazioni specifiche e dai pacchetti installati.

Per un destinatario predefinito tipico, puoi accedere alle seguenti schede:

* **[!UICONTROL General]**, per tutti i dati generali del profilo. In particolare, contiene il cognome, il nome, l’indirizzo e-mail, il formato e-mail, ecc.

   Questa scheda memorizza anche i **rinuncia** flag per il profilo: quando **[!UICONTROL No longer contact (by any channel)]** è selezionata, il profilo è in elenco Bloccati. Queste informazioni vengono aggiunte ai dati di contatto se, ad esempio, il destinatario ha fatto clic su un collegamento di annullamento all’abbonamento in una newsletter. Tale destinatario non deve più essere indirizzato su alcun canale (e-mail, direct mailing, ecc.). Per ulteriori informazioni, consulta [questa pagina](../send/quarantines.md).

* **Informazioni di contatto**, che contiene l’indirizzo direct mailing del profilo selezionato.

   È possibile controllare in questa schermata l&#39;indice di qualità dell&#39;indirizzo e quanti errori contiene l&#39;indirizzo. Queste informazioni vengono utilizzate direttamente dal provider di direct mailing, in base al numero di errori rilevati durante le consegne precedenti e non possono essere modificate manualmente.

* **Altro**, per campi specifici che possono essere personalizzati e compilati a seconda delle tue esigenze.

   Utilizza la **[!UICONTROL Field properties…]** menu contestuale per modificare i nomi dei campi e definirne il formato.

   ![](assets/other-tab-field-properties.png)

   Immetti le nuove impostazioni come segue:

   ![](assets/change-field-properties.png)

   Controlla l&#39;aggiornamento nell&#39;interfaccia utente:

   ![](assets/other-tab-updated.png)


   >[!CAUTION]
   >Le modifiche si applicano a tutti i destinatari.


* **Abbonamenti**, per tutte le iscrizioni attive ai servizi. Utilizza la **Cronologia** scheda per accedere ai dettagli degli abbonamenti e delle cancellazioni per questo contatto.

   ![](assets/subscription-tab.png)

   Ulteriori informazioni sugli abbonamenti [in questa sezione](../start/subscriptions.md).

* **Consegne**, per tutti i registri di consegna per il profilo selezionato. Utilizza questa scheda per accedere alla cronologia di marketing del contatto: etichette, date e stato di tutte le azioni di consegna indirizzate al profilo tramite tutti i canali.


* **Tracking**, per tutti i registri di tracciamento del profilo selezionato. Queste informazioni vengono utilizzate per tenere traccia del comportamento del profilo dopo le consegne. Questa scheda mostra il totale cumulativo di tutti gli URL tracciati nelle consegne. L’elenco è configurabile e in genere contiene: l’URL su cui hai fatto clic, la data e l’ora del clic e il documento che conteneva l’URL

   Ulteriori informazioni sul tracciamento [in questa sezione](../start/tracking.md).


## Profili attivi {#active-profiles}

I profili attivi sono i profili conteggiati a scopo di fatturazione.

La fatturazione riguarda solo i profili che **attivo**. Un profilo è considerato attivo se è stato eseguito il targeting del profilo o se è stato comunicato con esso negli ultimi 12 mesi tramite qualsiasi canale.

Un profilo per il quale sono state eseguite le destinazioni da più consegne viene conteggiato una sola volta.

Il conteggio dei profili attivi è disponibile per **Istanze di marketing** solo. Non è disponibile per le istanze di esecuzione, ovvero le istanze MID (mid sourcing) e RT (Message Center / Real-time messaging [Centro messaggi/Messaggistica in tempo reale]).

>[!NOTE]
>
>Puoi anche monitorare il numero di profili attivi sulla tua istanza direttamente dal Pannello di controllo Campaign Campaign. Per ulteriori informazioni, consulta la sezione [Documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
