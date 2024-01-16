---
title: Tabelherhalende sectie maken, toegewezen aan aangepast XML-onderdeel
linktitle: Tabelherhalende sectie maken, toegewezen aan aangepast XML-onderdeel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel kunt maken met een herhalende sectie die is toegewezen aan een CustomXmlPart in een Word-document met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

In deze zelfstudie wordt gedemonstreerd hoe u met Aspose.Words voor .NET een tabel kunt maken met een herhalende sectie die is toegewezen aan een aangepast XML-onderdeel in een Word-document. Met de herhalende sectie kunt u dynamisch rijen toevoegen op basis van de XML-gegevens die zijn opgeslagen in het aangepaste XML-onderdeel.

## Vereisten
Om deze tutorial te volgen, heb je het volgende nodig:

- Aspose.Words voor .NET-bibliotheek geïnstalleerd.
- Basiskennis van C# en woordenverwerking met Word-documenten.

## Stap 1: Stel de documentmap in
 Begin met het instellen van het pad naar uw documentmap. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar de map waar u het document wilt opslaan.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een document en DocumentBuilder
 Maak een nieuw exemplaar van de`Document` klasse en een`DocumentBuilder` om de inhoud van het document op te bouwen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Voeg aangepaste XML-gegevens toe aan een CustomXmlPart
 Maak een`CustomXmlPart` en voeg er aangepaste XML-gegevens aan toe. In dit voorbeeld maken we een XML-tekenreeks die een verzameling boeken vertegenwoordigt, met hun titels en auteurs.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Stap 4: Maak een tabel en tabelstructuur
 Begin met het maken van een tabel met behulp van de`StartTable` werkwijze van de`DocumentBuilder` . Voeg tabelcellen en inhoud toe met behulp van de`InsertCell` En`Write` methoden.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Stap 5: Maak de herhalende sectie die is toegewezen aan aangepaste XML
 Maak een`StructuredDocumentTag` met`SdtType.RepeatingSection` om het herhalende gedeelte weer te geven. Stel de XML-toewijzing voor de herhalende sectie in met behulp van de`SetMapping` werkwijze van de`XmlMapping` eigendom. In dit voorbeeld wijzen we de herhalende sectie toe aan`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Stap 6: Maak het herhalende sectie-item en voeg cellen toe
 Maak een`StructuredDocumentTag` met`SdtType.RepeatingSectionItem` om het herhalende sectie-item weer te geven. Voeg het als kind toe aan het herhalende gedeelte.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Maak een`Row`om elk item in de herhalende sectie weer te geven en toe te voegen aan het herhalende sectie-item.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Stap 7: Voeg inhoudsbesturingselementen toe in de herhalende sectie
 Creëren`StructuredDocumentTag` voorwerpen mee`SdtType.PlainText`

  om de titel- en auteursinhoudsregelaars weer te geven. Stel de XML-toewijzing voor elk inhoudsbesturingselement in met behulp van de`SetMapping` werkwijze van de`XmlMapping` eigendom. In dit voorbeeld wijzen we het titelbesturingselement toe aan`/books[1]/book[1]/title[1]` en de controle van de auteur`/books[1]/book[1]/author[1]`.

```csharp
StructuredDocumentTag titleSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.AppendChild(titleSdt);

StructuredDocumentTag authorSdt =
	new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.AppendChild(authorSdt);
```

## Stap 8: Bewaar het document
 Sla het gewijzigde document op in de opgegeven map met behulp van de`Save` methode. Geef de gewenste bestandsnaam op met de juiste bestandsextensie. In dit voorbeeld slaan we het document op als "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Voorbeeldbroncode voor het maken van een herhalende tabelsectie toegewezen aan een aangepast XML-onderdeel met behulp van Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Title");
	builder.InsertCell();
	builder.Write("Author");
	builder.EndRow();
	builder.EndTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
	repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
	table.AppendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
	repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.AppendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	titleSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.AppendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Cell);
	authorSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.AppendChild(authorSdt);
	doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");

```

Dat is het! U hebt met succes een tabel gemaakt met een herhalende sectie die is toegewezen aan een CustomXmlPart in uw Word-document met behulp van Aspose.Words voor .NET.