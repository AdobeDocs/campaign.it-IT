---
title: Impostazioni sulla consegna SMS
description: Scopri come impostare una consegna SMS
feature: SMS
role: User
level: Beginner, Intermediate
exl-id: c4d500ef-2339-491f-9ae2-9bfaf72088a9
source-git-commit: 6f29a7f157c167cae6d304f5d972e2e958a56ec8
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 1%

---

# Impostazioni sulla consegna SMS {#sms-settings}

>[!IMPORTANT]
>
>Questa documentazione si applica ad Adobe Campaign v8.7.2 e versioni successive. Per passare dalla versione precedente al nuovo connettore SMS, fai riferimento a questa [nota tecnica](https://experienceleague.adobe.com/docs/campaign/technotes-ac/tn-new/sms-migration){target="_blank"}
>
>Per le versioni precedenti, leggere la [documentazione di Campaign Classic v7](https://experienceleague.adobe.com/en/docs/campaign-classic/using/sending-messages/sending-messages-on-mobiles/sms-set-up/sms-set-up){target="_blank"}.

Le impostazioni tecniche necessarie per una consegna SMS sono:

* L’account esterno SMPP per il routing dei messaggi. [Ulteriori informazioni](smpp-external-account.md#smpp-connection-settings)
* Configura la scheda SMS. [Scopri come](#sms-tab)

Puoi impostarli tutti in un modello di consegna per evitare di eseguire le impostazioni per ogni creazione di consegna SMS.

## Configurare la scheda SMS {#sms-tab}

![](assets/send_settings.png){zoomable="yes"}

Queste sono le informazioni necessarie per compilare il modulo. Ogni campo è spiegato di seguito:

* **[!UICONTROL Sender address]**

  Questo campo è facoltativo. Consente di ignorare l’indirizzo del mittente (oADC). Il contenuto di questo campo viene inserito nel campo *source_addr* della PDU SUBMIT_SM.

  La specifica SMPP limita il campo a 21 caratteri, ma alcuni provider possono consentire valori più lunghi. Tieni presente che in alcuni paesi possono essere applicate restrizioni molto rigide (lunghezza, contenuto, caratteri consentiti, ecc.), pertanto potrebbe essere necessario verificare che il contenuto inserito qui sia legale. Presta particolare attenzione quando utilizzi campi personalizzati.

  Se questo campo viene lasciato vuoto, verrà utilizzato il valore del campo del numero di Source definito nell’account esterno. Se entrambi i valori sono vuoti, il campo *source_addr* verrà lasciato vuoto.

* **[!UICONTROL Service or program ID]**

  >[!NOTE]
  >
  >L’utilizzo di questa funzione è sconsigliato. I parametri SMPP opzionali forniscono un’implementazione molto più flessibile.
  >
  >Entrambe le funzioni non possono essere utilizzate contemporaneamente.

  In combinazione con l’impostazione dell’account esterno corrispondente, consente di inviare un parametro opzionale con ogni messaggio MT. Questo campo definisce la parte relativa al valore del TLV.

* **[!UICONTROL Transmission mode]**

  Questo campo indica il tipo di SMS che desideri trasferire: messaggi normali o flash, memorizzati sul cellulare o sulla scheda SIM. Questa impostazione viene trasmessa nel campo facoltativo dest_addr_subunit nella PDU SUBMIT_SM.

   * **Flash** imposta il valore su 1. Invia un messaggio flash che viene visualizzato sul dispositivo mobile e non viene memorizzato.
   * **Normal** imposta il valore su 0. Invia un messaggio normale.
   * **Salva su dispositivo mobile** imposta il valore su 2. Indica al telefono di memorizzare l’SMS nella memoria interna.
   * **Salva nel terminale** imposta il valore su 3. Indica al telefono di memorizzare l’SMS nella scheda SIM.

* **[!UICONTROL Priority, Communication type]**

  Questi campi vengono ignorati dal connettore SMPP esteso.

* **[!UICONTROL Maximum number of SMS per message]**

  Questa impostazione funziona solo se l’impostazione del payload del messaggio è disabilitata (consulta nelle impostazioni dell’account esterno per ulteriori informazioni). Se il messaggio richiede più SMS di questo valore, viene attivato un errore.

  Il protocollo SMS limita gli SMS a 255 parti, ma alcuni telefoni cellulari hanno problemi a mettere insieme messaggi lunghi con più di 10 parti o giù di lì (il limite dipende dal modello esatto). Se vuoi essere sicuro, non superare le 5 parti per messaggio.

  A causa del funzionamento dei messaggi personalizzati in Adobe Campaign, le dimensioni dei messaggi possono variare, pertanto la quantità di messaggi molto lunghi può aumentare notevolmente i costi di invio: impostando un valore ragionevole si contribuisce a controllare questi costi.

  Specificando 0 si disabilita il limite.

* **[!UICONTROL Optional SMPP parameters (TLV)]**
Puoi specificare campi aggiuntivi da inviare come parametri SMPP (TLV) facoltativi. Questi campi aggiuntivi vengono inviati con ogni messaggio MT e i campi personalizzati consentono di avere valori diversi per ogni messaggio MT.
Nella tabella sono elencati i parametri facoltativi da inviare con ogni messaggio. Le colonne contengono le seguenti informazioni:
   * **Etichetta**: etichetta facoltativa in formato libero. Non viene trasmesso al provider. Puoi fornire una descrizione testuale del parametro.
   * **Tag**: il valore del tag, in formato decimale (ad esempio 12345) o esadecimale con prefisso 0x (ad esempio 0x12ab). I tag possono essere compresi tra 0 e 65535. Chiedi al provider di servizi SMPP i tag supportati.
   * **Valore**: valore da inviare nel parametro facoltativo. Questo è un campo personalizzato.
   * **Formato**: codifica utilizzata per il parametro. È possibile selezionare qualsiasi codifica di testo supportata o i formati binari più comuni. Chiedi al provider di servizi SMPP il formato richiesto.
   * **Lunghezza massima**: numero massimo di byte per questo parametro. Questa opzione viene ignorata per i campi binari in quanto i campi binari hanno una dimensione fissa.

* **[!UICONTROL Using binary formats for TLV]**

  Campaign supporta l’invio di TLV in formato binario. Il binario è limitato all&#39;invio di numeri.

  Poiché i campi personalizzati producono sempre del testo, il campo personalizzato deve contenere una rappresentazione decimale del numero (qualsiasi stringa va bene purché contenga solo cifre). I valori possono essere firmati o non firmati; il motore di personalizzazione li converte semplicemente nella rappresentazione binaria corretta.

  Quando si utilizzano formati binari, i valori speciali &quot;&quot; (stringa vuota), &quot;null&quot; e &quot;undefined&quot; disabilitano completamente il campo senza generare un errore. In questi 3 casi speciali, il tag non viene passato. Questo consente di trasmettere un TLV specifico solo per alcuni messaggi quando si utilizza JavaScript creato con attenzione nel campo di personalizzazione.

  >[!NOTE]
  >
  >I formati binari sono sempre codificati in formato big-endian.

