---
title: Exportera anpassade egenskaper i ett PDF-dokument
linktitle: Exportera anpassade egenskaper i ett PDF-dokument
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du exporterar anpassade egenskaper när du konverterar dokument till PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/custom-properties-export/
---

den här handledningen går vi igenom stegen för att exportera ett dokuments anpassade egenskaper i ett PDF-dokument med Aspose.Words för .NET. Genom att exportera anpassade egenskaper kan du inkludera ytterligare information i det genererade PDF-dokumentet. Följ stegen nedan:

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


## Slutsats

I den här handledningen förklarade vi hur man exporterar anpassade egenskaper från ett dokument till ett PDF-dokument med Aspose.Words för .NET. Genom att följa stegen som beskrivs kan du enkelt inkludera ytterligare information i det genererade PDF-dokumentet genom att exportera dokumentets anpassade egenskaper. Dra nytta av funktionerna i Aspose.Words för .NET för att anpassa och berika dina PDF-dokument genom att exportera anpassade egenskaper.

### Vanliga frågor

#### F: Vad är att exportera anpassade egenskaper till ett PDF-dokument?
S: Genom att exportera anpassade egenskaper till ett PDF-dokument kan ytterligare information inkluderas i det genererade PDF-dokumentet. Anpassade egenskaper är metadata som är specifik för ditt dokument, till exempel taggar, nyckelord eller autentiseringsuppgifter. Genom att exportera dessa anpassade egenskaper kan du göra dem tillgängliga för användare när de visar PDF-dokumentet.

#### F: Hur kan jag exportera ett dokuments anpassade egenskaper till ett PDF-dokument med Aspose.Words för .NET?
S: För att exportera ett dokuments anpassade egenskaper till ett PDF-dokument med Aspose.Words för .NET, följ dessa steg:

 Skapa en instans av`Document` klass.

 Lägg till önskade anpassade egenskaper med hjälp av`CustomDocumentProperties` samling. Använd till exempel`Add` metod för att lägga till en "Company"-egenskap med värdet "Aspose".

 Skapa en instans av`PdfSaveOptions` klass och ange hur man exporterar anpassade egenskaper med hjälp av`CustomPropertiesExport` fast egendom. De`PdfCustomPropertiesExport.Standard` värde exporterar anpassade egenskaper enligt standardinställningar.

 Använd`Save` metod för`Document` klass för att konvertera dokumentet till PDF och ange konverteringsalternativen.

#### F: Hur kommer jag åt anpassade egenskaper för ett PDF-dokument?
S: För att komma åt de anpassade egenskaperna för ett PDF-dokument kan du använda en kompatibel PDF-läsare som stöder visning av dokumentegenskaper. De vanligaste PDF-läsarna, som Adobe Acrobat Reader, ger tillgång till metadata och egenskaper för ett PDF-dokument. Du kan vanligtvis hitta dessa alternativ under "Arkiv"-menyn eller genom att högerklicka på dokumentet och välja "Egenskaper".