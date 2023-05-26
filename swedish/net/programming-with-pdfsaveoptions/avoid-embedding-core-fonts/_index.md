---
title: Undvik att bädda in kärnteckensnitt
linktitle: Undvik att bädda in kärnteckensnitt
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du undviker grundläggande teckensnittsinbäddning när du konverterar Word-dokument till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/avoid-embedding-core-fonts/
---

I den här handledningen går vi igenom stegen för att använda funktionen Undvik grundläggande teckensnittsinbäddning med Aspose.Words för .NET. Den här funktionen låter dig styra om grundläggande typsnitt som Arial, Times New Roman, etc. måste bäddas in i PDF:en när du konverterar ett Word-dokument. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp Word-dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt Word-dokument.

## Steg 2: Ställ in PDF-konverteringsalternativ

Skapa en instans av klassen PdfSaveOptions och aktivera grundläggande teckensnittsinbäddning:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
```

Det här alternativet styr om basteckensnitt ska bäddas in i PDF:en eller inte.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera Word-dokumentet till PDF genom att ange konverteringsalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för Undvik att bädda in kärnteckensnitt med Aspose.Words för .NET

Här är den fullständiga källkoden för att använda funktionen för att undvika inbäddning av kärnteckensnitt med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Utdata-PDF-filen kommer inte att bäddas in med kärnteckensnitt som Arial, Times New Roman etc.
	PdfSaveOptions saveOptions = new PdfSaveOptions { UseCoreFonts = true };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.AvoidEmbeddingCoreFonts.pdf", saveOptions);

```

Genom att följa dessa steg kan du enkelt kontrollera om basteckensnitt ska bäddas in i PDF:en när du konverterar ett Word-dokument med Aspose.Words för .NET.

