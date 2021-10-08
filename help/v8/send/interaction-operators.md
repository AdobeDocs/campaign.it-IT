---
title: Operatori di interazione campagna
description: Creare operatori di gestione delle offerte
feature: Overview
role: Data Engineer
level: Beginner
source-git-commit: 391eac2f5e4d4c8c5d4dadd3394798361640e1d8
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 1%

---

# Profili degli operatori {#operator-profiles}

Due tipi di operatori possono utilizzare l’interazione con Campaign: **Gestione offerte** e **Manager consegna**. Ognuno di essi dispone di autorizzazioni e restrizioni specifiche. Ulteriori informazioni sugli operatori e sulle autorizzazioni di Campaign in [questa pagina](../start/permissions.md).

* Il **[!UICONTROL Offer manager]** crea e gestisce le offerte.
* Il **[!UICONTROL Delivery manager]** approva e utilizza le offerte

## Creare un operatore di Gestione offerte{#offer-manager}

1. Crea un operatore.

   ![](../assets/do-not-localize/book.png) I passaggi per creare un operatore in Campaign sono descritti in dettaglio nella documentazione di  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vai alla finestra **[!UICONTROL Groups and named rights]**, fai clic su **[!UICONTROL Add]** e seleziona il gruppo **[!UICONTROL Offer manager]**.

I diritti assegnati al gestore di offerte consentono loro di eseguire le seguenti attività:

* Modificare gli ambienti **[!UICONTROL Design]**.
* Visualizzare gli ambienti **[!UICONTROL Live]**.
* Configura le funzioni di amministrazione (spazi e filtri predefiniti).
* Creare e modificare le categorie.
* Creare offerte.
* Configura l’idoneità delle offerte.
* Approvare le offerte.

Se le offerte sono utilizzate in un flusso di lavoro, l’operatore deve essere aggiunto al gruppo di operatori **[!UICONTROL Administrator]** o **[!UICONTROL Offer managers]** per eseguire il flusso di lavoro.

>[!NOTE]
>
>**Il** gestore delle offerte approva un’offerta solo se non è specificato alcun revisore o se è stato dichiarato come revisori nel modello di offerta.

## Creare un operatore di Delivery Manager {#delivery-manager}

1. Crea un operatore.

   ![](../assets/do-not-localize/book.png) I passaggi per creare un operatore in Campaign sono descritti in dettaglio nella documentazione di  [Campaign Classic v7 .](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vai alla finestra **[!UICONTROL Groups and named rights]**, fai clic su **[!UICONTROL Add]** e seleziona il gruppo **[!UICONTROL Delivery manager]**.

I diritti assegnati ai gestori della consegna consentono loro di svolgere i seguenti compiti:

* Visualizzare gli ambienti **[!UICONTROL Live]**.
* Visualizza e modifica le categorie di offerte.
* Approva le offerte se sono i loro revisori.

   >[!NOTE]
   >
   >**Il** gestore delle consegne può approvare un’offerta solo se è stato dichiarato come revisore nella configurazione dell’offerta.

## Matrice di autorizzazioni per operatore di interazione {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gestione delle offerte (ambiente di progettazione)</strong><br /> </td> 
   <td> <strong>Gestione delle offerte (ambiente live)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Livello struttura ad albero</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Offerte in corso di modifica / Offerte live<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatario - Ambiente<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Amministrazione<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Spaces<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtri di offerta predefiniti<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipologia<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Regole di tipologia<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Catalogo delle offerte<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria offerta<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Responsabile consegna (env. progettazione)</strong><br /> </td> 
   <td> <strong>Delivery manager (Live env)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Livello struttura ad albero</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Offerte in corso di modifica / Offerte live<br /> </td> 
   <td> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatario - Ambiente<br /> </td> 
   <td> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Amministrazione<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Spaces<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Filtri di offerta predefiniti<br /> </td> 
   <td> Leggi<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipologia<br /> </td> 
   <td> Leggi<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Regole di tipologia<br /> </td> 
   <td> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Catalogo delle offerte<br /> </td> 
   <td> Leggi<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria offerta<br /> </td> 
   <td> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
 </tbody> 
</table>
