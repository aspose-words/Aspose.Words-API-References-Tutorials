---
title: Nedsampling av bilder
linktitle: Nedsampling av bilder
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du minskar bildupplösningen när du konverterar till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/downsampling-images/
---

I den här handledningen går vi igenom stegen för att minska bildupplösningen när du konverterar till PDF med Aspose.Words för .NET. Detta minskar storleken på den genererade PDF-filen. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt dokument.

## Steg 2: Konfigurera PDF-sparalternativ

Skapa en instans av klassen PdfSaveOptions och ställ in alternativen för nedskalning av bilden:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

 De`Resolution` egenskapen anger målupplösningen för bilderna och`ResolutionThreshold` egenskapen anger den lägsta upplösningen under vilken bilderna inte kommer att skalas ned.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av sparalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för nedsampling av bilder med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//Vi kan ställa in en lägsta tröskel för nedsampling.
	// Detta värde förhindrar att den andra bilden i inmatningsdokumentet nedsamplas.
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

Genom att följa dessa steg kan du enkelt minska bildupplösningen när du konverterar till PDF med Aspose.Words för .NET.


