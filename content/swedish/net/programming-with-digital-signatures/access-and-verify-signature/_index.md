---
title: Få åtkomst till och verifiera signatur i Word-dokument
linktitle: Få åtkomst till och verifiera signatur i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du får åtkomst till och verifierar digitala signaturer i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/access-and-verify-signature/
---
I den här handledningen guidar vi dig genom stegen för att använda åtkomst- och signaturverifieringsfunktionen i Aspose.Words för .NET. Den här funktionen låter dig komma åt digitala signaturer i ett Word-dokument och verifiera deras giltighet. Följ stegen nedan:

## Steg 1: Ladda dokumentet och komma åt signaturer

Börja med att ladda upp dokumentet som innehåller digitala signaturer:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Digitally signed.docx");
```

## Steg 2: Bläddra bland digitala signaturer

Använd en loop för att gå igenom alla digitala signaturer i dokumentet:

```csharp
foreach (DigitalSignature signature in doc.DigitalSignatures)
{
	// Få åtkomst till signaturinformation
	Console.WriteLine("* Signature Found *");
	Console.WriteLine("Is valid: " + signature.IsValid);
	// Den här egenskapen är endast tillgänglig i MS Word-dokument.
	Console.WriteLine("Reason for signing: " + signature.Comments); 
	Console.WriteLine("Time of signing: " + signature.SignTime);
	Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
	Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
	Console.WriteLine();
}
```

Se till att anpassa displaymeddelandena efter dina behov.

### Exempel på källkod för Access And Verify Signature med Aspose.Words för .NET

Här är den fullständiga källkoden för åtkomst och signaturverifiering med Aspose.Words för .NET:

```csharp
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Digitally signed.docx");

	foreach (DigitalSignature signature in doc.DigitalSignatures)
	{
		Console.WriteLine("* Signature Found *");
		Console.WriteLine("Is valid: " + signature.IsValid);
		// Den här egenskapen är endast tillgänglig i MS Word-dokument.
		Console.WriteLine("Reason for signing: " + signature.Comments); 
		Console.WriteLine("Time of signing: " + signature.SignTime);
		Console.WriteLine("Subject name: " + signature.CertificateHolder.Certificate.SubjectName.Name);
		Console.WriteLine("Issuer name: " + signature.CertificateHolder.Certificate.IssuerName.Name);
		Console.WriteLine();
	}

```

Genom att följa dessa steg kommer du enkelt att kunna komma åt och verifiera de digitala signaturerna i ditt Word-dokument med Aspose.Words för .NET.

## Slutsats

I den här självstudien utforskade vi funktionen att komma åt och verifiera digitala signaturer i ett Word-dokument med Aspose.Words för .NET. Genom att följa de angivna stegen kan du enkelt ladda ett dokument, komma åt dess digitala signaturer och verifiera deras giltighet. Möjligheten att komma åt och verifiera digitala signaturer ger ett sätt att säkerställa integriteten och äktheten hos dina Word-dokument. Aspose.Words för .NET erbjuder ett kraftfullt API för ordbehandling med digitala signaturer, vilket gör att du kan automatisera verifieringsprocessen och förbättra säkerheten för dina dokument.

### FAQ's

#### F: Vad är digitala signaturer i ett Word-dokument?

S: Digitala signaturer i ett Word-dokument är elektroniska signaturer som ger ett sätt att autentisera dokumentets integritet och ursprung. De skapas med hjälp av digitala certifikat och kryptografiska algoritmer, vilket gör att mottagarna kan verifiera att dokumentet inte har ändrats och att det kommer från en pålitlig källa.

#### F: Hur kan jag komma åt digitala signaturer i ett Word-dokument med Aspose.Words för .NET?

S: För att komma åt digitala signaturer i ett Word-dokument med Aspose.Words för .NET kan du följa dessa steg:
1.  Ladda dokumentet med hjälp av`Document` klass och ange sökvägen till dokumentfilen.
2.  Använd en slinga för att iterera genom`DigitalSignatures` insamling av dokumenten. Varje iteration representerar en digital signatur.

#### F: Vilken information kan jag komma åt från en digital signatur i ett Word-dokument?

S: Från en digital signatur i ett Word-dokument kan du komma åt olika information, till exempel:
- Giltighet: Kontrollera om signaturen är giltig.
- Kommentarer: Få orsaken till undertecknandet som anges av undertecknaren.
- Signera tid: Få tidpunkten när dokumentet undertecknades.
- Ämnesnamn: Hämta namnet på undertecknaren eller certifikatsubjektet.
- Utfärdarens namn: Hämta namnet på certifikatutfärdaren.

#### F: Kan jag verifiera giltigheten av en digital signatur i ett Word-dokument med Aspose.Words för .NET?

 S: Ja, du kan verifiera giltigheten av en digital signatur i ett Word-dokument med Aspose.Words för .NET. Genom att komma åt`IsValid` egendom av`DigitalSignature` objekt kan du avgöra om signaturen är giltig eller inte.

#### F: Hur kan jag verifiera giltigheten av digitala signaturer i ett Word-dokument med Aspose.Words för .NET?

S: För att verifiera giltigheten av digitala signaturer i ett Word-dokument med Aspose.Words för .NET kan du följa dessa steg:
1.  Få tillgång till`DigitalSignatures` insamling av dokumenten.
2.  Iterera genom varje`DigitalSignature` föremål i samlingen.
3.  Använd`IsValid` egendom av`DigitalSignature` objekt för att kontrollera om signaturen är giltig.

#### F: Kan jag hämta undertecknarens kommentarer eller anledning till undertecknandet från en digital signatur i ett Word-dokument?

S: Ja, du kan hämta undertecknarens kommentarer eller anledning till signering från en digital signatur i ett Word-dokument. De`Comments` egendom av`DigitalSignature` Objektet ger tillgång till kommentarerna som anges av undertecknaren under signeringsprocessen.

#### F: Vilken typ av dokument stöder signaturverifieringsfunktionen i Aspose.Words för .NET?

S: Signaturverifieringsfunktionen i Aspose.Words för .NET stöder verifiering av digitala signaturer i Word-dokument med filformatet DOCX. Du kan använda den här funktionen för att verifiera signaturer i DOCX-filer.

#### F: Hur kan jag komma åt certifikatdetaljerna för en digital signatur i ett Word-dokument med Aspose.Words för .NET?

 S: För att komma åt certifikatdetaljerna för en digital signatur i ett Word-dokument med Aspose.Words för .NET kan du komma åt`CertificateHolder` egendom av`DigitalSignature` objekt. Från`CertificateHolder` objekt kan du hämta olika detaljer om certifikatet, såsom ämnesnamn och utfärdarens namn.

#### F: Kan jag anpassa visningen eller bearbetningen av digitala signaturer i ett Word-dokument med Aspose.Words för .NET?

 S: Ja, du kan anpassa visningen eller bearbetningen av digitala signaturer i ett Word-dokument med Aspose.Words för .NET. Genom att komma åt egenskaperna och metoderna för`DigitalSignature` objekt kan du extrahera den önskade informationen, utföra ytterligare valideringar eller integrera signaturverifieringsprocessen i din applikations arbetsflöde.

#### F: Är det möjligt att verifiera flera digitala signaturer i ett Word-dokument med Aspose.Words för .NET?

 S: Ja, det är möjligt att verifiera flera digitala signaturer i ett Word-dokument med Aspose.Words för .NET. Genom att iterera genom`DigitalSignatures` insamling av dokumentet kan du komma åt och verifiera varje digital signatur individuellt.

