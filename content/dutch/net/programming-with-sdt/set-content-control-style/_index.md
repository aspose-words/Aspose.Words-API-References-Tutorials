---
title: Stel de stijl voor inhoudscontrole in
linktitle: Stel de stijl voor inhoudscontrole in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de stijl van een inhoudsbesturingselement in een Word-document instelt met Aspose.Words voor .NET, waarbij u consistente opmaak toepast.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/set-content-control-style/
---

In deze zelfstudie wordt uitgelegd hoe u de stijl van een inhoudsbesturingselement in een Word-document instelt met behulp van Aspose.Words voor .NET. U kunt vooraf gedefinieerde of aangepaste stijlen toepassen op inhoudsbesturingselementen voor een consistente opmaak.

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
 Laad het Word-document met behulp van de`Document` constructor, waarbij het pad naar het document als parameter wordt doorgegeven. Haal het gewenste inhoudsbeheer uit het document op. In dit voorbeeld gaan we ervan uit dat het inhoudsbesturingselement de eerste gestructureerde documenttag in het document is.

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## Stap 3: Haal de stijl op en pas deze toe op Content Control
 Haal de gewenste stijl op uit de stijlencollectie van het document. In dit voorbeeld halen we de stijl 'Quote' op met behulp van`StyleIdentifier.Quote` . Wijs vervolgens de opgehaalde stijl toe aan de`Style` eigenschap van de gestructureerde documenttag.

```csharp
Style style = doc.Styles[StyleIdentifier.Quote];
sdt.Style = style;
```

## Stap 4: Sla het document op
 Sla het gewijzigde document op in de opgegeven map met behulp van de`Save`methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.SetContentControlStyle.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

### Voorbeeldbroncode voor Set Content Control Style met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	Style style = doc.Styles[StyleIdentifier.Quote];
	sdt.Style = style;
	doc.Save(dataDir + "WorkingWithSdt.SetContentControlStyle.docx");
```

Dat is het! U hebt met succes de stijl van een inhoudsbesturingselement in uw Word-document ingesteld met Aspose.Words voor .NET.