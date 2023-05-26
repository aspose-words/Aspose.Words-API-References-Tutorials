---
title: Exportera dokumentstruktur
linktitle: Exportera dokumentstruktur
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att exportera dokumentstruktur med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/export-document-structure/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen Exportera dokumentstruktur med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du exporterar strukturen för ett dokument och genererar en PDF med strukturen för dokumentet synlig.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda upp dokumentet

Därefter måste vi ladda dokumentet vi vill bearbeta. I det här exemplet antar vi att dokumentet heter "Paragraphs.docx" och finns i den angivna dokumentkatalogen.

```csharp
Document doc = new Document(dataDir + "Paragraphs.docx");
```

## Steg 3: Konfigurera spara som PDF-alternativ

 För att exportera dokumentstrukturen och göra strukturen synlig i Adobe Acrobat Pros navigeringsfönster "Innehåll" när vi redigerar PDF-filen måste vi konfigurera`PdfSaveOptions` objekt med`ExportDocumentStructure` egenskapen inställd på`true`.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };
```

## Steg 4: Spara dokumentet som PDF med dokumentstrukturen

Slutligen kan vi spara dokumentet i PDF-format med hjälp av de sparade alternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
```

Det är allt ! Du har framgångsrikt exporterat en dokumentstruktur och genererat en PDF med dokumentstrukturen synlig med Aspose.Words för .NET.

### Exempel på källkod för export av dokumentstruktur med Aspose.Words för .NET


```csharp

            // Sökvägen till dokumentkatalogen.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(dataDir + "Paragraphs.docx");

            // Filstorleken kommer att ökas och strukturen kommer att synas i navigeringsrutan "Innehåll".
            // av Adobe Acrobat Pro, medan du redigerar .pdf.
            PdfSaveOptions saveOptions = new PdfSaveOptions { ExportDocumentStructure = true };

            doc.Save(dataDir + "WorkingWithPdfSaveOptions.ExportDocumentStructure.pdf", saveOptions);
        
```
