---
title: Vertikalt ankare
linktitle: Vertikalt ankare
second_title: Aspose.Words Document Processing API
description: Lär dig hur du placerar en form vertikalt i ett dokument med den vertikala ankarfunktionen i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-shapes/vertical-anchor/
---

Denna handledning förklarar hur du använder den vertikala ankarfunktionen i Aspose.Words för .NET för att placera en form vertikalt i ett dokument. Genom att ställa in den vertikala ankaregenskapen för en form kan du kontrollera dess vertikala justering i förhållande till texten eller sidan.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

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

## Steg 3: Infoga och konfigurera en form
 Infoga en form i dokumentet med hjälp av`InsertShape` metod för`DocumentBuilder` objekt. Ställ in önskade dimensioner för formen.

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## Steg 4: Ställ in det vertikala ankaret
Ställ in den vertikala ankaregenskapen för formen för att kontrollera dess vertikala justering. I det här exemplet ställer vi in den på "Bottom" för att förankra formen längst ner på texten eller sidan.

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## Steg 5: Lägg till innehåll i formen
 Använd`MoveTo` metod för`DocumentBuilder` objekt för att flytta markören till formens första stycke. Använd sedan`Write` metod för att lägga till innehåll i formen.

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## Steg 6: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save`metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithShapes.VerticalAnchor.docx".

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Exempel på källkod för Vertical Anchor med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

Det är allt! Du har framgångsrikt använt den vertikala ankarfunktionen i Aspose.Words för .NET för att placera en form vertikalt i ett dokument.