---
title: Skapa och signera ny signaturlinje
linktitle: Skapa och signera ny signaturlinje
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar och signerar en ny signaturrad i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/creating-and-signing-new-signature-line/
---
I den här handledningen går vi igenom stegen för att använda funktionen skapa och signera en ny signaturlinje med Aspose.Words för .NET. Med den här funktionen kan du infoga en signaturrad i ett Word-dokument, ställa in anpassade alternativ och signera dokumentet. Följ stegen nedan:

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

## Slutsats

den här handledningen lärde vi oss hur man skapar och signerar en ny signaturrad i ett Word-dokument med Aspose.Words för .NET. Genom att följa de angivna stegen kan du enkelt infoga en signaturrad i ditt dokument, anpassa dess alternativ och signera dokumentet med ett digitalt certifikat. Att lägga till signaturrader och digitala signaturer till dina dokument förbättrar deras autenticitet och integritet, vilket gör dem säkrare och mer pålitliga. Aspose.Words för .NET tillhandahåller ett kraftfullt API för ordbehandling med signaturer och digitala certifikat i Word-dokument, vilket gör att du kan automatisera signeringsprocessen och säkerställa att dina dokument är giltiga.

### FAQ's

#### F: Vad är en signaturrad i ett Word-dokument?

S: En signaturrad i ett Word-dokument är en platshållare som anger var en signatur ska placeras. Den innehåller vanligtvis namn, titel och datum och ger utrymme för en handskriven eller digital signatur.

#### F: Hur kan jag skapa en signaturrad i ett Word-dokument med Aspose.Words för .NET?

S: För att skapa en signaturrad i ett Word-dokument med Aspose.Words för .NET, kan du följa dessa steg:
1.  Skapa en instans av`Document` klass och a`DocumentBuilder` objekt.
2.  Använd`InsertSignatureLine` metod för`DocumentBuilder` objekt för att infoga en ny signaturrad i dokumentet.
3. Spara det ändrade dokumentet.

#### F: Kan jag anpassa signaturradsalternativen, som namn, titel och datum?

 S: Ja, du kan anpassa signaturradsalternativen. De`SignatureLineOptions` klass tillhandahåller egenskaper för att ställa in önskade alternativ, som t.ex`Signer`, `SignerTitle`, `ShowDate`, etc. Du kan ändra dessa egenskaper innan du infogar signaturraden.

#### F: Hur kan jag signera dokumentet efter att ha skapat en signaturrad?

 S: För att signera dokumentet efter att ha skapat en signaturrad, måste du ställa in signaturalternativen och använda`DigitalSignatureUtil` klass. Här är stegen:
1.  Ställ in`SignatureLineId` egendom i`SignOptions` invända mot signaturradens ID.
2.  Ställ in`SignatureLineImage` egendom i`SignOptions` invända mot bilden av signaturen du vill använda.
3.  Ladda signeringscertifikatet med hjälp av`CertificateHolder` klass.
4.  Använd`DigitalSignatureUtil.Sign` metod för att signera dokumentet, tillhandahålla nödvändiga parametrar.

#### F: Kan jag använda en digital signaturbild för att signera dokumentet?

 S: Ja, du kan använda en digital signaturbild för att signera dokumentet. För att göra detta måste du tillhandahålla bildfilen i`SignOptions` objekt med hjälp av`SignatureLineImage`fast egendom. Bilden kan vara i alla bildformat som stöds, till exempel JPEG, PNG eller EMF.

#### F: Vad är syftet med att skapa och signera en ny signaturrad i ett Word-dokument?

S: Genom att skapa och signera en ny signaturrad i ett Word-dokument med Aspose.Words för .NET kan du lägga till en platshållare för en signatur och sedan signera dokumentet med ett digitalt certifikat. Denna process säkerställer dokumentets äkthet och integritet, vilket ger bevis på godkännande eller avtal.

#### F: Kan jag skapa och signera flera signaturrader i ett Word-dokument med Aspose.Words för .NET?

S: Ja, du kan skapa och signera flera signaturrader i ett Word-dokument med Aspose.Words för .NET. Varje signaturrad kan ha sitt eget unika ID och alternativ. Du kan upprepa stegen för att skapa och signera ytterligare signaturrader i dokumentet.

#### F: Kan jag ändra signaturraden eller lägga till ytterligare information efter att den har signerats?

S: När en signaturrad har signerats blir den en del av dokumentets innehåll och kan inte ändras separat. Du kan dock lägga till ytterligare information eller innehåll efter den signerade signaturraden.

#### F: Kan jag verifiera den digitala signaturen för ett dokument som innehåller en signaturrad?

 S: Ja, Aspose.Words för .NET tillhandahåller funktionalitet för att verifiera den digitala signaturen för ett dokument som innehåller en signaturrad. Du kan använda`DigitalSignatureUtil.Verify` metod för att kontrollera giltigheten och äktheten av den digitala signaturen.

#### F: Vilket filformat stöder Aspose.Words for .NET för att skapa och signera signaturrader?

S: Aspose.Words för .NET stöder att skapa och signera signaturrader i DOCX-filformatet. Du kan skapa och signera signaturrader i DOCX-filer med hjälp av de medföljande metoderna och klasserna.