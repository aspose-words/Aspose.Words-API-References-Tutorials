---
title: Lägg till digital signatur till PDF med certifikathållare
linktitle: Lägg till digital signatur till PDF med certifikathållare
second_title: Aspose.Words Document Processing API
description: Lär dig hur du lägger till digital signatur till PDF med Certificate Holder med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

I den här handledningen går vi igenom stegen för att lägga till digital signatur till PDF med certifikatinnehavare med Aspose.Words för .NET. Den digitala signaturen lägger till ett lager av säkerhet och integritet till PDF-dokumentet. Följ stegen nedan:

## Steg 1: Skapa dokumentet och lägga till innehåll

Börja med att skapa en instans av klassen Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Lägg till innehåll i dokumentet

 Använd sedan`DocumentBuilder`för att lägga till innehåll i dokumentet. Om du till exempel vill lägga till ett stycke som innehåller texten "Testsignerad PDF" använder du`Writeln` metod:

```csharp
builder.Writeln("Test Signed PDF.");
```

Du kan lägga till andra innehållsobjekt efter behov.

## Steg 3: Ställ in PDF-sparalternativ

Skapa en instans av klassen PdfSaveOptions och ange detaljerna för den digitala signaturen:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
	DigitalSignatureDetails = new PdfDigitalSignatureDetails(
		CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
		DateTime.Now)
};
```

Var noga med att ange rätt sökväg till ditt certifikat och tillhörande lösenord. Du kan också anpassa signaturens orsak och plats.

## Steg 4: Spara dokument som digitalt signerad PDF

 Använd`Save` metod för att spara dokumentet som en PDF genom att ange sparalternativen:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den digitalt signerade PDF-filen.

Genom att följa dessa steg kan du enkelt skapa en digitalt signerad PDF med ett certifikat med Aspose.Words för .NET.

### Exempel på källkod för digitalt signerad pdf med certifikatinnehavare med Aspose.Words för .NET

Här är den fullständiga källkoden till digitalt signerad PDF med certifikatinnehavare från ett dokument som använder Aspose.Words för .NET:

```csharp

            // Sökvägen till dokumentkatalogen.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document();
            DocumentBuilder builder = new DocumentBuilder(doc);
            
            builder.Writeln("Test Signed PDF.");

            PdfSaveOptions saveOptions = new PdfSaveOptions
            {
                DigitalSignatureDetails = new PdfDigitalSignatureDetails(
                    CertificateHolder.Create(MyDir + "morzal.pfx", "aw"), "reason", "location",
                    DateTime.Now)
            };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.DigitallySignedPdfUsingCertificateHolder.pdf", saveOptions);
            
        
```
## Slutsats

den här handledningen utforskade vi stegen för att lägga till en digital signatur i ett PDF-dokument med hjälp av ett certifikat med Aspose.Words för .NET. Den digitala signaturen lägger till ett lager av säkerhet och integritet till dokumentet, vilket garanterar dess äkthet och gör det möjligt att upptäcka eventuella efterföljande ändringar. Genom att följa de givna stegen kan du enkelt skapa en digitalt signerad PDF med ett certifikat med Aspose.Words för .NET.

### Vanliga frågor

#### F: Vad är en digital signatur och varför är den viktig i ett PDF-dokument?
S: En digital signatur är en säkerhetsteknik som hjälper till att säkerställa äktheten, integriteten och att ett elektroniskt dokument, till exempel en PDF-fil, inte förkastas. Den använder ett digitalt certifikat för att lägga till ett säkerhetslager till dokumentet, vilket hjälper till att verifiera författarens identitet och upptäcka eventuella efterföljande ändringar av innehållet.

#### F: Hur kan jag lägga till en digital signatur i ett PDF-dokument med ett certifikat med Aspose.Words för .NET?
S: För att lägga till en digital signatur i ett PDF-dokument med ett certifikat med Aspose.Words för .NET, följ dessa steg:

 Skapa en instans av`Document` klass för att representera dokumentet.

 Använd`DocumentBuilder` klass för att lägga till önskat innehåll i dokumentet.

 Skapa en instans av`PdfSaveOptions` klass och ange detaljerna för den digitala signaturen med hjälp av`PdfDigitalSignatureDetails` klass. Du måste ange sökvägen till certifikatet (`CertificateHolder.Create`), det associerade lösenordet och signeringsorsaken och platsen.

 Använd`Save` metod för att spara dokumentet i PDF-format med angivande av sparalternativ.

#### F: Hur får jag ett certifikat för att lägga till en digital signatur i ett PDF-dokument?
S: För att få ett certifikat för att lägga till en digital signatur i ett PDF-dokument kan du vanligtvis kontakta en certifikatutfärdare (CA) eller en leverantör av betrodda tjänster. Dessa enheter utfärdar digitala certifikat efter att ha verifierat din identitet och validerat din begäran. När du har fått ett certifikat kan du använda det i din ansökan för att lägga till digitala signaturer i PDF-dokument.

#### F: Är det möjligt att anpassa detaljerna för den digitala signaturen, som orsak och plats?
 S: Ja, du kan anpassa detaljerna för den digitala signaturen genom att ange orsaken och platsen för signaturen. I exempelkoden som tillhandahålls kan du ändra värdena för`reason` och`location` parametrar när du skapar`PdfDigitalSignatureDetails` objekt. Se till att tillhandahålla lämplig information för varje parameter för att återspegla orsaken och platsen för signaturen i ditt PDF-dokument.