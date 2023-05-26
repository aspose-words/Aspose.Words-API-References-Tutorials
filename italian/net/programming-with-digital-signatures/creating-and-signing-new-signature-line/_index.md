---
title: Creazione e firma di una nuova linea di firma
linktitle: Creazione e firma di una nuova linea di firma
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare e firmare una nuova riga della firma in un documento Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzionalità di creazione e firma di una nuova riga della firma con Aspose.Words per .NET. Questa funzione consente di inserire una riga della firma in un documento Word, impostare opzioni personalizzate e firmare il documento. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e del generatore

Inizia creando un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: Inserimento della riga della firma

Utilizzare il metodo InsertSignatureLine() dell'oggetto DocumentBuilder per inserire una nuova riga della firma nel documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Passaggio 3: salvare il documento

Salva il documento modificato:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento.

## Passaggio 4: Firma del documento

Per firmare il documento, è necessario impostare le opzioni di firma e utilizzare la classe DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
	SignatureLineId = signatureLine.Id,
	SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
	dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);
```

Assicurati di specificare i percorsi corretti per il documento, l'immagine della riga della firma e il documento firmato.

### Codice sorgente di esempio per la creazione e la firma di una nuova riga della firma utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per creare e firmare una nuova riga della firma con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
	
	doc.Save(dataDir + "SignDocuments.SignatureLine.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLine.docx",
		dataDir + "SignDocuments.NewSignatureLine.docx", certHolder, signOptions);

```

Seguendo questi passaggi, sarai in grado di creare e firmare facilmente una nuova riga della firma nel tuo documento Word con Aspose.Words per .NET.

