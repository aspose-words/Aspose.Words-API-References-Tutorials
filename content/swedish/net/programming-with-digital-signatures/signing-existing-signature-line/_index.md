---
title: Signering av befintlig signaturrad i Word-dokument
linktitle: Signering av befintlig signaturrad i Word-dokument
second_title: Aspose.Words Document Processing API
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

## Slutsats

den här handledningen lärde vi oss hur man signerar en befintlig signaturrad i ett Word-dokument med Aspose.Words för .NET. Genom att följa de medföljande stegen kan du enkelt ladda dokumentet, komma åt den befintliga signaturraden, ställa in signeringsalternativ och signera dokumentet. Möjligheten att signera en befintlig signaturrad ger ett bekvämt sätt att lägga till digitala signaturer till fördefinierade områden i dina Word-dokument, vilket säkerställer dokumentintegritet och autentisering. Aspose.Words för .NET erbjuder ett kraftfullt API för ordbehandling med digitala signaturer, vilket gör att du kan anpassa signeringsprocessen och förbättra säkerheten för dina Word-dokument.

### FAQ's

#### F: Vad är en befintlig signaturrad i ett Word-dokument?

S: En befintlig signaturrad i ett Word-dokument är ett fördefinierat område där en signatur kan placeras. Det representeras vanligtvis av en form eller ett objekt i dokumentet och fungerar som ett avsett utrymme för undertecknaren att lägga till sin digitala signatur.

#### F: Hur kan jag signera en befintlig signaturrad i ett Word-dokument med Aspose.Words för .NET?

S: För att signera en befintlig signaturrad i ett Word-dokument med Aspose.Words för .NET, kan du följa dessa steg:
1.  Ladda dokumentet med hjälp av`Document` klass och ange sökvägen till dokumentfilen.
2.  Få åtkomst till den befintliga signaturraden med lämplig metod eller egenskap. Du kan till exempel använda`GetChild` metod för att hämta signaturlinjeformen.
3.  Skapa en instans av`SignOptions` klass och ställ in`SignatureLineId` egenskap till ID för den befintliga signaturraden.
4.  Ställ in`SignatureLineImage` egendom av`SignOptions` klass till bilden som representerar den digitala signaturen.
5.  Ladda signeringscertifikatet med hjälp av`CertificateHolder` klass och ange det nödvändiga certifikatet och lösenordet.
6.  Använd`DigitalSignatureUtil.Sign` metod för att signera dokumentet, tillhandahålla nödvändiga parametrar inklusive`SignOptions` objekt.

#### F: Hur kommer jag åt den befintliga signaturraden i ett Word-dokument med Aspose.Words för .NET?

 S: För att komma åt den befintliga signaturraden i ett Word-dokument med Aspose.Words för .NET kan du använda lämplig metod eller egenskap för att hämta signaturlinjeformen från dokumentets struktur. Du kan till exempel använda`GetChild` metod med lämpliga parametrar för att få den önskade signaturlinjeformen.

#### F: Kan jag anpassa utseendet på den digitala signaturen i en befintlig signaturrad?

S: Ja, du kan anpassa utseendet på den digitala signaturen i en befintlig signaturrad genom att tillhandahålla en bildfil som representerar signaturen. Bilden kan vara en logotyp, handskriven signatur eller någon annan grafisk representation av signaturen. Du kan ställa in`SignatureLineImage` egendom av`SignOptions` klass till bildfilens byte.

#### F: Kan jag signera flera befintliga signaturrader i ett Word-dokument?
 S: Ja, du kan signera flera befintliga signaturrader i ett Word-dokument. Du måste följa stegen för varje signaturrad individuellt och ställa in lämplig`SignatureLineId` och`SignatureLineImage` värden i`SignOptions` objekt för varje signaturrad.

#### F: Vilket format ska bildfilen vara för den digitala signaturen i en befintlig signaturrad?

 S: Bildfilen för den digitala signaturen i en befintlig signaturrad kan vara i olika format, som PNG, JPEG, BMP eller GIF. Du kan ange filsökvägen eller läsa byte för bildfilen och tilldela den till`SignatureLineImage` egendom av`SignOptions` klass.
