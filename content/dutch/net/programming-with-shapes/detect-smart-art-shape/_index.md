---
title: Detecteer slimme kunstvorm
linktitle: Detecteer slimme kunstvorm
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Smart Art-vormen in een Word-document kunt detecteren met Aspose.Words voor .NET, waarmee u grafische representaties kunt identificeren.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/detect-smart-art-shape/
---

In deze zelfstudie wordt uitgelegd hoe u Smart Art-vormen in een Word-document kunt detecteren met behulp van Aspose.Words voor .NET. Smart Art-vormen zijn grafische representaties die worden gebruikt om informatie en ideeën visueel te presenteren.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar uw document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het document
 Laad het Word-document met behulp van de`Document` constructor, waarbij het pad naar het document als parameter wordt doorgegeven.

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## Stap 3: Detecteer slimme kunstvormen
 Herhaal de onderliggende knooppunten van het type`Shape` in het document met behulp van de`GetChildNodes`methode. Controleer of elke vorm Smart Art heeft met behulp van de`HasSmart Art` eigendom.

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## Stap 4: Voer het resultaat uit
Druk het aantal vormen af waarbij Smart Art in het document is gedetecteerd.

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Voorbeeldbroncode voor Detect Smart Art Shape met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

Dat is het! U hebt met succes Smart Art-vormen in uw Word-document gedetecteerd met Aspose.Words voor .NET.