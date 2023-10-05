---
title: Exportera Word-dokumentstruktur till PDF-dokument
linktitle: Exportera Word-dokumentstruktur till PDF-dokument
second_title: Aspose.Words Document Processing API
description: Steg för steg guide för att exportera Word-dokumentstruktur till PDF-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/export-document-structure/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen Exportera Word-dokumentstruktur till PDF-dokument med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du exporterar strukturen för ett dokument och genererar en PDF med strukturen för dokumentet synlig.

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


## Slutsats

I den här handledningen har vi förklarat hur man exporterar strukturen för ett Word-dokument till ett PDF-dokument med Aspose.Words för .NET. Genom att följa stegen som beskrivs kan du enkelt skapa en PDF med din dokumentstruktur synlig, vilket gör det lättare att navigera och söka i dokumentet. Använd funktionerna i Aspose.Words för .NET för att exportera strukturen i dina Word-dokument och skapa välstrukturerade PDF-filer.

### Vanliga frågor

#### F: Vad är att exportera strukturen för ett Word-dokument till ett PDF-dokument?
S: Genom att exportera strukturen för ett Word-dokument till ett PDF-dokument skapas en PDF med en synlig dokumentstruktur. Dokumentstruktur inkluderar vanligtvis saker som rubriker, avsnitt, stycken och andra strukturerade delar av dokumentet. Denna struktur kan vara användbar för navigering och sökning i PDF-dokumentet.

#### F: Hur kan jag exportera strukturen för ett Word-dokument till ett PDF-dokument med Aspose.Words för .NET?
S: För att exportera strukturen för ett Word-dokument till ett PDF-dokument med Aspose.Words för .NET, följ dessa steg:

 Skapa en instans av`Document` klass som anger sökvägen till Word-dokumentet.

 Skapa en instans av`PdfSaveOptions` klass och ställ in`ExportDocumentStructure`egendom till`true`. Detta kommer att exportera dokumentstrukturen och göra den synlig i Adobe Acrobat Pros "Innehåll" navigeringsfönster när du redigerar PDF-filen.

 Använd`Save` metod för`Document`klass för att spara dokumentet i PDF-format genom att ange sparalternativ.

#### F: Hur kan jag se strukturen för ett PDF-dokument med Adobe Acrobat Pro?
S: För att se strukturen för ett PDF-dokument med Adobe Acrobat Pro, följ dessa steg:

Öppna PDF-dokumentet i Adobe Acrobat Pro.

Klicka på ikonen "Innehåll" i det vänstra navigeringsfältet för att visa navigeringsfönstret "Innehåll".

I navigeringsrutan "Innehåll" ser du dokumentstrukturen med rubriker, avsnitt och andra strukturerade element.