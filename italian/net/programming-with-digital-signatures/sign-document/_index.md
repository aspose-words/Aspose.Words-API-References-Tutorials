---
title: Firma documento
linktitle: Firma documento
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come firmare digitalmente un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/sign-document/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di firma del documento con Aspose.Words per .NET. Questa funzione consente di firmare digitalmente un documento Word utilizzando un certificato. Segui i passaggi seguenti:

## Passaggio 1: caricamento del certificato

Inizia caricando il certificato di firma utilizzando la classe CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assicurati di specificare il percorso corretto per il certificato e la password associata.

## Passaggio 2: Firma del documento

Utilizzare la classe DigitalSignatureUtil per firmare il documento:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Assicurati di specificare i percorsi corretti per il documento di origine e il documento firmato.

### Codice sorgente di esempio per il documento di firma utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per firmare un documento con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Seguendo questi passaggi, puoi facilmente firmare un documento Word con Aspose.Words per .NET.



