---
title: Exportera sidfotsbokmärken
linktitle: Exportera sidfotsbokmärken
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att exportera sidhuvuden och sidfotsbokmärken med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen Exportera sidhuvud och sidfotsbokmärken med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du exporterar bokmärken från sidhuvuden och sidfötter i ett dokument och genererar en PDF med lämpliga bokmärken.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda upp dokumentet

Därefter måste vi ladda dokumentet vi vill bearbeta. I det här exemplet antar vi att dokumentet heter "Bokmärken i sidhuvuden och sidfötter.docx" och finns i den angivna dokumentkatalogen.

```csharp
Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");
```

## Steg 3: Konfigurera spara som PDF-alternativ

 För att exportera sidhuvuden och sidfötter måste vi konfigurera`PdfSaveOptions` objekt. I det här exemplet ställer vi in standardnivån för bokmärkeskontur till 1 och exportläget för sidhuvud och sidfot till "Första".

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;
```

## Steg 4: Spara dokumentet som PDF med sidhuvuden och sidfötter bokmärken

Slutligen kan vi spara dokumentet i PDF-format med hjälp av de sparade alternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt exporterat sidhuvuden och sidfotsbokmärken från ett dokument och skapat en PDF med lämpliga bokmärken med Aspose.Words för .NET.

### Exempel på källkod för att exportera sidhuvuden och sidfotsbokmärken med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks in headers and footers.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.DefaultBookmarksOutlineLevel = 1;
	saveOptions.HeaderFooterBookmarksExportMode = HeaderFooterBookmarksExportMode.First;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportHeaderFooterBookmarks.pdf", saveOptions);

```
