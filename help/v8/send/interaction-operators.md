---
solution: Campaign
product: Adobe Campaign
title: Operatori di interazione campagna
description: Creare operatori di gestione delle offerte
feature: Panoramica
role: Data Engineer
level: Beginner
translation-type: tm+mt
source-git-commit: b9de052de5aaeee4b089feb70bf20723be5c9cfa
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 1%

---


# Profili operatori {#operator-profiles}

Due tipi di operatori possono utilizzare l’interazione con Campaign: **Gestione offerte** e **Manager consegna**. Ognuno di essi dispone di autorizzazioni e restrizioni specifiche. Ulteriori informazioni sugli operatori e sulle autorizzazioni di Campaign in [questa pagina](../start/permissions.md).

* Il **[!UICONTROL Offer manager]** crea e gestisce le offerte.
* Il **[!UICONTROL Delivery manager]** approva e utilizza le offerte

## Creare un operatore Offer Manager{#offer-manager}

1. Crea un nuovo operatore.

:arrow_Upper_right: I passaggi per creare un operatore in Campaign sono descritti in [Documentazione Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vai alla finestra **[!UICONTROL Groups and named rights]**, fai clic su **[!UICONTROL Add]** e seleziona il gruppo **[!UICONTROL Offer manager]**.

I diritti assegnati al gestore di offerte consentono loro di eseguire le seguenti attività:

* Modificare gli ambienti **[!UICONTROL Design]**.
* Visualizzare gli ambienti **[!UICONTROL Live]**.
* Configura le funzioni di amministrazione (spazi e filtri predefiniti).
* Creare e modificare le categorie.
* Creare offerte.
* Configura l’idoneità delle offerte.
* Approvare le offerte.

Nota che se le offerte sono utilizzate in un flusso di lavoro, l’operatore deve essere aggiunto al gruppo di operatori **[!UICONTROL Administrator]** o **[!UICONTROL Offer managers]** per eseguire il flusso di lavoro.

>[!NOTE]
>
>Un **gestore offerte** può approvare un&#39;offerta solo se non è specificato alcun revisore o se è stato dichiarato come revisore nel modello di offerta su cui si basa l&#39;offerta.

## Creare un operatore di Delivery Manager {#delivery-manager}

1. Crea un nuovo operatore.

:arrow_Upper_right: I passaggi per creare un operatore in Campaign sono descritti in [Documentazione Campaign Classic](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/permissions/access-management-operators.html)

1. Vai alla finestra **[!UICONTROL Groups and named rights]**, fai clic su **[!UICONTROL Add]** e seleziona il gruppo **[!UICONTROL Delivery manager]**.

I diritti assegnati al gestore della consegna sono/consentono loro di eseguire le seguenti attività:

* Visualizzare gli ambienti **[!UICONTROL Live]**.
* Visualizza e modifica le categorie di offerte.
* Approva le offerte se s/he è specificato come uno dei suoi revisori.

   >[!NOTE]
   >
   >Un **gestore consegne** può approvare un’offerta solo se è stato dichiarato come revisore durante la configurazione dell’offerta.

## Matrice di autorizzazioni per operatore di interazione {#recap-of-rights-according-to-operator}

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td> <strong>Gestione delle offerte (env di progettazione)</strong><br /> </td> 
   <td> <strong>Gestione delle offerte (Live env)</strong><br /> </td> 
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
   <td> Administration<br /> </td> 
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
