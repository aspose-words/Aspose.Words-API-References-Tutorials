---
title: Interpolera bilder
linktitle: Interpolera bilder
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att möjliggöra bildinterpolation med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/interpolate-images/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder bildinterpolationsfunktionen med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du aktiverar bildinterpolation när du konverterar till PDF.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda upp dokumentet

Därefter måste vi ladda dokumentet vi vill bearbeta. I det här exemplet antar vi att dokumentet heter "Rendering.docx" och finns i den angivna dokumentkatalogen.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 3: Konfigurera alternativ för att spara som PDF med raminterpolation

 För att möjliggöra interpolering av bilder vid konvertering till PDF måste vi konfigurera`PdfSaveOptions` objekt genom att ställa in`InterpolateImages` egendom till`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };
```

## Steg 4: Spara dokumentet som en PDF med raminterpolation

Slutligen kan vi spara dokumentet i PDF-format med hjälp av de sparade alternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt aktiverat bildinterpolering när du konverterade ett dokument till PDF med Aspose.Words för .NET.

### Exempel på källkod för bildinterpolation med Aspose.Words för .NET


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { InterpolateImages = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.InterpolateImages.pdf", saveOptions);

```
