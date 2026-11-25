---
product: campaign
title: Definire il layout dei moduli web
description: Definire il layout dei moduli web
feature: Web Forms
version: Campaign v8, Campaign Classic v7
exl-id: 23ca17f8-de1a-4f9c-8357-3965dc3329b1
TQID: 'https://experienceleague.adobe.com/-0PZWl-79Q-MXZ-jHjp-VF12IUPeMcq27aGSgWl5Ans'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: d0e9f0b2-1f2b-4134-9844-49cd4e950f27
    internal-label: Campaign v8
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: f391046b-0cf3-4e76-bd3b-97fe06654506
    internal-label: Web Apps
  - id: ed29abcd-b6a8-4d4b-ab8b-b7e746973281
    internal-label: Web Forms
  - id: d7be2b01-dc9c-40f7-aace-a151707504ed
    internal-label: Landing pages
source-git-commit: d3b34546c1b08190772154efe6f818b98cc1094c
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 1%
---
# Definire il layout dei moduli web{#defining-web-forms-layout}



## Creazione di contenitori {#creating-containers}

I contenitori consentono di combinare i campi di una pagina, configurarne il layout e organizzare gli elementi nella pagina.

Per ogni pagina del modulo, i contenitori vengono creati tramite il pulsante **[!UICONTROL Containers]** della barra degli strumenti.

![Editor pagina modulo Web con il pulsante della barra degli strumenti Contenitori aperto, che offre l&#39;opzione Contenitore standard](assets/s_ncs_admin_survey_containers_add.png)

Utilizza un contenitore per raggruppare gli elementi della pagina senza aggiungere un’etichetta al rendering finale. Gli elementi sono raggruppati nella sottostruttura contenitore. I contenitori standard consentono di gestire il layout.

Ad esempio:

![Proprietà di pagina con una struttura ad albero composta da due contenitori, informazioni generali e contratti e relativi campi modulo](assets/s_ncs_admin_survey_containers_std_arbo.png)

La posizione delle etichette viene applicata agli elementi posizionati sotto il contenitore nella gerarchia. Se necessario, può essere sovraccaricato per ogni elemento. Aggiungere o rimuovere colonne per modificare il layout. Vedi [Posizionamento dei campi nella pagina](#positioning-the-fields-on-the-page).

Nell’esempio precedente, il rendering sarà il seguente:

![Pagina modulo con rendering con due contenitori: campi dei dettagli personali e un elenco di caselle di controllo del contratto, più un pulsante Convalida](assets/s_ncs_admin_survey_containers_std_ex.png)

## Posizionamento dei campi nella pagina {#positioning-the-fields-on-the-page}

Il layout del modulo web è definito pagina per pagina in ciascun contenitore e, se necessario, può essere sovraccaricato.

Le pagine sono suddivise in colonne: ogni pagina contiene un determinato numero di colonne. Ogni campo della pagina occupa **n** celle. I contenitori occupano anche un determinato numero di colonne e i campi che contengono occupano un determinato numero di celle.

Per impostazione predefinita, le pagine sono create su una singola colonna e ogni elemento occupa una cella. Ciò significa che i campi vengono visualizzati uno sotto l&#39;altro, ciascuno occupando un&#39;intera linea, come illustrato di seguito:

![Pagina modulo a colonna singola con rendering con campi Genere, Nome, Nome e Posta elettronica sovrapposti su righe separate](assets/s_ncs_admin_survey_container_ex.png)

Nell’esempio seguente, è stata mantenuta la configurazione predefinita. La pagina occupa una singola colonna che include quattro contenitori.

![Proprietà pagina con quattro contenitori e numero di colonne impostato su 1 evidenziato](assets/s_ncs_admin_survey_container_ex0.png)

Ogni contenitore occupa una colonna e ogni elemento occupa una cella:

![Proprietà degli elementi di informazione con numero di celle impostato su 1 evidenziato in Impostazioni visualizzazione](assets/s_ncs_admin_survey_container_ex0a.png)

Il rendering è il seguente:

![Rendering di pagine a colonna singola con quattro contenitori, ciascuno con una colonna, impilato verticalmente](assets/s_ncs_admin_survey_container_ex0_rend.png)

È possibile adattare i parametri di visualizzazione per ottenere il seguente rendering:

![Rendering di pagine a due colonne in cui i contenitori 1 e 3 riempiono la colonna sinistra e i contenitori 2 e 4 la destra](assets/s_ncs_admin_survey_container_ex1_rend.png)

Nell’esempio di rendering precedente, ogni campo di input, titolo e immagine occupa una cella nelle colonne dei contenitori.

Puoi modificare la formattazione in ogni contenitore. Nel nostro esempio, puoi distribuire il contenuto del contenitore 4 su due colonne e distribuire gli elementi.

![Contenitore 4 con due colonne: il titolo e la casella combinata contengono una cella ciascuna, la casella di controllo si estende su due celle](assets/s_ncs_admin_survey_container_ex2_rend.png)

Il titolo e l’elenco occupano una cella ciascuno (e quindi un’intera riga del contenitore) e la casella di controllo si estende su due celle. Il numero di celle attribuite al campo di input è definito nella scheda **[!UICONTROL General]** o nella scheda **[!UICONTROL Advanced]**, in base al tipo di campo:

![Scheda avanzata dell&#39;elemento checkbox con numero di celle impostato su 2 in Impostazioni di visualizzazione](assets/s_ncs_admin_survey_container_ex2.png)

## Definizione della posizione delle etichette {#defining-the-position-of-labels}

È possibile definire l&#39;allineamento di campi ed etichette nel modulo.

Per impostazione predefinita, i parametri di visualizzazione per i campi e altro contenuto della pagina vengono ereditati dalla configurazione generale del modulo, dalla configurazione della pagina o dalla configurazione del contenitore principale, se presente.

I parametri di visualizzazione globali per l&#39;intero modulo sono specificati nella casella delle proprietà del modulo. La scheda **[!UICONTROL Rendering]** consente di selezionare la posizione delle etichette.

![Finestra di dialogo Proprietà modulo Web, scheda Rendering, con l&#39;elenco Posizione etichetta: Ereditata, Sinistra, Destra, Sopra, Sotto, Nascosta](assets/s_ncs_admin_survey_label_position.png)

Questa posizione può essere sovraccaricata per ogni pagina, contenitore e campo tramite la scheda **[!UICONTROL Advanced]**.

Sono supportati i seguenti allineamenti:

* Ereditato: l’allineamento viene ereditato dall’elemento padre (valore predefinito), ovvero l’eventuale contenitore principale, oppure dalla pagina.
* Sinistra/Destra: l’etichetta è posizionata a destra o a sinistra del campo,
* Sopra/sotto: l’etichetta è posizionata sopra o sotto il campo,
* Nascosto: l’etichetta non viene visualizzata.
