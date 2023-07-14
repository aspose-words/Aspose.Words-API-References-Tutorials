---
title: Bildförhållande låst
linktitle: Bildförhållande låst
second_title: Aspose.Words Document Processing API
description: Lär dig hur du låser eller låser upp bildförhållandet för en form i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-shapes/aspect-ratio-locked/
---

Den här handledningen förklarar hur du låser eller låser upp bildförhållandet för en form i ett Word-dokument med Aspose.Words för .NET. Genom att låsa bildförhållandet kan du behålla formens ursprungliga proportioner när du ändrar storlek på den.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett nytt dokument och DocumentBuilder
 Skapa en ny instans av`Document` klass och a`DocumentBuilder` objekt för att arbeta med dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga en bildform
 Använd`InsertImage` metod för`DocumentBuilder` objekt för att infoga en bildform i dokumentet. Ange sökvägen till bildfilen som en parameter.

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Steg 4: Lås eller lås upp bildförhållandet
 Ställ in`AspectRatioLocked` formens egenskap till`true` eller`false` för att låsa respektive låsa upp bildförhållandet.

```csharp
shape.AspectRatioLocked = false; //Lås upp bildförhållandet
```

## Steg 5: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithShapes.AspectRatioLocked.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Exempel på källkod för Aspect Ratio Locked med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

Det är allt! Du har framgångsrikt låst eller låst upp bildförhållandet för en form i ditt Word-dokument med Aspose.Words för .NET.