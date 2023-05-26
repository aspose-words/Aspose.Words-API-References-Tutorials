---
title: Upptäck Smart Art Shape
linktitle: Upptäck Smart Art Shape
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du upptäcker Smart Art-former i ett Word-dokument med Aspose.Words för .NET, som identifierar grafiska representationer.
type: docs
weight: 10
url: /sv/net/programming-with-shapes/detect-smart-art-shape/
---

Denna handledning förklarar hur du upptäcker Smart Art-former i ett Word-dokument med Aspose.Words för .NET. Smart Art-former är grafiska representationer som används för att visuellt presentera information och idéer.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och att arbeta med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet
 Ladda Word-dokumentet med hjälp av`Document` konstruktor, skickar sökvägen till dokumentet som en parameter.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Steg 3: Upptäck smarta konstformer
Iterera genom de underordnade noderna av typen`Shape` i dokumentet med hjälp av`GetChildNodes` metod. Kontrollera om varje form har Smart Art med hjälp av`HasSmart Art` fast egendom.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Steg 4: Mata ut resultatet
Skriv ut antalet former med Smart Art som upptäckts i dokumentet.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Exempel på källkod för Detect Smart Art Shape med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Det är allt! Du har framgångsrikt upptäckt Smart Art-former i ditt Word-dokument med Aspose.Words för .NET.