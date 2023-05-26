---
title: Inaktivera Bädda in Windows-teckensnitt
linktitle: Inaktivera Bädda in Windows-teckensnitt
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du inaktiverar Windows-fontinbäddning när du konverterar dokument till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

I den här handledningen går vi igenom stegen för att inaktivera Windows-fontinbäddning i ett PDF-dokument med Aspose.Words för .NET. Genom att inaktivera teckensnittsinbäddning kan du minska storleken på den genererade PDF-filen. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt dokument.

## Steg 2: Ställ in PDF-sparalternativ

Skapa en instans av klassen PdfSaveOptions och ange hur teckensnitt ska bäddas in:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

Det här alternativet låter dig inaktivera integrationen av Windows-teckensnitt i den genererade PDF-filen.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av konverteringsalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för Inaktivera bädda in Windows-teckensnitt med Aspose.Words för .NET

Här är den fullständiga källkoden för att inaktivera inbäddning av Windows-teckensnitt i ett PDF-dokument med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	// Utdata-PDF-filen kommer att sparas utan att bädda in vanliga Windows-teckensnitt.
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
Genom att följa dessa steg kan du enkelt inaktivera inbäddningen av Windows-teckensnitt i ett PDF-dokument med Aspose.Words för .NET.

