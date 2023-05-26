---
title: Bildkomprimering
linktitle: Bildkomprimering
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide till komprimering av bilder med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/image-compression/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder bildkomprimeringsfunktionen med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du komprimerar bilder i ett dokument och genererar en PDF med korrekt bildkomprimering.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda upp dokumentet

Därefter måste vi ladda dokumentet vi vill bearbeta. I det här exemplet antar vi att dokumentet heter "Rendering.docx" och finns i den angivna dokumentkatalogen.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Steg 3: Konfigurera spara som PDF-alternativ med bildkomprimering

 För att komprimera bilder vid konvertering till PDF måste vi konfigurera`PdfSaveOptions` objekt. Vi kan ställa in bildkomprimeringstyp, JPEG-kvalitet och andra PDF-kompatibilitetsalternativ om det behövs.

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## Steg 4: Spara dokument som PDF med bildkomprimering

Slutligen kan vi spara dokumentet i PDF-format med hjälp av de sparade alternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## Steg 5: Konfigurera alternativ för att spara till PDF/A-2u med bildkomprimering

Om du vill generera PDF/A-2u-kompatibel PDF med bildkomprimering kan du konfigurera de ytterligare sparalternativen.

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, // Använd JPEG-komprimering med 50 % kvalitet för att minska filstorleken.
};
```

## Steg 6: Spara dokumentet som PDF/A-2u med bildkomprimering

Spara dokumentet i PDF/A-2u-format med hjälp av de extra sparalternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



Det är allt ! Du har framgångsrikt komprimerat bilderna i ett dokument och skapat en PDF med korrekt bildkomprimering med Aspose.Words för .NET.

### Exempel på källkod för att komprimera bilder med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, // Använd JPEG-komprimering med 50 % kvalitet för att minska filstorleken.
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```
