---
title: Firma della riga della firma esistente
linktitle: Firma della riga della firma esistente
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come firmare una riga della firma esistente in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/signing-existing-signature-line/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di firma di una riga di firma esistente con Aspose.Words per .NET. Questa funzionalità consente di firmare digitalmente una riga di firma già presente in un documento Word. Segui i passaggi seguenti:

## Passaggio 1: caricamento del documento e accesso alla riga della firma

Inizia caricando il documento contenente la riga della firma esistente:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Passaggio 2: impostazione delle opzioni di firma

Crea un'istanza della classe SignOptions e imposta le opzioni della firma, inclusi l'ID della riga della firma e l'immagine della riga della firma:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Assicurati di specificare il percorso corretto per l'immagine della riga della firma.

## Passaggio 3: caricamento del certificato

Inizia caricando il certificato di firma utilizzando la classe CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Assicurati di specificare il percorso corretto per il certificato e la password associata.

## Passaggio 4: firma della riga della firma esistente

Utilizzare la classe DigitalSignatureUtil per firmare la riga della firma esistente:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Assicurati di specificare i percorsi corretti per il documento di origine, il documento firmato e il certificato.

### Codice sorgente di esempio per la firma della riga della firma esistente utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per firmare una linea di firma esistente con Aspose.Words per .NET:


```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");
	
	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
	

```

Seguendo questi passaggi, puoi facilmente firmare una riga della firma esistente in un documento Word con Aspose.Words per .NET.

