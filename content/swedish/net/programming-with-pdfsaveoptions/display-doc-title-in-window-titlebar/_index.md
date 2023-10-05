---
title: Visa dokumentrubrik i fönstrets titelrad
linktitle: Visa dokumentrubrik i fönstrets titelrad
second_title: Aspose.Words Document Processing API
description: Lär dig hur du visar dokumenttitel i fönstrets namnlist när du konverterar till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

den här handledningen kommer vi att guida dig genom stegen för att visa dokumenttiteln i fönstrets namnlist med Aspose.Words för .NET. Den här funktionen låter dig visa dokumentets titel i fönstrets namnlist när du öppnar det genererade PDF-dokumentet. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt dokument.

## Steg 2: Konfigurera PDF-sparalternativ

Skapa en instans av klassen PdfSaveOptions och aktivera visningen av dokumenttiteln i fönstrets namnlist:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

Detta alternativ möjliggör visning av dokumenttiteln i fönstrets namnlist vid konvertering till PDF.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av konverteringsalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för Visa dokumenttitel i fönstrets titelrad med Aspose.Words för .NET

Här är den fullständiga källkoden för att visa dokumenttiteln i fönstrets namnlist i ett PDF-dokument med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
Genom att följa dessa steg kan du enkelt visa dokumenttiteln i fönstrets namnlist när du konverterar till PDF med Aspose.Words för .NET.

### Vanliga frågor

#### F: Vad är funktionen "Visa dokumenttitel i fönstrets namnlist" med Aspose.Words för .NET?
Funktionen "Visa dokumenttitel i fönstrets namnlist" med Aspose.Words för .NET låter dig visa dokumenttiteln i fönstrets namnlist när du öppnar det genererade PDF-dokumentet. Detta gör det lättare att identifiera och särskilja PDF-dokument i din läsmiljö.

#### F: Hur kan jag använda den här funktionen med Aspose.Words för .NET?
För att använda den här funktionen med Aspose.Words för .NET, följ dessa steg:

 Ladda dokumentet med hjälp av`Document` metod och ange sökvägen till filen som ska konverteras till PDF.

 Konfigurera PDF-sparalternativ genom att skapa en instans av`PdfSaveOptions` klass och ställa in`DisplayDocTitle`egendom till`true`. Detta möjliggör visning av dokumenttiteln i fönstrets namnlist vid konvertering till PDF.

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av konverteringsalternativ.

#### F: Ändrar den här funktionen innehållet i själva dokumentet?
Nej, den här funktionen ändrar inte innehållet i själva dokumentet. Det påverkar bara visningen av dokumenttiteln i fönstrets namnlist när den öppnas som ett PDF-dokument. Innehållet i dokumentet förblir oförändrat.

#### F: Är det möjligt att anpassa titeln på dokumentet som visas i fönstrets namnlist?
 Ja, du kan anpassa dokumenttiteln som visas i fönstrets namnlist genom att ändra`Document.Title` egenskapen för dokumentet innan du konverterar det till PDF. Du kan ställa in önskad titel med en sträng. Se till att ställa in titeln innan du ringer`Save` metod för att konvertera till PDF.

#### F: Vilka andra utdataformat stöder Aspose.Words för dokumentkonvertering?
Aspose.Words för .NET stöder många utdataformat för dokumentkonvertering, såsom PDF, XPS, HTML, EPUB, MOBI, bild (JPEG, PNG, BMP, TIFF, GIF) och många fler. ytterligare andra. Du kan välja lämpligt utdataformat enligt dina specifika behov.