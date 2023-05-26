---
title: Firma del documento crittografato
linktitle: Firma del documento crittografato
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come firmare digitalmente un documento crittografato con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/signing-encrypted-document/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di firma di un documento crittografato con Aspose.Words per .NET. Questa funzione consente di firmare digitalmente un documento Word crittografato utilizzando una password di decrittografia. Segui i passaggi seguenti:

## Passaggio 1: impostazione delle opzioni di firma

Crea un'istanza della classe SignOptions e imposta la password di decrittografia:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionpassword" };
```

Assicurati di specificare la password di decrittografia corretta per il tuo documento crittografato.

## Passaggio 2: caricamento del certificato

Inizia caricando il certificato di firma utilizzando la classe CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assicurati di specificare il percorso corretto per il certificato e la password associata.

## Passaggio 3: Firma del documento crittografato

Utilizzare la classe DigitalSignatureUtil per firmare il documento crittografato:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
	certHolder, signOptions);
```

Assicurati di specificare i percorsi corretti per il documento crittografato, il documento firmato e il certificato.

### Esempio di codice sorgente per la firma di un documento crittografato utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per firmare un documento crittografato con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	SignOptions signOptions = new SignOptions { DecryptionPassword = "decryptionPassword" };

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.EncryptedDocument.docx",
		certHolder, signOptions);
	

```
Seguendo questi passaggi, puoi facilmente firmare un documento Word crittografato con Aspose.Words per .NET.

