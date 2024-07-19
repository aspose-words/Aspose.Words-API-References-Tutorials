---
title: Update Smart Art-tekening
linktitle: Update Smart Art-tekening
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de Smart Art-tekening in een Word-document kunt bijwerken met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/update-smart-art-drawing/
---

In deze tutorial wordt uitgelegd hoe u de Smart Art-tekening in een Word-document kunt bijwerken met Aspose.Words voor .NET. Door de vormen in het document te doorlopen en te controleren of ze Smart Art hebben, kunt u de Smart Art-tekening bijwerken om eventuele wijzigingen in de gegevens weer te geven.

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
 Laad het Word-document dat de Smart Art-tekening bevat met behulp van de`Document` klasse constructeur.

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## Stap 3: Update de Smart Art-tekening
 Doorloop de vormen in het document met behulp van de`GetChildNodes` methode met de`NodeType.Shape` parameter. Controleer of elke vorm Smart Art heeft met behulp van de`HasSmartArt` eigendom, en indien waar, bel dan de`UpdateSmartArtDrawing` methode om de Smart Art-tekening bij te werken.

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Voorbeeldbroncode voor het bijwerken van Smart Art Drawing met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

Dat is het! U hebt de Smart Art-tekening in uw Word-document met succes bijgewerkt met Aspose.Words voor .NET.