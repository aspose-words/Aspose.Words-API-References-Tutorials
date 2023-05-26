---
title: Crea una nuova riga della firma e imposta l'ID del fornitore
linktitle: Crea una nuova riga della firma e imposta l'ID del fornitore
second_title: Riferimento all'API Aspose.Words per .NET
description: Scopri come creare una nuova riga della firma e impostare l'ID del provider in un documento di Word con Aspose.Words per .NET.
type: docs
weight: 10
url: /it/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

In questo tutorial, ti guideremo attraverso i passaggi per utilizzare la funzione Crea nuova riga della firma e Imposta ID provider con Aspose.Words per .NET. Questa funzione consente di inserire una riga della firma in un documento Word, impostare opzioni personalizzate e firmare il documento. Segui i passaggi seguenti:

## Passaggio 1: creazione del documento e del generatore

Inizia creando un'istanza della classe Document e un oggetto DocumentBuilder:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Passaggio 2: impostazione delle opzioni della riga della firma

Crea un'istanza della classe SignatureLineOptions e imposta le opzioni desiderate:

```csharp
SignatureLineOptions signatureLineOptions = new SignatureLineOptions
{
Sign = "vderyushev",
SignerTitle = "QA",
Email = "vderyushev@aspose.com",
ShowDate=true,
Default Instructions = false,
Instructions = "Please sign here.",
AllowComments = true
};
```

## Passaggio 3: Inserimento della riga della firma

Utilizzare il metodo InsertSignatureLine() dell'oggetto DocumentBuilder per inserire la riga della firma nel documento:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Passaggio 4: impostare l'ID del fornitore

Imposta l'ID del provider per la riga della firma utilizzando la proprietà ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Assicurati di specificare l'ID provider corretto per il tuo caso d'uso.

## Passaggio 5: salvare il documento

Salva il documento modificato:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Assicurati di specificare il percorso e il nome file corretti per salvare il documento.

## Passaggio 6: Firma del documento

Per firmare il documento, è necessario impostare le opzioni di firma e utilizzare la classe DigitalSignatureUtil:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
ProviderId = signatureLine.ProviderId,
Comments = "Document was signed by vderyushev",
SignTime = DateTime.Now
};

CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
	dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions)
```

Assicurati di specificare i percorsi corretti per il documento, il certificato e il documento firmato.

### Codice sorgente di esempio per creare una nuova riga della firma e impostare l'ID del provider utilizzando Aspose.Words per .NET

Ecco il codice sorgente completo per creare una nuova riga della firma e impostare l'ID del provider con Aspose.Words per .NET:

```csharp

	// Il percorso della directory dei documenti.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	SignatureLineOptions signatureLineOptions = new SignatureLineOptions
	{
		Signer = "vderyushev",
		SignerTitle = "QA",
		Email = "vderyushev@aspose.com",
		ShowDate = true,
		DefaultInstructions = false,
		Instructions = "Please sign here.",
		AllowComments = true
	};

	SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
	signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
	
	doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");

	SignOptions signOptions = new SignOptions
	{
		SignatureLineId = signatureLine.Id,
		ProviderId = signatureLine.ProviderId,
		Comments = "Document was signed by vderyushev",
		SignTime = DateTime.Now
	};

	CertificateHolder certHolder = CertificateHolder.Create(MyDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "SignDocuments.SignatureLineProviderId.docx", 
		dataDir + "SignDocuments.CreateNewSignatureLineAndSetProviderId.docx", certHolder, signOptions);

```

Seguendo questi passaggi, puoi facilmente creare una nuova riga della firma e impostare l'ID del provider nel tuo documento Word con Aspose.Words per .NET.

