---
title: Ange ID för signaturleverantör
linktitle: Ange ID för signaturleverantör
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in signaturleverantörens ID i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/set-signature-provider-id/
---

I den här handledningen går vi igenom stegen för att använda funktionen Set Signature Provider ID med Aspose.Words för .NET. Med den här funktionen kan du ange signaturleverantörens ID för en signaturrad i ett Word-dokument. Följ stegen nedan:

## Steg 1: Ladda dokumentet och komma åt signaturraden

Börja med att ladda upp dokumentet som innehåller signaturraden:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Signature line.docx");

SignatureLine signatureLine = ((Shape)doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;
```

## Steg 2: Ställ in signaturalternativ

Skapa en instans av SignOptions-klassen och ställ in signeringsalternativen, inklusive leverantörs-ID:

```csharp
SignOptions signOptions = new SignOptions
{
ProviderId = signatureLine.ProviderId,
 SignatureLineId = signatureLine.Id
};
```

## Steg 3: Signera dokumentet

För att signera dokumentet måste du använda klassen DigitalSignatureUtil och ange signeringscertifikatet:

```csharp
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
	dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);
```

Se till att ange rätt sökvägar för dokumentet, certifikatet och det signerade dokumentet.

### Exempel på källkod för Set Signature Provider Id med Aspose.Words för .NET

Här är den fullständiga källkoden för att ställa in signaturleverantörens ID med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Signature line.docx");

	SignatureLine signatureLine =
		((Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true)).SignatureLine;

	SignOptions signOptions = new SignOptions
	{
		ProviderId = signatureLine.ProviderId, SignatureLineId = signatureLine.Id
	};

	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");

	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx",
		dataDir + "SignDocuments.SetSignatureProviderId.docx", certHolder, signOptions);

```

Slutför ID för signaturleverantör i ditt Word-dokument med Aspose.Words för .NET.

