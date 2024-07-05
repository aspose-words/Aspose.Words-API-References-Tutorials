---
title: Exportera Word-dokument sidfotsbokmärken till PDF-dokument
linktitle: Exportera Word-dokument sidfotsbokmärken till PDF-dokument
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att exportera sidfotsbokmärken för Word-dokument till pdf-dokumentbokmärken med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/export-header-footer-bookmarks/
---

Den här artikeln ger en steg-för-steg-guide om hur du exporterar sidfotsbokmärken i Word-dokument till pdf-dokumentfunktionen med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du exporterar bokmärken från sidhuvuden och sidfötter i ett dokument och genererar en PDF med lämpliga bokmärken.

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

## Slutsats

den här handledningen förklarade vi hur man exporterar sidhuvuden och sidfotsbokmärken från ett Word-dokument till ett PDF-dokument med Aspose.Words för .NET. Exporterade bokmärken möjliggör enkel navigering och snabb referens till motsvarande sidhuvuden och sidfötter i det genererade PDF-dokumentet. Följ stegen som beskrivs för att exportera sidhuvuden och sidfotsbokmärken från ett dokument och generera en PDF med lämpliga bokmärken med Aspose.Words för .NET. Var noga med att ange rätt sökväg till dina dokument och konfigurera sparaalternativ efter behov.

### Vanliga frågor

### F: Vad är att exportera sidhuvuden och sidfotsbokmärken från ett Word-dokument till ett PDF-dokument?
S: Att exportera sidhuvuden och sidfötter från Word-dokument till PDF-dokument är en funktion för att behålla och generera bokmärken i PDF-dokumentet från sidhuvuden och sidfötter. sidfötter i det ursprungliga Word-dokumentet. Detta tillåter användare att snabbt och enkelt navigera genom PDF-dokumentet genom att använda bokmärken som motsvarar sidhuvuden och sidfötter.

### F: Hur kan jag använda Aspose.Words för .NET för att exportera sidhuvuden och sidfötter från ett Word-dokument till ett PDF-dokument?
S: För att exportera sidhuvuden och sidfotsbokmärken från ett Word-dokument till ett PDF-dokument med Aspose.Words för .NET, följ dessa steg:

 Ställ in katalogsökvägen där dina dokument finns genom att ersätta`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

 Ladda dokumentet du vill bearbeta med hjälp av`Document` klass och ange sökvägen till Word-dokumentet i den angivna dokumentkatalogen.

 Konfigurera spara som PDF-alternativ genom att skapa en instans av`PdfSaveOptions` klass och ställa in lämpliga sidhuvud och sidfots bokmärkesalternativ.

 Spara dokumentet i PDF-format med hjälp av`Save` metod för`Document` klass som anger sökvägen och sparalternativ.

### F: Vilka är fördelarna med att exportera sidhuvuden och sidfötter till ett PDF-dokument?
S: Fördelarna med att exportera sidhuvuden och sidfotsbokmärken till ett PDF-dokument är:

Enkel navigering: Bokmärken tillåter användare att enkelt navigera i ett PDF-dokument genom att hänvisa till specifika sidhuvuden och sidfötter.

Snabbreferens: Med bokmärken kan användare snabbt hitta relevanta delar av PDF-dokumentet baserat på sidhuvuden och sidfötter.