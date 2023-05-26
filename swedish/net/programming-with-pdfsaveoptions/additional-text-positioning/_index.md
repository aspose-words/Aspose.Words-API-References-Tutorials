---
title: Ytterligare textpositionering
linktitle: Ytterligare textpositionering
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du kontrollerar placeringen av ytterligare text när du konverterar Word-dokument till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/additional-text-positioning/
---

I den här handledningen går vi igenom stegen för att använda den extra textpositioneringsfunktionen med Aspose.Words för .NET. Den här funktionen låter dig styra placeringen av ytterligare text när du konverterar ett Word-dokument till PDF. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp Word-dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt Word-dokument.

## Steg 2: Ställ in PDF-konverteringsalternativ

Skapa en instans av klassen PdfSaveOptions och aktivera extra textpositionering:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };
```

Det här alternativet styr den exakta placeringen av ytterligare text i PDF-filen.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera Word-dokumentet till PDF genom att ange konverteringsalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för ytterligare textpositionering med Aspose.Words för .NET

Här är den fullständiga källkoden för att använda den extra textpositioneringsfunktionen med Aspose.Words för .NET:


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { AdditionalTextPositioning = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AdditionalTextPositioning.pdf", saveOptions);

```
Genom att följa dessa steg kan du enkelt styra placeringen av ytterligare text när du konverterar ett Word-dokument till PDF med Aspose.Words för .NET.

