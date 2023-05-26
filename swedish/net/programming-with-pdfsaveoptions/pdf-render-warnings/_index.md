---
title: Pdf-rendering varningar
linktitle: Pdf-rendering varningar
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att hantera PDF-renderingsvarningar med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-pdfsaveoptions/pdf-render-warnings/
---

Den här artikeln ger en steg-för-steg-guide om hur du använder funktionen för varningar för PDF-rendering med Aspose.Words för .NET. Vi kommer att förklara varje del av koden i detalj. I slutet av denna handledning kommer du att kunna förstå hur du hanterar rendering av varningar när du konverterar till PDF.

Innan du börjar, se till att du har installerat och konfigurerat Aspose.Words for .NET-biblioteket i ditt projekt. Du hittar biblioteket och installationsinstruktioner på Asposes webbplats.

## Steg 1: Definiera dokumentkatalogen

 För att börja måste du definiera sökvägen till katalogen där dina dokument finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda upp dokumentet

Därefter måste vi ladda dokumentet vi vill bearbeta. I det här exemplet antar vi att dokumentet heter "WMF med image.docx" och finns i den angivna dokumentkatalogen.

```csharp
Document doc = new Document(dataDir + "WMF with image.docx");
```

## Steg 3: Konfigurera spara som PDF-alternativ med renderingsvarningar

För att hantera renderingsvarningar vid konvertering till PDF måste vi konfigurera`MetafileRenderingOptions` objekt för att specificera hur metafiler renderas. Vi använder också`HandleDocumentWarnings` möjlighet att hantera de varningar som genereras när dokumentet sparas.

```csharp
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
     EmulateRasterOperations = false,
     RenderingMode = MetafileRenderingMode.VectorWithFallback
};

PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
```

## Steg 4: Spara dokument som PDF med renderingsvarningar

Slutligen kan vi spara dokumentet i PDF-format med hjälp av de sparade alternativen som konfigurerats tidigare.

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);
```

## Steg 5: Hantera återgivningsvarningar

Återgivningsvarningar som genereras när dokumentet sparas kan hämtas med den anpassade varningshanteraren. I det här exemplet skriver vi helt enkelt ut beskrivningen av varje varning.

```csharp
foreach(WarningInfo warningInfo in callback.mWarnings)
{
     Console.WriteLine(warningInfo.Description);
}
```

Det är allt ! Du har lyckats hantera rendering av varningar vid konvertering av ett dokument

  till PDF med Aspose.Words för .NET.

### Exempel på källkod för varningar för PDF-rendering med Aspose.Words för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "WMF with image.docx");

	MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
	{
		EmulateRasterOperations = false, RenderingMode = MetafileRenderingMode.VectorWithFallback
	};

	PdfSaveOptions saveOptions = new PdfSaveOptions { MetafileRenderingOptions = metafileRenderingOptions };

	// Om Aspose.Words inte kan rendera några av metafilposterna korrekt
	// till vektorgrafik sedan renderar Aspose.Words denna metafil till en bitmapp.
	HandleDocumentWarnings callback = new HandleDocumentWarnings();
	doc.WarningCallback = callback;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfRenderWarnings.pdf", saveOptions);

	// Även om filen sparas framgångsrikt, samlas renderingsvarningar som inträffade under sparandet här.
	foreach (WarningInfo warningInfo in callback.mWarnings)
	{
		Console.WriteLine(warningInfo.Description);
	}
        
```
