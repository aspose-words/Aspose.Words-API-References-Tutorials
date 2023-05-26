---
title: Hoppa över inbäddade Arial- och Times Roman-teckensnitt
linktitle: Hoppa över inbäddade Arial- och Times Roman-teckensnitt
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att generera PDF utan att bädda in Arial- och Times Roman-teckensnitt med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/skip-embedded-arial-and-times-roman-fonts/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen för att hoppa över inbäddade Arial- och Times Roman-teckensnitt till metafilstorlek med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du konfigurerar alternativet för typsnittsinbäddningsläge i ett dokument och genererar en PDF utan att bädda in Arial- och Times Roman-teckensnitt.

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

## Steg 3: Konfigurera spara som PDF-alternativ med teckensnittsinbäddning

 För att hoppa över att bädda in Arial- och Times Roman-teckensnitt i den genererade PDF-filen måste vi konfigurera`PdfSaveOptions` objekt och ställ in`FontEmbeddingMode` egendom till`PdfFontEmbeddingMode.EmbedAll`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };
```

## Steg 4: Spara dokumentet som PDF utan inbäddade teckensnitt

Slutligen kan vi spara dokumentet i PDF-format med hjälp av de sparade alternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt skapat en PDF utan att bädda in Arial- och Times Roman-teckensnitt med Aspose.Words för .NET.

### Exempel på källkod för att hoppa över inbäddade Arial- och Times Roman-teckensnitt i metafilstorlek med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedAll };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SkipEmbeddedArialAndTimesRomanFonts.pdf", saveOptions);
   
```
