---
title: Profili degli operatori
description: Creare operatori di gestione delle offerte
feature: Interaction, Offers
role: Data Engineer
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: eed3396584940f99a865eef2358887b6bf5c4936
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 8%

---

# Profili degli operatori {#operator-profiles}

Due tipi di operatori possono utilizzare l’interazione con Campaign: **Gestori di offerte** e **Gestori di consegna**. Ognuno di essi dispone di autorizzazioni e restrizioni specifiche. Ulteriori informazioni sugli operatori e sulle autorizzazioni di Campaign in [questa pagina](../start/gs-permissions.md).

* La **[!UICONTROL Offer manager]** crea e gestisce le offerte.
* La **[!UICONTROL Delivery manager]** approva e utilizza le offerte

## Creare un operatore di Gestione offerte{#offer-manager}

1. Crea un operatore. [Ulteriori informazioni](../start/manage-permissions.md#add-users)
1. Sfoglia il **[!UICONTROL Groups and named rights]** finestra, fai clic su **[!UICONTROL Add]** e seleziona la **[!UICONTROL Offer manager]** gruppo.

Sono descritte le autorizzazioni associate ai gestori delle offerte [qui](../start/manage-permissions.md#ootb-productprofiles)

## Creare un operatore di Delivery Manager {#delivery-manager}

1. Crea un operatore. [Ulteriori informazioni](../start/manage-permissions.md#add-users)
1. Sfoglia il **[!UICONTROL Groups and named rights]** scheda , fai clic su **[!UICONTROL Add]** e seleziona la **[!UICONTROL Delivery manager]** gruppo.

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
   <td> Categoria offerta<br /> </td> 
   <td> </td> 
   <td> Leggi<br /> </td> 
  </tr> 
 </tbody> 
</table>
