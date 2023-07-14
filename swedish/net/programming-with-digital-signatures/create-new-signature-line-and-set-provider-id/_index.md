---
title: Skapa ny signaturlinje och ställ in leverantörs-ID
linktitle: Skapa ny signaturlinje och ställ in leverantörs-ID
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar en ny signaturrad och ställer in leverantörs-ID i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/create-new-signature-line-and-set-provider-id/
---
den här handledningen går vi igenom stegen för att använda funktionen Skapa ny signaturlinje och ange leverantörs-ID med Aspose.Words för .NET. Med den här funktionen kan du infoga en signaturrad i ett Word-dokument, ställa in anpassade alternativ och signera dokumentet. Följ stegen nedan:

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

## Slutsats

den här handledningen utforskade vi funktionen att skapa en ny signaturrad och ställa in leverantörs-ID i ett Word-dokument med Aspose.Words för .NET. Genom att följa de angivna stegen kan du enkelt infoga en signaturrad med anpassade alternativ och associera den med en specifik leverantör med hjälp av leverantörs-ID. Att lägga till signaturrader och anpassa leverantörsinformationen förbättrar äktheten och pålitligheten hos dina dokument. Aspose.Words för .NET tillhandahåller ett kraftfullt API för ordbehandling med signaturrader och digitala certifikat i Word-dokument, vilket gör att du kan automatisera signeringsprocessen och säkerställa att dina dokument är giltiga.

### FAQ's

#### F: Vad är ett leverantörs-ID i en signaturrad?

S: Ett leverantörs-ID i en signaturrad är en unik identifierare som representerar leverantören av den digitala signaturen. Det hjälper till att identifiera källan eller organisationen som är ansvarig för signaturen.

#### F: Hur kan jag skapa en ny signaturrad i ett Word-dokument med Aspose.Words för .NET?

S: För att skapa en ny signaturrad i ett Word-dokument med Aspose.Words för .NET, kan du följa dessa steg:
1.  Skapa en instans av`Document` klass och a`DocumentBuilder` objekt.
2.  Skapa en instans av`SignatureLineOptions` klass och ställ in önskade signaturradsalternativ.
3.  Använd`InsertSignatureLine` metod för`DocumentBuilder` objekt för att infoga signaturraden i dokumentet.

#### F: Kan jag anpassa alternativen för signaturraden, såsom undertecknarens namn, titel och instruktioner?

 S: Ja, du kan anpassa alternativen för signaturraden. De`SignatureLineOptions` klass tillhandahåller egenskaper för att ställa in önskade alternativ, som t.ex`Signer`, `SignerTitle`, `Instructions`, `AllowComments`, etc. Du kan ändra dessa egenskaper innan du infogar signaturraden.

#### F: Vad är syftet med att ställa in leverantörs-ID för en signaturlinje?

S: Att ställa in leverantörs-ID för en signaturlinje hjälper till att identifiera källan eller organisationen som är ansvarig för den digitala signaturen. Det låter dig associera signaturen med en specifik leverantör eller enhet, vilket ger ytterligare information om signaturens ursprung och tillförlitlighet.

#### F: Hur kan jag ställa in leverantörs-ID för en signaturrad med Aspose.Words för .NET?

S: För att ställa in leverantörs-ID för en signaturrad med Aspose.Words för .NET kan du följa dessa steg:
1.  När du har infogat signaturraden, gå till`ProviderId`egendom av`SignatureLine` objekt.
2.  Ställ in`ProviderId` egendom till det önskade leverantörs-ID-värdet med hjälp av`Guid` data typ.

#### F: Kan jag signera dokumentet efter att ha skapat en ny signaturrad och angett leverantörs-ID?

 S: Ja, efter att ha skapat en ny signaturrad och angett leverantörs-ID kan du signera dokumentet. För att signera dokumentet måste du ställa in signaturalternativ, inklusive signaturrads-ID, leverantörs-ID, kommentarer och signeringstid. Använd sedan`DigitalSignatureUtil.Sign` metod för att signera dokumentet med ett digitalt certifikat.

#### F: Kan jag ange ett specifikt leverantörs-ID för varje signaturrad i ett Word-dokument?

S: Ja, du kan ange ett specifikt leverantörs-ID för varje signaturrad i ett Word-dokument. Efter att ha infogat varje signaturrad kan du ställa in leverantörs-ID för just den signaturraden genom att gå till`ProviderId` respektive egendom`SignatureLine` objekt.

#### F: Hur kan jag spara det ändrade dokumentet efter att ha skapat en ny signaturrad och angett leverantörs-ID?

 S: För att spara det ändrade dokumentet efter att ha skapat en ny signaturrad och angett leverantörs-ID, kan du använda`Save` metod för`Document` objekt. Ange rätt sökväg och filnamn för att spara dokumentet.

#### F: Vilket filformat stöder Aspose.Words for .NET för att skapa och signera signaturrader?

S: Aspose.Words för .NET stöder att skapa och signera signaturrader i DOCX-filformatet. Du kan skapa och signera signaturrader i DOCX-filer med hjälp av de medföljande metoderna och klasserna.

#### F: Kan jag ändra leverantörs-ID eller andra alternativ för en signaturrad efter att den har signerats?

S: När en signaturrad har signerats blir den en del av dokumentets innehåll och kan inte ändras separat. Eventuella ändringar av signaturraden, som att ändra leverantörs-ID eller andra alternativ, skulle kräva att man tar bort den befintliga signaturen och skapar en ny signaturrad.