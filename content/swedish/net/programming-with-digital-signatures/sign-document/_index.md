---
title: Signera Word-dokument
linktitle: Signera Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du digitalt signerar ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-digital-signatures/sign-document/
---
I den här handledningen går vi igenom stegen för att använda dokumentsigneringsfunktionen med Aspose.Words för .NET. Den här funktionen låter dig signera ett Word-dokument digitalt med ett certifikat. Följ stegen nedan:

## Steg 1: Laddar certifikatet

Börja med att ladda signeringscertifikatet med klassen CertificateHolder:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
```

Var noga med att ange rätt sökväg till ditt certifikat och tillhörande lösenord.

## Steg 2: Signera dokumentet

Använd klassen DigitalSignatureUtil för att signera dokumentet:

```csharp
DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
	certHolder);
```

Var noga med att ange rätt sökvägar för källdokumentet och det signerade dokumentet.

### Exempel på källkod för Sign Document med Aspose.Words för .NET

Här är den fullständiga källkoden för att signera ett dokument med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	CertificateHolder certHolder = CertificateHolder.Create(dataDir + "morzal.pfx", "aw");
	
	DigitalSignatureUtil.Sign(dataDir + "Digitally signed.docx", dataDir + "Document.Signed.docx",
		certHolder);

```

Genom att följa dessa steg kan du enkelt signera ett Word-dokument med Aspose.Words för .NET.

## Slutsats

 I den här handledningen utforskade vi dokumentsigneringsfunktionen i Aspose.Words för .NET. Genom att ladda ett signeringscertifikat och använda`DigitalSignatureUtil.Sign` metod kan vi digitalt signera ett Word-dokument. Dokumentsignering ger autentisering och säkerställer integriteten hos dokumentets innehåll, vilket gör det till en värdefull funktion för säker och pålitlig dokumenthantering.

### Vanliga frågor för sign word-dokument

#### F: Vad är dokumentsignering i Aspose.Words för .NET?

S: Dokumentsignering i Aspose.Words för .NET avser processen att digitalt signera ett Word-dokument med ett certifikat. Den här funktionen lägger till en digital signatur till dokumentet, vilket ger äkthet, integritet och inte förkastande av dokumentets innehåll.

#### F: Hur kan jag ladda signeringscertifikatet i Aspose.Words för .NET?

 S: För att ladda signeringscertifikatet i Aspose.Words för .NET kan du använda`CertificateHolder` klass. Skapa en instans av`CertificateHolder` genom att ange sökvägen till certifikatfilen och det tillhörande lösenordet. Här är ett exempel:

```csharp
CertificateHolder certHolder = CertificateHolder.Create("path/to/certificate.pfx", "password");
```

Se till att ange rätt sökväg till ditt certifikat och tillhörande lösenord.

#### F: Hur signerar jag ett Word-dokument med Aspose.Words för .NET?

 S: För att signera ett Word-dokument med Aspose.Words för .NET, kan du använda`DigitalSignatureUtil` klass. Ring`Sign` metod, som tillhandahåller sökvägen till källdokumentet, sökvägen till det signerade dokumentet (utdata) och`CertificateHolder` objekt. Här är ett exempel:

```csharp
DigitalSignatureUtil.Sign("path/to/source/document.docx", "path/to/signed/document.docx", certHolder);
```

Se till att du anger rätt sökvägar för källdokumentet och det signerade dokumentet (utdata).

#### F: Vad är syftet med dokumentsignering?

S: Dokumentsignering fungerar som en metod för att säkerställa ett dokuments äkthet och integritet. Genom att digitalt signera ett dokument kan du tillhandahålla bevis på dess ursprung, verifiera att dess innehåll inte har ändrats och fastställa att det inte är förkastande. Dokumentsignering används ofta för juridiska, finansiella och känsliga dokument.

#### F: Kan jag använda vilket certifikat som helst för dokumentsignering i Aspose.Words för .NET?

S: För dokumentsignering i Aspose.Words för .NET måste du använda ett giltigt X.509-certifikat. Detta certifikat kan erhållas från en betrodd certifikatutfärdare (CA) eller så kan ett självsignerat certifikat användas för teständamål.

#### F: Vilket filformat stöder Aspose.Words for .NET för dokumentsignering?

 S: Aspose.Words för .NET stöder dokumentsignering för Word-dokument i filformatet DOCX. Du kan signera DOCX-filer med hjälp av`DigitalSignatureUtil` klass och lämpligt certifikat.

#### F: Kan jag signera flera Word-dokument med samma certifikat?

S: Ja, du kan signera flera Word-dokument med samma certifikat. När du har laddat certifikatet med hjälp av`CertificateHolder` klass, kan du återanvända den för att signera flera dokument genom att ringa`DigitalSignatureUtil.Sign` metod med olika källa och signerade dokumentvägar.

#### F: Ändrar dokumentsignering originaldokumentet?

S: Dokumentsignering med Aspose.Words för .NET ändrar inte originaldokumentet. Istället skapar den en digitalt signerad kopia av dokumentet, vilket lämnar originaldokumentet intakt. Den digitalt signerade kopian innehåller den tillagda digitala signaturen, vilket säkerställer integriteten hos dokumentets innehåll.

#### F: Kan jag verifiera den digitala signaturen för ett signerat dokument med Aspose.Words för .NET?

 S: Ja, Aspose.Words för .NET tillhandahåller funktionalitet för att verifiera den digitala signaturen för ett signerat dokument. Du kan använda`DigitalSignatureUtil.Verify` metod för att kontrollera giltigheten och äktheten av den digitala signaturen.