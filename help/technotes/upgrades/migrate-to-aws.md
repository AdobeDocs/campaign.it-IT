---
title: Migrazione dell’infrastruttura di invio di Campaign ad Amazon Web Services (AWS)
description: Migrazione dell’infrastruttura di invio di Campaign ad Amazon Web Services (AWS)
hide: true
hidefromtoc: true
exl-id: 50279a2f-0296-43f5-8967-16cc6a0c88f6
source-git-commit: 3e95a56825a143a4457ab7ee242208d7daaeb414
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 0%

---

# Campaign invio della migrazione dell’infrastruttura ad Amazon Web Services (AWS) {#migrate-infra-to-aws}

## Cosa è cambiato?{#aws-changes}

Come parte del nostro impegno continuo per fornire il servizio di consegna e-mail di qualità più elevata, l’infrastruttura di invio e-mail di Campaign viene spostata dai centri dati ospitati da Adobe ad Amazon Web Services (AWS).

Questo passaggio garantirà un&#39;elevata disponibilità, un throughput ottimale e la possibilità di scalabilità per soddisfare le esigenze dei clienti.

## Sei interessato?{#aws-impact}

Questa modifica interessa:

* Clienti Campaign Classic v7 in hosting e ibridi
* Clienti di Campaign Managed Services
* Tutti i clienti di Campaign v8
* Clienti Campaign Standard

## Quando avverrà questa migrazione?{#aws-timeline}

La migrazione degli ambienti di sviluppo e staging avrà luogo il **ottobre 2023**.

La migrazione degli ambienti di produzione deve iniziare il **gennaio 2024**. Ulteriori dettagli verranno forniti con l’approssimarsi della data.

In qualità di cliente di Campaign, riceverai una notifica aggiuntiva durante la pianificazione delle ondate di migrazione. Le notifiche vengono inviate almeno 7 giorni prima della migrazione per gli ambienti di staging e almeno 30 giorni prima della migrazione per gli ambienti di produzione.

## Qual è l&#39;impatto?{#impact}

Questo passaggio sarà trasparente per i clienti:

* La lunghezza di ogni ondata di migrazione può variare a seconda del numero di istanze di Campaign interessate. Quando è pianificata un’ondata di migrazione, la notifica includerà la durata prevista.

* Le istanze di Campaign non saranno in grado di inviare messaggi e-mail durante la finestra di migrazione. Non verrà interessata nessun’altra funzione di Campaign.


## Domande frequenti {#aws-faq}

* **Perché si tratta di un aggiornamento obbligatorio?**

  Adobe pianifica di smantellare il datacenter legacy; le istanze Adobe Campaign in esecuzione in tale data center devono essere trasferite al nuovo datacenter di riferimento, Amazon Web Services (AWS).

  Il cloud Managed Services di Adobe è ospitato su Amazon Web Services (AWS), un ambiente moderno, sicuro e ottimizzato. [Ulteriori informazioni su Amazon Web Services](https://aws.amazon.com/application-hosting/benefits/){target="_blank"}.

* **Quali clienti sono destinatari di questa migrazione?**

  Tutti i clienti Campaign v8 e Campaign Classic v7 ibridi, in hosting e Campaign Managed Services avranno la migrazione dei loro ambienti. Anche i clienti Campaign Standard sono interessati.

* **Quali sono i tempi di inattività previsti?**

  La migrazione dovrebbe richiedere tra 30 minuti e 60 minuti, ma la lunghezza di ogni ondata di migrazione potrebbe variare a seconda del numero di istanze di Campaign interessate. Quando è pianificata un’ondata di migrazione, la notifica includerà la durata prevista.

* **Il cliente ha bisogno di eseguire una migrazione?**

  Non è richiesta alcuna azione in quanto la migrazione verrà eseguita automaticamente da Adobe.

* **Quali convalide devono essere eseguite dai clienti?**

  Per questa migrazione non è necessario alcun test specifico. In caso di problemi, contatta l&#39;[Assistenza clienti Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.


* **Posso richiedere una modifica di data/ora nello slot di aggiornamento della sicurezza pianificato?**

  Poiché si tratta di una migrazione obbligatoria, non possiamo accettare modifiche alla pianificazione esistente.

Per qualsiasi altra domanda, puoi contattare [l&#39;Assistenza clienti Adobe](https://experienceleague.adobe.com/?support-solution=Campaign#support){target="_blank"}.
