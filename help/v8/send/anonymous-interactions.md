---
product: campaign
title: Offerte presenti ai profili anonimi (interazione in entrata)
description: Scopri come presentare offerte ai profili anonimi
source-git-commit: c19336c84114a0c81563c4d5ae760330d3b284cb
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%

---

# Interazioni anonime{#anonymous-interactions}

## Ambiente per interazioni anonime {#environment-for-anonymous-interactions}

Per impostazione predefinita, Campaign **Interazione** Il modulo viene fornito con un ambiente preconfigurato per eseguire il targeting della tabella dei destinatari integrata (offerte identificate). Se devi eseguire il targeting di un’altra tabella, di una tabella di visitatori per offerte anonime o di una tabella di destinatari personalizzata, ad esempio, per creare l’ambiente devi utilizzare la procedura guidata di mappatura di destinazione . [Ulteriori informazioni sugli ambienti](interaction-env.md).

Quando crei un ambiente anonimo tramite la procedura guidata di creazione della mappatura, la **[!UICONTROL Environment dedicated to incoming anonymous interactions]** viene selezionato automaticamente nel **[!UICONTROL General]** scheda .

La **[!UICONTROL Targeting dimension]** viene completato automaticamente. Per impostazione predefinita, si collega alla tabella dei visitatori.

La **[!UICONTROL Visitor folder]** viene visualizzato il campo . Viene automaticamente completato per il collegamento al **[!UICONTROL Visitors]** cartella. Questo campo ti consente di scegliere dove memorizzare i profili dei visitatori.

![](assets/anonymous_environment_option.png)

>[!NOTE]
>
>Se desideri filtrare diversi tipi di visitatori, ad esempio nel caso di offerte anonime presentate per uno o più marchi, devi creare un ambiente per ogni marchio e un **[!UICONTROL Visitors]** digitare la cartella per ogni ambiente.

## Catalogo delle offerte per interazioni anonime {#offer-catalog-for-anonymous-interactions}

Proprio come le interazioni in uscita, le interazioni in entrata sono organizzate in un catalogo di offerte composto da categorie e offerte.

Per creare categorie e spazi, applica lo stesso processo dei visitatori identificati. Fai riferimento a [Creare una categoria di offerta](interaction-offer-catalog.md#creating-offer-categories) e [Creare un ambiente di offerta](interaction-env.md#creating-an-offer-environment)).

## Visitatori anonimi {#anonymous-visitors}

I visitatori anonimi possono essere sottoposti a un processo di identificazione dei cookie al momento della connessione. Questo riconoscimento implicito si basa sulla cronologia del browser del visitatore.

Durante questo passaggio viene effettuato un confronto tra i dati recuperati dai cookie e quelli presenti nel database. In alcuni casi, i visitatori vengono riconosciuti (sono quindi identificati implicitamente), in altri casi non vengono riconosciuti (e quindi rimangono anonimi).

Per eseguire questa analisi, per lo spazio di offerta, controlla la **[!UICONTROL Implicitly identify the individual based on their browser history]** opzione .

![](assets/identification_anonymous_visitors.png)

## Elaborazione di visitatori anonimi non identificati {#processing-unidentified-anonymous-visitors}

Dopo l’analisi, se un visitatore anonimo non è identificato, puoi memorizzare i suoi dati in uno spazio specifico. Questo ti consente di suggerire offerte specificamente mirate a questo tipo di visitatore, che corrispondono alle regole di tipologia specificate.

Se non esiste un elemento che ti consenta di identificare un contatto, o se non desideri suggerire un&#39;offerta identificata a un contatto che possa essere identificato implicitamente, puoi scegliere di eseguire un fallback su un ambiente anonimo.

Per eseguire questa operazione, controlla il **[!UICONTROL Fall back on an anonymous environment if no individuals were identified]**, quindi specifica l’ambiente dedicato a questi visitatori non identificati nel **[!UICONTROL Linked anonymous space]** quando si specifica uno spazio di offerta.

![](assets/anonymous_to_anonymous_environment.png)
