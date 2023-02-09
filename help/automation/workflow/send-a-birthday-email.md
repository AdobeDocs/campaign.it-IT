---
product: campaign
title: Inviare un’e-mail di compleanno
description: Scopri come inviare un’e-mail di compleanno con un flusso di lavoro
feature: Workflows
exl-id: c3a80871-e045-454c-b1ca-8f484d2e14e1
source-git-commit: 190707b8b1ea5f90dc6385c13832fbb01378ca1d
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 2%

---

# Inviare un’e-mail di compleanno{#sending-a-birthday-email}

Questo caso d’uso illustra come pianificare l’invio di un’e-mail ricorrente a un elenco di destinatari il giorno del loro compleanno.

Per impostare questo caso d’uso, abbiamo creato il seguente flusso di lavoro di targeting:

![](assets/birthday-workflow_usecase_1.png)

Questo flusso di lavoro (esecuzione giornaliera) seleziona tutti i destinatari che festeggiano il compleanno alla data corrente.

A questo scopo, crea una campagna e aggiungi una [flusso di lavoro della campagna](campaign-workflows.md).

Quindi segui i passaggi descritti di seguito.

## Identifica i destinatari del compleanno {#identifying-recipients-whose-birthday-it-is}

Dopo aver configurato la **[!UICONTROL Scheduler]** in modo che il flusso di lavoro inizi ogni giorno, identifica tutti i destinatari la cui data di nascita è uguale alla data corrente.

A questo scopo, esegui i seguenti passaggi:

1. Trascina e rilascia una **[!UICONTROL Query]** nel flusso di lavoro e fai doppio clic su di esso.
1. Fai clic sul pulsante **Modifica query** collegamento e seleziona **[!UICONTROL Filtering conditions]**.

   ![](assets/s_ncs_user_create_exp_exple00.png)

1. Fai clic sulla prima cella del **[!UICONTROL Expression]** e fai clic su **[!UICONTROL Edit expression]** per aprire l’editor di espressioni.

   ![](assets/s_ncs_user_create_exp_exple.png)

1. Fai clic su **[!UICONTROL Advanced selection]** per selezionare la modalità di filtro.

   ![](assets/s_ncs_user_create_exp_exple_a.png)

1. Seleziona **[!UICONTROL Edit the formula using an expression]** e fai clic su **[!UICONTROL Next]** per visualizzare l’editor di espressioni.
1. Nell’elenco delle funzioni, fai doppio clic su **[!UICONTROL Day]**, accessibile tramite **[!UICONTROL Date]** nodo. Questa funzione restituisce il numero che rappresenta il giorno corrispondente alla data passata come parametro.

   ![](assets/s_ncs_user_create_exp_exple01.png)

1. Nell’elenco dei campi disponibili, fai doppio clic su **[!UICONTROL Birth date]**. Nella sezione superiore dell’editor viene quindi visualizzata la seguente formula:

   ```
   Day(@birthDate)
   ```

   Fai clic su **[!UICONTROL Finish]** per confermare.

1. Nell’editor delle query, nella prima cella del **[!UICONTROL Operator]** colonna, seleziona **[!UICONTROL equal to]**.

   ![](assets/s_ncs_user_create_exp_exple02.png)

1. Quindi, fai clic sulla prima cella della seconda colonna (**[!UICONTROL Value]**) e fai clic su **[!UICONTROL Edit expression]** per aprire l’editor di espressioni.
1. Nell’elenco delle funzioni, fai doppio clic su **[!UICONTROL Day]**, accessibile tramite **[!UICONTROL Date]** nodo.
1. Fai doppio clic sul pulsante **[!UICONTROL GetDate]** per recuperare la data corrente.

   ![](assets/s_ncs_user_create_exp_exple04.png)

   Nella sezione superiore dell’editor viene visualizzata la seguente formula:

   ```
   Day(GetDate())
   ```

   Fai clic su **[!UICONTROL Finish]** per confermare.

1. Ripetere questa procedura per recuperare il mese di nascita corrispondente al mese corrente. A questo scopo, fai clic sul pulsante **[!UICONTROL Add]** pulsante e ripetere i punti da 3 a 10, sostituendo **[!UICONTROL Day]** con **[!UICONTROL Month]**.

   La query completa è la seguente:

   ![](assets/s_ncs_user_create_exp_exple03.png)

Collega il risultato della **[!UICONTROL Query]** a un **[!UICONTROL Email delivery]** attività per inviare un’e-mail all’elenco di tutti i destinatari al loro compleanno.

## Includi destinatari nati il 29 febbraio (facoltativo) {#including-recipients-born-on-february-29th--optional-}

Se desideri includere tutti i destinatari nati il 29 febbraio, questo caso d’uso illustra come pianificare l’invio di un’e-mail ricorrente a un elenco di destinatari per il loro compleanno, che si tratti di un anno bisestile o meno.

I passaggi principali per l’implementazione di questo caso d’uso sono:

