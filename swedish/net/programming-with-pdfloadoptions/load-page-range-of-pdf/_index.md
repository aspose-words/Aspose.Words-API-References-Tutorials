---
title: Ladda sidintervall av pdf
linktitle: Ladda sidintervall av pdf
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att ladda ett specifikt PDF-sidintervall med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

I den här handledningen går vi igenom hur du laddar ett specifikt sidintervall från ett PDF-dokument med Aspose.Words för .NET. Följ stegen nedan:

## Steg 1: Ladda en rad PDF-sidor

Använd följande kod för att ladda ett specifikt sidintervall från ett PDF-dokument:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

 I det här exemplet laddar vi den första sidan av PDF-dokumentet. Du kan ändra värdena på`PageIndex` och`PageCount` till önskat sidintervall.

## Steg 2: Spara dokumentet

 Slutligen kan du spara dokumentet som innehåller det specifika sidintervallet med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

Var noga med att ange rätt sökväg för att spara det redigerade dokumentet.

Det är allt ! Du har nu laddat ett specifikt sidintervall från ett PDF-dokument med Aspose.Words för .NET.

### Exempel på källkod för Load Page Range Of Pdf med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
Kom ihåg att ange rätt sökväg till katalogen för dina PDF-dokument.



