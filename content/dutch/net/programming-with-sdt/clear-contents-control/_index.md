---
title: Inhoudsbeheer wissen
linktitle: Inhoudsbeheer wissen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de inhoud van een besturingselement in een Word-document wist met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/clear-contents-control/
---

Deze tutorial laat zien hoe u de inhoud van een SDT in een Word-document kunt wissen met Aspose.Words voor .NET. Als u de inhoud van een SDT wist, worden alle tekst of onderliggende knooppunten binnen het inhoudsbesturingselement verwijderd.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar uw document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het document en haal de StructuredDocumentTag op
 Laad het Word-document met behulp van de`Document` constructor, waarbij het pad naar het document als parameter wordt doorgegeven. Haal vervolgens het gewenste op`StructuredDocumentTag` uit het document. In dit voorbeeld gaan we ervan uit dat de SDT het eerste onderliggende knooppunt in het document is.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Stap 3: Wis de inhoud van de StructuredDocumentTag
 Wis de inhoud van de SDT met behulp van de`Clear` methode. Hiermee worden alle tekst- of onderliggende knooppunten binnen het inhoudsbesturingselement verwijderd.

```csharp
sdt.Clear();
```

## Stap 4: Sla het document op
 Sla het gewijzigde document op met behulp van de`Save`methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.ClearContentsControl.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

### Voorbeeldbroncode voor Clear Contents Control met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	sdt.Clear();
	doc.Save(dataDir + "WorkingWithSdt.ClearContentsControl.doc");
```

Dat is het! U hebt de inhoud van een StructuredDocumentTag in uw Word-document met succes gewist met Aspose.Words voor .NET.