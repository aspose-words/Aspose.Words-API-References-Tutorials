---
title: Skapa och signera ny signaturlinje
linktitle: Skapa och signera ny signaturlinje
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar och signerar en ny signaturrad i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---

den här handledningen går vi igenom stegen för att använda funktionen skapa och signera en ny signaturlinje med Aspose.Words för .NET. Med den här funktionen kan du infoga en signaturrad i ett Word-dokument, ställa in anpassade alternativ och signera dokumentet. Följ stegen nedan:

## Steg 1: Skapa dokumentet och generatorn

Börja med att skapa en instans av klassen Document och ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga signaturraden

Använd metoden InsertSignatureLine() för DocumentBuilder-objektet för att infoga en ny signaturrad i dokumentet:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(new SignatureLineOptions()).SignatureLine;
```

## Steg 3: Spara dokumentet

Spara det ändrade dokumentet:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLine.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara dokumentet.

## Steg 4: Signera dokumentet

För att signera dokumentet måste du ställa in signaturalternativen och använda klassen DigitalSignatureUtil:

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

Var noga med att ange rätt sökvägar för dokumentet, signaturradsbilden och det signerade dokumentet.

### Exempel på källkod för att skapa och signera ny signaturrad med Aspose.Words för .NET

Här är den fullständiga källkoden för att skapa och signera en ny signaturrad med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
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

Genom att följa dessa steg kommer du enkelt att kunna skapa och signera en ny signaturrad i ditt Word-dokument med Aspose.Words för .NET.

