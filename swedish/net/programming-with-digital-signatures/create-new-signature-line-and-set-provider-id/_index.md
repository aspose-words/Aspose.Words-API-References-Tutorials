---
title: Skapa ny signaturlinje och ställ in leverantörs-ID
linktitle: Skapa ny signaturlinje och ställ in leverantörs-ID
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar en ny signaturrad och ställer in leverantörs-ID i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---

I den här handledningen går vi igenom stegen för att använda funktionen Skapa ny signaturlinje och ange leverantörs-ID med Aspose.Words för .NET. Med den här funktionen kan du infoga en signaturrad i ett Word-dokument, ställa in anpassade alternativ och signera dokumentet. Följ stegen nedan:

## Steg 1: Skapa dokumentet och generatorn

Börja med att skapa en instans av klassen Document och ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Ställa in signaturlinjealternativ

Skapa en instans av klassen SignatureLineOptions och ställ in önskade alternativ:

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

## Steg 3: Infoga signaturraden

Använd metoden InsertSignatureLine() för DocumentBuilder-objektet för att infoga signaturraden i dokumentet:

```csharp
SignatureLine signatureLine = builder.InsertSignatureLine(signatureLineOptions).SignatureLine;
```

## Steg 4: Ange leverantörs-ID

Ställ in leverantörs-ID för signaturraden med egenskapen ProviderId:

```csharp
signatureLine.ProviderId = Guid.Parse("CF5A7BB4-8F3C-4756-9DF6-BEF7F13259A2");
```

Var noga med att ange rätt leverantörs-ID för ditt användningsfall.

## Steg 5: Spara dokumentet

Spara det ändrade dokumentet:

```csharp
doc.Save(dataDir + "SignDocuments.SignatureLineProviderId.docx");
```

Var noga med att ange rätt sökväg och filnamn för att spara dokumentet.

## Steg 6: Signera dokumentet

För att signera dokumentet måste du ställa in signaturalternativen och använda klassen DigitalSignatureUtil:

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

Se till att ange rätt sökvägar för dokumentet, certifikatet och det signerade dokumentet.

### Exempel på källkod för Skapa ny signaturlinje och ange leverantörs-ID med Aspose.Words för .NET

Här är den fullständiga källkoden för att skapa en ny signaturrad och ställa in leverantörs-ID med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
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

Genom att följa dessa steg kan du enkelt skapa en ny signaturrad och ange leverantörs-ID i ditt Word-dokument med Aspose.Words för .NET.

