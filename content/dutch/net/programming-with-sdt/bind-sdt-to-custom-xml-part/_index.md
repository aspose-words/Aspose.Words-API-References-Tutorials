---
title: Bind SDT aan een aangepast XML-onderdeel
linktitle: Bind SDT aan een aangepast XML-onderdeel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een SDT aan een aangepast XML-onderdeel koppelt met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

In deze zelfstudie wordt gedemonstreerd hoe u een Structured Document Tag (SDT) koppelt aan een aangepast XML-onderdeel met behulp van Aspose.Words voor .NET. Met SDT's kunt u gestructureerde inhoudsbesturingselementen toevoegen aan een Word-document, en CustomXmlParts bieden een manier om aangepaste XML-gegevens op te slaan die aan het document zijn gekoppeld.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en XML.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een document en CustomXmlPart
 Maak een nieuw exemplaar van de`Document` klasse en een`CustomXmlPart` om de aangepaste XML-gegevens op te slaan. De aangepaste XML moet een geldig XML-formaat hebben. In dit voorbeeld gebruiken we een eenvoudige XML-tekenreeks`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Stap 3: Voeg een StructuredDocumentTag (SDT) toe aan het document
 Voeg een ... toe`StructuredDocumentTag` naar het document om als inhoudscontrole te dienen. Specificeer de`SdtType` als`PlainText` en de`MarkupLevel` als`Block` om een SDT op blokniveau te maken.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Stap 4: Stel de XML-toewijzing voor de SDT in
 Wijs de SDT toe aan de`CustomXmlPart` door gebruik te maken van de`SetMapping` werkwijze van de`XmlMapping` eigendom. Specificeer de`CustomXmlPart` , de XPath-expressie om het gewenste XML-knooppunt te lokaliseren, en indien nodig het naamruimtevoorvoegsel. In dit voorbeeld wijzen we de SDT toe aan`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Stap 5: Sla het document op
 Sla het gewijzigde document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Voorbeeldbroncode voor Bind Sd Tto Custom XML Part met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Dat is het! U hebt met succes een SDT aan een CustomXmlPart in uw Word-document gebonden met behulp van Aspose.Words voor .NET.