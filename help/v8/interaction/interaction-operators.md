---
title: Profili degli operatori
description: Creare operatori di gestione delle offerte
feature: Overview
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: d2f4e54b0c37cc019061dd3a7b7048cd80876ac0
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 1%

---

# Profili degli operatori {#operator-profiles}

Due tipi di operatori possono utilizzare l’interazione con Campaign: **Gestori di offerte** e **Gestori di consegna**. Ognuno di essi dispone di autorizzazioni e restrizioni specifiche. Ulteriori informazioni sugli operatori e sulle autorizzazioni di Campaign in [questa pagina](../start/permissions.md).

* La **[!UICONTROL Offer manager]** crea e gestisce le offerte.
* La **[!UICONTROL Delivery manager]** approva e utilizza le offerte

## Creare un operatore di Gestione offerte{#offer-manager}

1. Crea un operatore.

   ![](../assets/do-not-localize/book.png) I passaggi per creare un operatore in Campaign sono descritti in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vai a **[!UICONTROL Groups and named rights]** finestra, fai clic su **[!UICONTROL Add]** e seleziona la **[!UICONTROL Offer manager]** gruppo.

I diritti assegnati al gestore di offerte consentono loro di eseguire le seguenti attività:

* Modifica **[!UICONTROL Design]** ambienti.
* Visualizza **[!UICONTROL Live]** ambienti.
* Configura le funzioni di amministrazione (spazi e filtri predefiniti).
* Creare e modificare le categorie.
* Creare offerte.
* Configura l’idoneità delle offerte.
* Approvare le offerte.

Se le offerte vengono utilizzate in un flusso di lavoro, l’operatore deve essere aggiunto al **[!UICONTROL Administrator]** o **[!UICONTROL Offer managers]** gruppo di operatori per eseguire il flusso di lavoro.

>[!NOTE]
>
>**Gestori di offerte** può approvare un’offerta solo se non è stato specificato alcun revisore o se è stato dichiarato come revisori nel modello di offerta.

## Creare un operatore di Delivery Manager {#delivery-manager}

1. Crea un operatore.

   ![](../assets/do-not-localize/book.png) I passaggi per creare un operatore in Campaign sono descritti in [Documentazione di Campaign Classic v7](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vai a **[!UICONTROL Groups and named rights]** finestra, fai clic su **[!UICONTROL Add]** e seleziona la **[!UICONTROL Delivery manager]** gruppo.

I diritti assegnati ai gestori della consegna consentono loro di svolgere i seguenti compiti:

* Visualizzazione **[!UICONTROL Live]** ambienti.
* Visualizza e modifica le categorie di offerte.
* Approva le offerte se sono i loro revisori.

   >[!NOTE]
   >
   >**Gestori di consegna** può approvare un’offerta solo se è stata dichiarata come revisore nella configurazione dell’offerta.

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
   <td> Spazi<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
  <tr> 
   <td> filtri di offerta predefiniti<br /> </td> 
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
   <td> Categoria di offerta<br /> </td> 
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
   <td> Spazi<br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> filtri di offerta predefiniti<br /> </td> 
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
   <td> Categoria di offerta<br /> </td> 
   <td> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
 </tbody> 
</table>
