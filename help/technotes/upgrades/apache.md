---
product: campaign
title: Nota tecnica - Adobe Campaign - Aggiornamento sulla sicurezza della versione di Apache
description: Adobe Campaign - Aggiornamento sulla sicurezza della versione di Apache
hide: true
hidefromtoc: true
exl-id: 68e42fe4-7fb6-4b53-9f39-e77374e3753d
source-git-commit: 50dcdf1f6bcc8c8a195a0bf0a37af254f33b80d5
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 0%

---

# Adobe Campaign - Aggiornamento sulla sicurezza della versione di Apache {#apache-update}

>[!CAUTION]
>Il presente articolo si applica a: clienti Campaign Classic v7 Managed Cloud Services, clienti Campaign v8 e clienti Campaign Standard.

Adobe Campaign funziona con strumenti di terze parti e la compatibilità viene aggiornata regolarmente, al fine di implementare solo le versioni supportate e beneficiare delle correzioni e dei miglioramenti più recenti.

Adobe Campaign include Apache Tomcat che funge da punto di ingresso nel server applicazioni tramite HTTP ed è integrato con il server web Apache. Apache Software Foundation ha rilasciato Apache HTTP Server 2.4.53. Questa versione affronta le vulnerabilità che possono consentire a un utente malintenzionato remoto di prendere il controllo di un sistema interessato. Ulteriori informazioni sono disponibili nell&#39;annuncio di [Apache 2.4.53](https://downloads.apache.org/httpd/Announcement2.4.html){target="_blank"}.

Il team di Adobe Campaign eseguirà l’attività di aggiornamento della sicurezza della versione di Apache entro il **15 giugno 2022** per mitigare questa vulnerabilità di Apache e rendere più sicuro l’ambiente delle istanze. Questo aggiornamento si applica a tutti i clienti di Campaign Classic v7 Managed Cloud Services, Campaign v8 e Campaign Standard che eseguono su una versione vulnerabile di Apache HTTP Server. Se sei interessato, Adobe ti ha già contattato per informarti su questo aggiornamento.

Questo aggiornamento dovrebbe essere eseguito automaticamente al di fuori del normale orario di lavoro per consentire di continuare a utilizzare il servizio Campaign senza interruzioni.

Le istanze non di produzione verranno aggiornate dai nostri team prima di aggiornare le istanze di produzione. Poiché si tratta di un processo di aggiornamento automatico di proprietà di Adobe, non è necessaria alcuna azione da parte tua. Tuttavia, in caso di problemi, contatta l&#39;[Assistenza clienti Adobe](https://experienceleague.adobe.com/it?support-solution=Campaign#support){target="_blank"}.


>[!NOTE]
>Questo aggiornamento richiede il riavvio del server web Apache. I tempi di inattività non superano i 10 minuti nell&#39;intervallo indicato di seguito.
> 

## Domande frequenti {#apache-faq}

* **Perché si tratta di un aggiornamento obbligatorio?**

  L’attuale versione di Apache è vulnerabile e presenta una potenziale minaccia per la sicurezza. È importante che le istanze di Campaign siano aggiornate alla versione di Apache più recente applicabile per evitare rischi per la sicurezza.


* **Quali clienti sono destinatari degli aggiornamenti di sicurezza?**

  Tutti i clienti che utilizzano ambienti Campaign implementati su versioni precedenti di Apache vengono aggiornati all’ultima versione di Apache applicabile.

* **Quali sono i tempi di inattività previsti?**

  Il tempo di inattività previsto è inferiore a 10 minuti.

* **Sono richieste azioni dal cliente per questo aggiornamento della sicurezza?**

  Non è richiesta alcuna azione poiché l&#39;aggiornamento della sicurezza verrà eseguito automaticamente.

* **Quali convalide devono essere eseguite dai clienti?**

  Non sono necessari test specifici per questo aggiornamento della sicurezza. In caso di problemi, contatta l&#39;[Assistenza clienti Adobe](https://experienceleague.adobe.com/it?support-solution=Campaign#support){target="_blank"}.


* **Posso richiedere una modifica di data/ora nello slot di aggiornamento della sicurezza pianificato?**

  Poiché si tratta di una correzione di sicurezza, si consiglia vivamente di adattarsi alla pianificazione esistente.


Per qualsiasi altra domanda, puoi contattare l&#39;[Assistenza clienti Adobe](https://experienceleague.adobe.com/it?support-solution=Campaign#support){target="_blank"}.
