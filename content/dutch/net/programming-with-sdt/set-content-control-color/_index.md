---
title: Stel de kleur van het inhoudsbeheer in
linktitle: Stel de kleur van het inhoudsbeheer in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de kleur van een inhoudsbesturingselement in een Word-document instelt met Aspose.Words voor .NET, en hoe u het uiterlijk ervan aanpast.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/set-content-control-color/
---

In deze zelfstudie wordt uitgelegd hoe u de kleur van een inhoudsbesturingselement in een Word-document instelt met behulp van Aspose.Words voor .NET. U kunt het uiterlijk van inhoudsbesturingselementen aanpassen door de kleur ervan te wijzigen.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar uw document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het document en haal het inhoudsbeheer op
 Laad het Word-document met behulp van de`Document`constructor, waarbij het pad naar het document als parameter wordt doorgegeven. Haal het gewenste inhoudsbeheer uit het document op. In dit voorbeeld gaan we ervan uit dat het inhoudsbesturingselement de eerste gestructureerde documenttag in het document is.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Stap 3: Stel de kleur van het inhoudsbeheer in
 Stel de kleur van het inhoudsbesturingselement in door a toe te wijzen`Color` waarde aan de`Color` eigenschap van de gestructureerde documenttag. In dit voorbeeld stellen we de kleur in op rood.

```csharp
sdt.Color = Color.Red;
```

## Stap 4: Sla het document op
 Sla het gewijzigde document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.SetContentControlColor.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

### Voorbeeldbroncode voor Set Content Control Color met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Color = Color.Red;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlColor.docx");
```

Dat is het! U hebt met succes de kleur van een inhoudsbesturingselement in uw Word-document ingesteld met Aspose.Words voor .NET.