---
solution: Campaign
product: Adobe Campaign
title: Matrice di compatibilità di Campaign v8
description: Scopri i sistemi e le versioni compatibili con Campaign v8
feature: Panoramica
role: Data Engineer
level: Beginner
exl-id: 4be3a6dc-0c61-4534-b9dd-6c99c8a037a9,870a336f-94ac-4171-891b-67614feef6ef,bebdd930-c7f6-4629-a489-3c704b33f058,d493e613-eb61-43b1-9c6d-1bd881af0734
translation-type: tm+mt
source-git-commit: 3419ede105f652f0a33362468a7d119687c078de
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 25%

---

# Matrice di compatibilità di Campaign v8

In questo documento sono elencati tutti i sistemi e i componenti supportati per la build più recente di **Adobe Campaign v8**. I prodotti e le versioni che non fanno parte di questo elenco non sono compatibili con Adobe Campaign.

>[!CAUTION]
>
>* Salvo diversa indicazione, sono supportate tutte le versioni minori.
>* Poiché versioni specifiche di questi sistemi e strumenti di terze parti raggiungono la fine del ciclo di vita (EOL), Adobe Campaign non sarà più compatibile con tali versioni e verranno rimosse da questa matrice di compatibilità. Assicurati di disporre delle versioni supportate di tutti i sistemi elencati nella matrice di compatibilità per evitare problemi.


## Sistemi compatibili

### Connettori di gestione delle relazioni con i clienti{#CRMconnectors}

* **** API Salesforceconnector versione 49
* **Microsoft** Dynamicsconnector, API Web: Dynamics 365 on-premise e online

### Federated Data Access (FDA){#FederatedDataAccessFDA}

* **Microsoft Azure Synapse Analytics**
* **Amazon Redshift**
* **[!DNL Snowflake]**
* **Oracle** 19c, 18c, 12c, 11G
* **PostgreSQL** 12.x, 11.x, 10.x, 9.6.x, 9.5.x, 9.4.x
* **Microsoft SQL Server** 2019, 2017, 2016, 2014, 2012 SP1 e SP2
* **MySQL** 5.7
* **Teradata** 16.20, 16, 15.10, 15.0
* **Netezza** 7.2
* **sybase IQ** 16, ASE 15.7
* **SAP** HANAversione 1 SPS 12
* **Hadoop tramite HiveSQL**
   * HortonWorks HDP 2.4.X, 2.5.x, 2.6.x
   * HDInsight 3.4 (HDP 2.4), 3.5 (HDP 2.5), 3.6 (HDP 2.6
   * Cloudera CDH6.x

### Console client{#ClientConsoleoperatingsystems}

:warning: Per utilizzare la console client di Campaign sono necessari i seguenti sistemi operativi e browser.

**Sistemi operativi**

* **Microsoft Windows Server** 2016, 2012
* **Microsoft Windows** 8, 10 (consigliato per le istanze giapponesi)

**Browser**

Microsoft Internet Explorer 11

### SDK per dispositivi mobili{#MobileSDK}

* **Android** 7.x, 8.x, 9.0 con SDK mobile versione 1.0.27.
* **Apple iOS** 9 - 14 con SDK mobile versione 1.0.26, compatibile con le versioni a 32 e 64 bit.

### Browser supportati {#Browsers}

I seguenti browser sono compatibili con Campaign per Web Access.

* **Microsoft Edge**,  **Mozilla Firefox**,  **Google Chrome**,  **Safari**  (versioni più recenti)

* **Internet Explorer** 11

## Controllare la versione Campaign

Il menu **Aiuto > Informazioni su...** consente di accedere alle seguenti informazioni:

* il numero di versione per la console client di Campaign e il server applicazioni
* numero di build per la console client e il server applicazioni di Campaign
* un collegamento per contattare l’Assistenza clienti Adobe
* collegamenti ad Adobe Privacy Policy, Condizioni d&#39;uso e Politica sui cookie
