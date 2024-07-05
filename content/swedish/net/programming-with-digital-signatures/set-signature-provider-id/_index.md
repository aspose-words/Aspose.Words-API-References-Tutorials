---
title: Ställ in signaturleverantörs-ID i Word-dokument
linktitle: Ställ in signaturleverantörs-ID i Word-dokument
second_title: Aspose.Words Document Processing API
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


## Slutsats

den här handledningen lärde vi oss hur man ställer in signaturleverantörens ID för en signaturrad i ett Word-dokument med Aspose.Words för .NET. Genom att följa de medföljande stegen kan du enkelt ladda dokumentet, komma åt signaturraden, ange leverantörs-ID och signera dokumentet. Möjligheten att ställa in signaturleverantörens ID hjälper till att fastställa undertecknarens identitet och pålitlighet, vilket förbättrar säkerheten och integriteten för dina Word-dokument. Aspose.Words för .NET tillhandahåller ett robust API för ordbehandling med digitala signaturer, så att du enkelt kan anpassa och hantera signaturprocessen.

### Vanliga frågor för att ställa in signaturleverantörs-id i word-dokument

#### F: Vad är ett signaturleverantörs-ID i ett Word-dokument?

S: Ett signaturleverantörs-ID i ett Word-dokument är en unik identifierare som anger leverantören av en digital signatur. Det hjälper till att identifiera den enhet eller organisation som ansvarar för att skapa och hantera den digitala signaturen.

#### F: Hur kan jag ställa in signaturleverantörens ID för en signaturrad i ett Word-dokument med Aspose.Words för .NET?

S: För att ställa in signaturleverantörens ID för en signaturrad i ett Word-dokument med Aspose.Words för .NET kan du följa dessa steg:
1.  Ladda dokumentet med hjälp av`Document` klass och ange sökvägen till dokumentfilen.
2.  Gå till signaturraden med lämplig metod eller egenskap. Du kan till exempel använda`GetChild` metod för att hämta signaturlinjeformen.
3. Hämta leverantörs-ID från signaturraden.
4.  Skapa en instans av`SignOptions` klass och ställ in`ProviderId` egendom till det hämtade leverantörs-ID.
5.  Använd`DigitalSignatureUtil.Sign` metod för att signera dokumentet, tillhandahålla nödvändiga parametrar inklusive`SignOptions` objekt.

#### F: Hur kommer jag åt signaturraden i ett Word-dokument med Aspose.Words för .NET?

 S: För att komma åt signaturraden i ett Word-dokument med Aspose.Words för .NET kan du använda lämplig metod eller egenskap för att hämta signaturlinjeformen från dokumentets struktur. Du kan till exempel använda`GetChild` metod med lämpliga parametrar för att få den önskade signaturlinjeformen.

#### F: Kan jag ställa in signaturleverantörens ID för flera signaturrader i ett Word-dokument?

 S: Ja, du kan ställa in signaturleverantörens ID för flera signaturrader i ett Word-dokument. Du kan iterera genom samlingen av signaturrader i dokumentet och ställa in leverantörs-ID för varje signaturrad individuellt med hjälp av`SignOptions.ProviderId` fast egendom.

#### F: Vad är syftet med signaturleverantörens ID i ett Word-dokument?

S: Signaturleverantörens ID i ett Word-dokument tjänar till att identifiera den enhet eller organisation som ansvarar för att skapa och hantera den digitala signaturen. Det hjälper till att fastställa äktheten och trovärdigheten för den digitala signaturen genom att associera den med en specifik leverantör.

#### F: Vilken typ av digitala certifikat kan användas för att ställa in signaturleverantörens ID i ett Word-dokument?

S: Du kan använda X.509 digitala certifikat med lämplig leverantörsinformation för att ställa in signaturleverantörens ID i ett Word-dokument. Det digitala certifikatet bör utfärdas av en betrodd certifikatutfärdare (CA) och innehålla nödvändig metadata för att identifiera leverantören.