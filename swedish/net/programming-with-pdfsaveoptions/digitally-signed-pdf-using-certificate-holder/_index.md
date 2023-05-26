---
title: Digitalt signerad pdf med certifikathållare
linktitle: Digitalt signerad pdf med certifikathållare
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du signerar en PDF digitalt med en certifikatinnehavare med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/digitally-signed-pdf-using-certificate-holder/
---

den här handledningen går vi igenom stegen för att skapa en digitalt signerad PDF med ett certifikat med Aspose.Words för .NET. Den digitala signaturen lägger till ett lager av säkerhet och integritet till PDF-dokumentet. Följ stegen nedan:

## Steg 1: Skapa dokumentet och lägga till innehåll

Börja med att skapa en instans av klassen Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Lägg till innehåll i dokumentet

 Använd sedan`DocumentBuilder` för att lägga till innehåll i dokumentet. Om du till exempel vill lägga till ett stycke som innehåller texten "Testsignerad PDF" använder du`Writeln` metod:

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
