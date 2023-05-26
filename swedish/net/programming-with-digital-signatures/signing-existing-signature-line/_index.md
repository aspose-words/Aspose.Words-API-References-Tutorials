---
title: Signering av befintlig signaturlinje
linktitle: Signering av befintlig signaturlinje
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du signerar en befintlig signaturrad i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/signing-existing-signature-line/
---

I den här handledningen går vi igenom stegen för att använda signaturfunktionen för en befintlig signaturlinje med Aspose.Words för .NET. Med den här funktionen kan du digitalt signera en signaturrad som redan finns i ett Word-dokument. Följ stegen nedan:

## Steg 1: Ladda dokumentet och komma åt signaturraden

Börja med att ladda upp dokumentet som innehåller den befintliga signaturraden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Steg 2: Ställ in signaturalternativ

Skapa en instans av klassen SignOptions och ställ in signaturalternativen, inklusive signaturrads-ID och signaturradsbild:

```csharp
SignOptions signOptions = new SignOptions
{
SignatureLineId = signatureLine.Id,
SignatureLineImage = File.ReadAllBytes(ImagesDir + "Enhanced Windows MetaFile.emf")
};
```

Var noga med att ange rätt sökväg till signaturlinjebilden.

## Steg 3: Laddar certifikatet

Börja med att ladda signeringscertifikatet med klassen CertificateHolder:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Var noga med att ange rätt sökväg till ditt certifikat och tillhörande lösenord.

## Steg 4: Signering av den befintliga signaturraden

Använd klassen DigitalSignatureUtil för att signera den befintliga signaturraden:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SigningExistingSignatureLine.docx", certHolder, signOptions);
```

Var noga med att ange rätt sökvägar för källdokumentet, det signerade dokumentet och certifikatet.

### Exempel på källkod för signering av befintlig signaturlinje med Aspose.Words för .NET

Här är den fullständiga källkoden för att signera en befintlig signaturrad med Aspose.Words för .NET:


```csharp

	// Sökvägen till dokumentkatalogen.
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

Genom att följa dessa steg kan du enkelt signera en befintlig signaturrad i ett Word-dokument med Aspose.Words för .NET.