* Selezione dei destinatari
* Selezionare se si tratta di un anno bisestile
* Selezione dei destinatari nati il 29 febbraio

Per impostare questo caso d’uso, abbiamo creato il seguente flusso di lavoro di targeting:



Se l&#39;anno corrente **non è un anno bisestile** e il flusso di lavoro viene eseguito il 1° marzo, dobbiamo selezionare tutti i destinatari che avrebbero compiuto il compleanno ieri (29 febbraio) e aggiungerli all’elenco dei destinatari. In ogni altro caso non è necessaria alcuna azione aggiuntiva.

### Passaggio 1: Selezionare i destinatari {#step-1--selecting-the-recipients}

Dopo aver configurato la **[!UICONTROL Scheduler]** in modo che il flusso di lavoro inizi ogni giorno, identifica tutti i destinatari il cui anniversario è il giorno corrente.

>[!NOTE]
>
>Se l&#39;anno corrente è un anno bisestile, tutti i destinatari nati il 29 febbraio sono automaticamente inclusi.

![](assets/birthday-workflow_usecase_2.png)

La selezione dei destinatari il cui compleanno corrisponde alla data corrente viene presentata nel [Identificazione dei destinatari il cui compleanno è](#identifying-recipients-whose-birthday-it-is) sezione .

### Passaggio 2: Seleziona se si tratta di un anno bisestile o meno {#step-2--select-whether-or-not-it-is-a-leap-year}

La **[!UICONTROL Test]** L’attività ti consente di verificare se si tratta o meno di un anno bisestile e se la data corrente è il 1° marzo.

Se il test viene verificato (l&#39;anno non è un anno bisestile - non c&#39;è il 29 febbraio - e la data corrente è effettivamente il 1 marzo), la **[!UICONTROL True]** la transizione è abilitata e i destinatari nati il 29 febbraio verranno aggiunti alla consegna del 1° marzo. In caso contrario, la **[!UICONTROL False]** la transizione è abilitata e solo i destinatari nati nella data corrente riceveranno la consegna.

Copia e incolla il codice sottostante nel **[!UICONTROL Initialization script]** della sezione **[!UICONTROL Advanced]** scheda .

```
function isLeapYear(iYear)
{
    if(iYear/4 == Math.floor(iYear/4))
    {
        if(iYear/100 != Math.floor(iYear/100))
        {
            // Divisible by 4 only -> Leap Year
            return 1;
        }
        else
        {
            if(iYear/400 == Math.floor(iYear/400))
            {
                // Divisible by 4, 100 and 400 -> Leap year
                return 1;
            }
        }
    }
    // all others: no leap year
    return 0;
}

// Return today's date and time
var currentTime = new Date()
// returns the month (from 0 to 11)
var month = currentTime.getMonth() + 1
// returns the day of the month (from 1 to 31)
var day = currentTime.getDate()
// returns the year (four digits)
var year = currentTime.getFullYear()

// is current year a leap year?
vars.currentIsALeapYear = isLeapYear(year);

// is current date the first of march?
if(month == 3 && day == 1) {
  // today is 1st of march
vars.firstOfMarch = 1;
}
```

![](assets/birthday-workflow_usecase_3.png)

Aggiungi la seguente condizione nella **[!UICONTROL Conditional forks]** sezione:

```
vars.currentIsALeapYear == 0 && vars.firstOfMarch == 1
```

![](assets/birthday-workflow_usecase_4.png)

### Passaggio 3: Seleziona i destinatari nati il 29 febbraio {#step-3--select-any-recipients-born-on-february-29th}

Crea un **[!UICONTROL Fork]** e collega una delle transizioni in uscita a un **[!UICONTROL Query]** attività.

In questa query, seleziona tutti i destinatari la cui data di nascita è il 29 febbraio.

![](assets/birthday-workflow_usecase_5.png)

Combinare i risultati con un **[!UICONTROL Union]** attività.

Collega i risultati dei due **[!UICONTROL Test]** rami di attività in un **[!UICONTROL Email delivery]** attività per inviare un’e-mail all’elenco di tutti i destinatari al loro compleanno, anche a quelli nati il 29 febbraio durante un anno non bisestile.

## Creare una consegna ricorrente {#creating-a-recurring-delivery-in-a-targeting-workflow}

Aggiungi un **Consegna ricorrente** in base al modello e-mail di compleanno che desideri inviare.

>[!CAUTION]
>
>Affinché i flussi di lavoro possano essere eseguiti, è necessario avviare i flussi di lavoro tecnici relativi al pacchetto Campaign. Per ulteriori informazioni, consulta la sezione [Elenco dei flussi di lavoro tecnici](technical-workflows.md) sezione .
>
>Se per la campagna sono abilitati i passaggi di approvazione, le consegne vengono inviate solo dopo la conferma di questi passaggi. Per ulteriori informazioni, consulta la sezione .

![](assets/birthday-workflow_usecase_1.png)
