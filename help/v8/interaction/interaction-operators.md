---
title: Profili operatori
description: Creare operatori di gestione delle offerte
feature: Interaction, Offers
role: User, Admin
level: Beginner
exl-id: 865ddb84-3373-45e0-849d-9d3c92455d22
source-git-commit: 567c2e84433caab708ddb9026dda6f9cb717d032
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---

# Profili operatori {#operator-profiles}

L’interazione con Campaign può essere utilizzata da due tipi di operatori: **Manager offerta** e **Responsabili della consegna**. Ognuno di essi dispone di autorizzazioni e restrizioni specifiche. Ulteriori informazioni sugli operatori e sulle autorizzazioni di Campaign in [questa pagina](../start/gs-permissions.md).

* Il **[!UICONTROL Offer manager]** crea e mantiene le offerte.
* Il **[!UICONTROL Delivery manager]** approva e utilizza le offerte

## Creare un operatore di Gestione offerte{#offer-manager}

1. Crea un operatore. [Ulteriori informazioni](../start/manage-permissions.md#add-users)
1. Accedi a **[!UICONTROL Groups and named rights]** finestra, fai clic su **[!UICONTROL Add]** e seleziona la **[!UICONTROL Offer manager]** gruppo.

Sono descritte le autorizzazioni associate ai gestori delle offerte [qui](../start/manage-permissions.md#ootb-productprofiles)

## Creare un operatore di Delivery Manager {#delivery-manager}

1. Crea un operatore. [Ulteriori informazioni](../start/manage-permissions.md#add-users)
1. Accedi a **[!UICONTROL Groups and named rights]** , fare clic su **[!UICONTROL Add]** e seleziona la **[!UICONTROL Delivery manager]** gruppo.

I diritti assegnati ai responsabili delle consegne consentono loro di svolgere i seguenti compiti:

* Visualizzazione **[!UICONTROL Live]** ambienti.
* Visualizzare e modificare le categorie di offerta.
* Approva le offerte se sono i loro revisori.

  >[!NOTE]
  >
  >**Responsabili della consegna** può approvare un’offerta solo se è stata dichiarata come revisore nella configurazione dell’offerta.

## Matrice di autorizzazione per operatore di interazione {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gestione offerte (ambiente di progettazione)</strong><br /> </td> 
   <td> <strong>Gestione offerte (ambiente live)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Livello struttura ad albero</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Offerte in fase di modifica / Offerte live<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatario - Ambiente<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Amministrazione<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Spaces<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> filtri di offerta predefiniti<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipologia<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Regole di tipologia<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Catalogo delle offerte<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria di offerta<br /> </td> 
   <td> Lettura/scrittura<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Responsabile della consegna (ambiente di progettazione)</strong><br /> </td> 
   <td> <strong>Gestione consegne (ambiente live)</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Livello struttura ad albero</strong><br /> </td> 
   <td> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Offerte in fase di modifica / Offerte live<br /> </td> 
   <td> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Destinatario - Ambiente<br /> </td> 
   <td> </td> 
   <td> Letto<br /> </td> 
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
   <td> filtri di offerta predefiniti<br /> </td> 
   <td> Letto<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipologia<br /> </td> 
   <td> Letto<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Regole di tipologia<br /> </td> 
   <td> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Catalogo delle offerte<br /> </td> 
   <td> Letto<br /> </td> 
   <td> Letto<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoria di offerta<br /> </td> 
   <td> </td> 
   <td> Letto<br /> </td> 
  </tr> 
 </tbody> 
</table>
