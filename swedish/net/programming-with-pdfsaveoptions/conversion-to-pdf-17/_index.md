---
title: Konvertering till pdf 17
linktitle: Konvertering till pdf 17
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar dokument till PDF 1.7 med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

I den här handledningen går vi igenom stegen för att konvertera till PDF 1.7 med Aspose.Words för .NET. Genom att konvertera till PDF 1.7 kan du generera PDF-filer som överensstämmer med PDF 1.7-standarden. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt dokument.

## Steg 2: Ställ in PDF-konverteringsalternativ

Skapa en instans av klassen PdfSaveOptions och ange versionen av PDF-standarden du vill använda:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Detta alternativ säkerställer att den genererade PDF-filen överensstämmer med PDF 1.7-standarden.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av konverteringsalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för konvertering till pdf 17 med Aspose.Words för .NET

Här är den fullständiga källkoden för att konvertera till PDF 1.7 med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Genom att följa dessa steg kan du enkelt konvertera till PDF 1.7 med Aspose.Words för .NET.

