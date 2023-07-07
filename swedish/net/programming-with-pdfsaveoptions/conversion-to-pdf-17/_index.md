---
title: Konvertera Word-dokument till PDF 1.7
linktitle: Konvertera Word-dokument till PDF 1.7
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du konverterar Word-dokument till PDF 1.7 med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

den här handledningen går vi igenom stegen för hur du konverterar Word-dokument till PDF 1.7 med Aspose.Words för .NET. Genom att konvertera till PDF 1.7 kan du generera PDF-filer som överensstämmer med PDF 1.7-standarden. Följ stegen nedan:

## Steg 1: Ladda dokumentet

Börja med att ladda upp dokumentet du vill konvertera till PDF:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

Var noga med att ange rätt sökväg till ditt dokument.

## Steg 2: Ställ in PDF-konverteringsalternativ

Skapa en instans av klassen PdfSaveOptions och ange versionen av PDF-standarden du vill använda:

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

Detta alternativ säkerställer att den genererade PDF-filen överensstämmer med PDF 1.7-standarden.

## Steg 3: Konvertera dokument till PDF

 Använd`Save` metod för att konvertera dokumentet till PDF med angivande av konverteringsalternativ:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

Se till att ange rätt sökväg för att spara den konverterade PDF-filen.

### Exempel på källkod för konvertering till pdf 17 med Aspose.Words för .NET

Här är den fullständiga källkoden för att konvertera till PDF 1.7 med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

Genom att följa dessa steg kan du enkelt konvertera till PDF 1.7 med Aspose.Words för .NET.


## Slutsats

den här handledningen har vi förklarat hur man konverterar ett Word-dokument till PDF 1.7 med Aspose.Words för .NET. Genom att följa stegen som beskrivs kan du enkelt generera PDF-filer som överensstämmer med PDF 1.7-standarden. Var noga med att ange rätt sökväg till ditt Word-dokument och konfigurera alternativen för konvertering till PDF efter behov. Konvertering till PDF 1.7 säkerställer optimal kompatibilitet och läsbarhet på olika plattformar.

### Vanliga frågor

#### F: Vad är Word till PDF 1.7-konvertering?
S: Att konvertera Word-dokument till PDF 1.7 är att generera PDF-filer som överensstämmer med PDF 1.7-standarden. Denna standard specificerar funktioner och krav för PDF-filer, vilket möjliggör optimal kompatibilitet och läsbarhet på olika plattformar.

#### F: Hur kan jag konvertera ett Word-dokument till PDF 1.7 med Aspose.Words för .NET?
S: För att konvertera ett Word-dokument till PDF 1.7 med Aspose.Words för .NET, följ dessa steg:

 Ställ in katalogsökvägen där dina dokument finns genom att ersätta`"YOUR DOCUMENTS DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

 Ladda Word-dokumentet du vill konvertera till PDF med hjälp av`Document` klass och ange sökvägen till Word-dokumentet i den angivna dokumentkatalogen.

 Konfigurera konverteringen som PDF-alternativ genom att skapa en instans av`PdfSaveOptions`klass och ange vilken version av PDF-standarden du vill använda med hjälp av`Compliance` fastighet med värdet`PdfCompliance. Pdf17` för att generera en PDF-fil som överensstämmer med PDF 1.7-standarden.

 Spara dokumentet i PDF-format med hjälp av`Save` metod för`Document`klass som anger sökvägen och sparalternativ.

#### F: Vilka är fördelarna med att konvertera till PDF 1.7 med Aspose.Words för .NET?
S: Fördelarna med att konvertera till PDF 1.7 med Aspose.Words för .NET är:

PDF 1.7-kompatibel: Konvertering till PDF 1.7 säkerställer att den genererade PDF-filen är PDF 1.7-kompatibel, vilket säkerställer kompatibilitet och läsbarhet på olika plattformar.

Bevarande av dokumentformatering: Aspose.Words för .NET säkerställer korrekt Word-dokumentkonvertering genom att bevara formatering, bilder och stilar, vilket resulterar i en sann-till-original PDF-fil.