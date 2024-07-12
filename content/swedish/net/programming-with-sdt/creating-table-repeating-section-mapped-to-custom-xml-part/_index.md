---
title: Skapa tabellupprepande avsnitt mappas till anpassad XML-del
linktitle: Skapa tabellupprepande avsnitt mappas till anpassad XML-del
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar en tabell med ett upprepande avsnitt mappat till en CustomXmlPart i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/creating-table-repeating-section-mapped-to-custom-xml-part/
---

Denna handledning visar hur man skapar en tabell med ett upprepande avsnitt mappat till en anpassad XML-del i ett Word-dokument med Aspose.Words för .NET. Den upprepande sektionen låter dig lägga till rader dynamiskt baserat på XML-data som lagras i den anpassade XML-delen.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"`med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa en Document and DocumentBuilder
 Skapa en ny instans av`Document` klass och a`DocumentBuilder` att bygga dokumentets innehåll.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Lägg till anpassade XML-data till en CustomXmlPart
 Skapa en`CustomXmlPart` och lägg till anpassade XML-data till den. I det här exemplet skapar vi en XML-sträng som representerar en samling böcker med deras titlar och författare.

```csharp
CustomXmlPart xmlPart = doc.CustomXmlParts.Add("Books",
	"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
	"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
	"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
```

## Steg 4: Skapa en tabell- och tabellstruktur
 Börja skapa en tabell med hjälp av`StartTable` metod för`DocumentBuilder` . Lägg till tabellceller och innehåll med hjälp av`InsertCell`och`Write` metoder.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
builder.Write("Title");
builder.InsertCell();
builder.Write("Author");
builder.EndRow();
builder.EndTable();
```

## Steg 5: Skapa det upprepande avsnittet mappat till anpassad XML
 Skapa en`StructuredDocumentTag` med`SdtType.RepeatingSection` för att representera det upprepade avsnittet. Ställ in XML-mappningen för den upprepande sektionen med hjälp av`SetMapping` metod för`XmlMapping` fast egendom. I det här exemplet mappar vi den repeterande sektionen till`/books[1]/book`.

```csharp
StructuredDocumentTag repeatingSectionSdt =
	new StructuredDocumentTag(doc, SdtType.RepeatingSection, MarkupLevel.Row);
repeatingSectionSdt.XmlMapping.SetMapping(xmlPart, "/books[1]/book", "");
table.AppendChild(repeatingSectionSdt);
```

## Steg 6: Skapa det upprepade avsnittet och lägg till celler
 Skapa en`StructuredDocumentTag` med`SdtType.RepeatingSectionItem` för att representera det upprepade avsnittet. Lägg till det som barn till det upprepande avsnittet.

```csharp
StructuredDocumentTag repeatingSectionItemSdt = 
	new StructuredDocumentTag(doc, SdtType.RepeatingSectionItem, MarkupLevel.Row);
repeatingSectionSdt.AppendChild(repeatingSectionItemSdt);
```

 Skapa en`Row` för att representera varje objekt i det upprepade avsnittet och lägga till det till det upprepade avsnittet.

```csharp
Row row = new Row(doc);
repeatingSectionItemSdt.AppendChild(row);
```

## Steg 7: Lägg till innehållskontroller i det upprepade avsnittet
 Skapa`StructuredDocumentTag` föremål med`SdtType.PlainText`

  för att representera kontrollerna för titeln och författarens innehåll. Ställ in XML-mappningen för varje innehållskontroll med hjälp av`SetMapping` metod för`XmlMapping` fast egendom. I det här exemplet mappar vi titelkontrollen till`/books[1]/book[1]/title[1]` och författaren kontroll till`/books[1]/book[1]/author[1]`.

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

## Steg 8: Spara dokumentet
 Spara det ändrade dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
```

### Exempel på källkod för att skapa tabellupprepande avsnitt mappad till anpassad XML-del med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
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

Det är allt! Du har framgångsrikt skapat en tabell med ett upprepande avsnitt mappat till en CustomXmlPart i ditt Word-dokument med Aspose.Words för .NET.