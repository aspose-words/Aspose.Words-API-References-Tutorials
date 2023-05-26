---
title: Visa dokumentets titel i fönstrets titelrad
linktitle: Visa dokumentets titel i fönstrets titelrad
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du visar dokumenttitel i fönstrets namnlist när du konverterar till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

I den här handledningen kommer vi att guida dig genom stegen för att visa dokumenttiteln i fönstrets namnlist med Aspose.Words för .NET. Den här funktionen låter dig visa dokumentets titel i fönstrets namnlist när du öppnar det genererade PDF-dokumentet. Följ stegen nedan:

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

