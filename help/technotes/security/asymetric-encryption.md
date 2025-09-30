---
product: campaign
title: 'Nota tecnica: crittografia e decrittografia asimmetriche in Adobe Campaign'
description: 'Nota tecnica: crittografia e decrittografia asimmetriche in Adobe Campaign'
hide: true
hidefromtoc: true
source-git-commit: 1d9d4111cde1e230220a04c8fd10a126116339ad
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# Nota tecnica: Crittografia asimmetrica e decrittografia in Adobe Campaign {#asymetric-encryption}

La crittografia a chiave pubblica, o crittografia asimmetrica, è il campo dei sistemi di crittografia che utilizzano coppie di chiavi correlate. Ogni coppia di chiavi è costituita da una **chiave pubblica** e da una **chiave privata** corrispondente.

* La **chiave pubblica** è condivisa e utilizzata per crittografare i dati.

* La **chiave privata** è tenuta segreta e utilizzata per decrittografare i dati.

Questo approccio garantisce che, anche se un utente dispone della chiave pubblica, non possa decrittografare il messaggio senza la chiave privata. Fornisce funzioni di sicurezza chiave come riservatezza, autenticazione e integrità.

A partire dalla versione 8.8.3 di Adobe Campaign, sono state aggiunte due nuove funzioni JavaScript per la crittografia e la decrittografia:

* Crittografia tramite chiave pubblica: `rsaPublicEncrypt(data, base64EncodedPublicKey, useOAEPpadding)`

* Decrittografia tramite chiave privata: `rsaPrivateDecrypt(encryptedData, base64EncodedPrivateKey, useOAEPpadding)`


Esempio:

```Java
// Encryption with PKCS#1 v1.5 padding (default)
var encrypted = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t..." // Base64 encoded public key
);
 
// Encryption with OAEP padding
var encryptedOAEP = rsaPublicEncrypt(
    "Secret message",
    "LS0tLS1CRUdJTiBQVUJMSUMgS0VZLS0t...", // Base64 encoded public key
    true
);
 
// Decryption
var decrypted = rsaPrivateDecrypt(
    encrypted,
    "LS0tLS1CRUdJTiBSU0EgUFJJVkFURSBLRVkt..." // Base64 encoded private key
);
```

**Risorse aggiuntive**

* [Introduzione alle [!DNL Campaign] API](https://experienceleague.adobe.com/it/docs/campaign/campaign-v8/developer/api){target="_blank"}
* [Documentazione JSAPI per Campaign](https://experienceleague.adobe.com/developer/campaign-api/api/p-1.html?lang=it){target="_blank"}
