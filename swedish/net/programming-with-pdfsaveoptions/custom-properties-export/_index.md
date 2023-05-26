---
title: Export av anpassade egenskaper
linktitle: Export av anpassade egenskaper
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du exporterar anpassade egenskaper när du konverterar dokument till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/custom-properties-export/
---

I den här handledningen går vi igenom stegen för att exportera ett dokuments anpassade egenskaper med Aspose.Words för .NET. Genom att exportera anpassade egenskaper kan du inkludera ytterligare information i det genererade PDF-dokumentet. Följ stegen nedan:

## Steg 1: Skapa ett dokument och lägga till anpassade egenskaper

Börja med att skapa en instans av klassen Document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Steg 2: Lägg till anpassade egenskaper
Lägg sedan till önskade anpassade egenskaper. Till exempel, för att lägga till en "Company"-egenskap med värdet "Aspose", använd`Add` metod för CustomDocumentProperties-samlingen:

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

Du kan lägga till så många anpassade egenskaper som behövs.

## Steg 3: Ställ in alternativ för PDF-export

Skapa en instans av klassen PdfSaveOptions och ange hur anpassade egenskaper exporteras:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

Det här alternativet styr exporten av anpassade egenskaper vid konvertering till PDF.

## Steg 4: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av konverteringsalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för export av anpassade egenskaper med Aspose.Words för .NET

Här är den fullständiga källkoden för att exportera anpassade egenskaper från ett dokument med Aspose.Words för .NET:


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

Genom att följa dessa steg kan du enkelt exportera anpassade egenskaper för ett dokument när du konverterar till PDF med Aspose.Words för .NET.

