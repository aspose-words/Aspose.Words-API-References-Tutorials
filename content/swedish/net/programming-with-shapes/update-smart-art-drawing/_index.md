---
title: Uppdatera Smart Art Drawing
linktitle: Uppdatera Smart Art Drawing
second_title: Aspose.Words Document Processing API
description: Lär dig hur du uppdaterar Smart Art-ritningen i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-shapes/update-smart-art-drawing/
---

Denna handledning förklarar hur du uppdaterar Smart Art-ritningen i ett Word-dokument med Aspose.Words för .NET. Genom att iterera genom formerna i dokumentet och kontrollera om de har Smart Art, kan du uppdatera Smart Art-ritningen för att återspegla eventuella ändringar som gjorts i dess data.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet
 Ladda Word-dokumentet som innehåller Smart Art-ritningen med hjälp av`Document` klass konstruktör.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Steg 3: Uppdatera den smarta konstritningen
 Iterera genom formerna i dokumentet med hjälp av`GetChildNodes` metod med`NodeType.Shape` parameter. Kontrollera om varje form har Smart Art med hjälp av`HasSmartArt` egendom, och om det är sant, ring till`UpdateSmartArtDrawing` metod för att uppdatera Smart Art-ritningen.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Exempel på källkod för Update Smart Art Drawing med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Det är allt! Du har framgångsrikt uppdaterat Smart Art-ritningen i ditt Word-dokument med Aspose.Words för .NET.