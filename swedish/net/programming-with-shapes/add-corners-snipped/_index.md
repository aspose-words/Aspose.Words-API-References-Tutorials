---
title: Lägg till hörn avklippta
linktitle: Lägg till hörn avklippta
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du lägger till en form med hörn avklippta i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-shapes/add-corners-snipped/
---

 Denna handledning förklarar hur man lägger till en form med hörn avklippta i ett Word-dokument med Aspose.Words för .NET. De hörnklippta formerna kan anpassas och infogas med hjälp av`InsertShape` metod.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och att arbeta med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"`med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett nytt dokument och DocumentBuilder
 Skapa en ny instans av`Document` klass och a`DocumentBuilder` objekt för att arbeta med dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Sätt in den avskurna hörnen
 Använd`InsertShape` metod för`DocumentBuilder` objekt för att infoga en form med hörn avklippta. Ange formtypen (i det här fallet,`ShapeType.TopCornersSnipped`) och ange önskad storlek för formen.

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## Steg 4: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithShapes.AddCornersSnipped.docx".

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Exempel på källkod för Add Corners Snipped med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

Det är allt! Du har framgångsrikt lagt till en form av klippt hörn till ditt Word-dokument med Aspose.Words för .NET.