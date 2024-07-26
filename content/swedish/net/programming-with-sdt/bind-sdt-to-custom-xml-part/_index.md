---
title: Bind SDT till anpassad XML-del
linktitle: Bind SDT till anpassad XML-del
second_title: Aspose.Words Document Processing API
description: Lär dig hur du binder en SDT till en anpassad XML-del med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

Den här handledningen visar hur man binder en SDT (Structured Document Tag) till en anpassad XML-del med Aspose.Words för .NET. Med SDT:er kan du lägga till strukturerade innehållskontroller i ett Word-dokument, och CustomXmlParts tillhandahåller ett sätt att lagra anpassade XML-data som är associerade med dokumentet.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och XML.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett dokument och CustomXmlPart
 Skapa en ny instans av`Document` klass och a`CustomXmlPart` för att lagra anpassade XML-data. Den anpassade XML-filen ska vara i ett giltigt XML-format. I det här exemplet använder vi en enkel XML-sträng`<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Steg 3: Lägg till en StructuredDocumentTag (SDT) till dokumentet
 Lägg till en`StructuredDocumentTag`till dokumentet för att fungera som innehållskontroll. Specificera`SdtType` som`PlainText` och den`MarkupLevel` som`Block` för att skapa en SDT på blocknivå.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Steg 4: Ställ in XML-mappningen för SDT
 Kartlägg SDT till`CustomXmlPart` genom att använda`SetMapping` metod för`XmlMapping` fast egendom. Specificera`CustomXmlPart` , XPath-uttrycket för att lokalisera den önskade XML-noden och namnområdesprefixet om det behövs. I det här exemplet mappar vi SDT till`/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Steg 5: Spara dokumentet
 Spara det ändrade dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Exempel på källkod för Bind Sd Tto Custom Xml Part med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

Det är allt! Du har framgångsrikt bundit en SDT till en CustomXmlPart i ditt Word-dokument med Aspose.Words för .NET.