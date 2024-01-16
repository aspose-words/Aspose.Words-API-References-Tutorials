---
title: Meerdere secties
linktitle: Meerdere secties
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u gestructureerde documenttags met meerdere secties kunt ophalen en verwerken in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/multi-section/
---

In deze zelfstudie wordt uitgelegd hoe u kunt werken met gestructureerde documenttags met meerdere secties in een Word-document met behulp van Aspose.Words voor .NET. U kunt de in het document aanwezige sectietags ophalen en verwerken.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar uw document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het document en haal tags met meerdere secties op
 Laad het Word-document met behulp van de`Document` constructor, waarbij het pad naar het document als parameter wordt doorgegeven. Haal alle startknooppunten van het gestructureerde documenttagbereik in het document op met behulp van de`GetChildNodes` methode.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Stap 3: Verwerk de tags met meerdere secties
Doorloop de verzameling startknooppunten van het gestructureerde documenttagbereik. In dit voorbeeld printen we eenvoudigweg de titel van elke tag naar de console. Op basis van uw wensen kunt u verdere verwerkingen uitvoeren.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Voorbeeldbroncode voor Multi Section met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Dat is het! U hebt met succes gestructureerde documenttags met meerdere secties opgehaald en verwerkt in uw Word-document met Aspose.Words voor .NET.