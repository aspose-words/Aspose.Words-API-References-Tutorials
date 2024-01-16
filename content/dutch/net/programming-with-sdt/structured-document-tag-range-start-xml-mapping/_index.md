---
title: Gestructureerd documenttagbereik Start XML-toewijzing
linktitle: Gestructureerd documenttagbereik Start XML-toewijzing
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u XML-toewijzing instelt voor een gestructureerd documenttagbereik in een Word-document met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

In deze zelfstudie wordt uitgelegd hoe u XML-toewijzing instelt voor een gestructureerd documenttagbereik in een Word-document met behulp van Aspose.Words voor .NET. Met XML-toewijzing kunt u specifieke delen van een XML-gegevensbron weergeven binnen het inhoudsbesturingselement.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar uw document zich bevindt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het document en maak een XML-onderdeel
 Laad het Word-document met behulp van de`Document` constructor, waarbij het pad naar het document als parameter wordt doorgegeven. Maak een XML-onderdeel dat de gegevens bevat die u binnen de gestructureerde documenttag wilt weergeven.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Stap 3: Stel XML-toewijzing in voor gestructureerde documenttags
Haal het gestructureerde documenttagbereik op vanaf het document. Stel vervolgens de XML-toewijzing voor de gestructureerde documenttag zo in dat een specifiek deel van het aangepaste XML-deel wordt weergegeven met behulp van een XPath-expressie.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Stap 4: Sla het document op
 Sla het gewijzigde document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Voorbeeldbroncode voor tagbereik voor gestructureerde documenten Start XML-toewijzing met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Construeer een XML-onderdeel dat gegevens bevat en voeg dit toe aan de CustomXmlPart-verzameling van het document.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Maak een StructuredDocumentTag die de inhoud van onze CustomXmlPart in het document weergeeft.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Als we een mapping instellen voor onze StructuredDocumentTag,
	// het geeft alleen een deel van de CustomXmlPart weer waarnaar de XPath verwijst.
	// Deze XPath zal verwijzen naar het tweede "<text>"-element van het eerste "<root>"-element van onze CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Dat is het! U hebt met succes XML-toewijzing ingesteld voor een gestructureerd documenttagbereik in uw Word-document met behulp van Aspose.Words voor .NET.