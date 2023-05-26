---
title: Ladda krypterad pdf
linktitle: Ladda krypterad pdf
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg guide för att ladda en krypterad PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

När du arbetar med PDF-dokument i din .NET-applikation kan det vara nödvändigt att ladda PDF-filer som är lösenordsskyddade. Aspose.Words för .NET är ett kraftfullt bibliotek som tillhandahåller funktionalitet för att ladda krypterade PDF-dokument. I den här artikeln guidar vi dig steg för steg för att förstå och använda den här funktionen.

## Förstå Load Encrypted PDF-funktionen

Funktionen Ladda krypterad PDF i Aspose.Words för .NET låter dig ladda PDF-filer som är lösenordsskyddade. Du kan ange lösenordet när du laddar dokumentet så att du kan komma åt dess innehåll och manipulera det efter behov.

## Steg 1: Laddar det krypterade PDF-dokumentet

Det första steget är att ladda det krypterade PDF-dokumentet i din applikation. Så här gör du:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

 Var noga med att ange rätt sökväg till den krypterade PDF-filen i`dataDir` variabel.

## Steg 2: Kryptera PDF-dokumentet

 Om du också vill kryptera ditt PDF-dokument kan du göra det med hjälp av`PdfSaveOptions` klass och specificera krypteringsdetaljerna:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

Detta kommer att skapa en krypterad version av PDF-dokumentet i den angivna katalogen.

## Steg 3: Spara det krypterade PDF-dokumentet

Efter att ha laddat upp och eventuellt krypterat PDF-dokumentet kan du spara det i ett annat format eller bearbeta det vidare enligt dina specifika behov.

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## Steg 5: Laddar det krypterade PDF-dokumentet med lösenord

Underhåll

 Men om du vill ladda det krypterade PDF-dokumentet med ett lösenord måste du använda`PdfLoadOptions` klass och ange lösenordet när du laddar dokumentet:

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

 Var noga med att ange rätt lösenord i`Password` variabel.

### Exempel på källkod för att ladda krypterad PDF med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## Slutsats

I den här artikeln undersökte vi hur man använder funktionen Ladda krypterad PDF i Aspose.Words för .NET. Du lärde dig hur man laddar upp krypterade PDF-filer, hur man krypterar ett PDF-dokument, hur man laddar upp en krypterad PDF med ett lösenord och hur man genererar utdata i Markdown-format. Den här funktionen är extremt användbar när du arbetar med säkra PDF-dokument.


