---
title: Structured Document Tag Range Starta XML-mappning
linktitle: Structured Document Tag Range Starta XML-mappning
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in XML-mappning för ett strukturerat dokumenttaggintervall med start i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

Den här handledningen förklarar hur du ställer in XML-mappning för ett strukturerat dokumenttaggintervall med start i ett Word-dokument med Aspose.Words för .NET. XML-mappning låter dig visa specifika delar av en XML-datakälla inom innehållskontrollen.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet och skapa XML-del
 Ladda Word-dokumentet med hjälp av`Document` konstruktor, skickar sökvägen till dokumentet som en parameter. Skapa en XML-del som innehåller de data du vill visa i den strukturerade dokumenttaggen.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Steg 3: Ställ in XML-mappning för strukturerad dokumenttagg
Hämta det strukturerade dokumenttaggintervallet från dokumentet. Ställ sedan in XML-mappningen för den strukturerade dokumenttaggen för att visa en specifik del av den anpassade XML-delen med hjälp av ett XPath-uttryck.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Steg 4: Spara dokumentet
 Spara det ändrade dokumentet i den angivna katalogen med hjälp av`Save`metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Exempel på källkod för Structured Document Tag Range Starta Xml-mappning med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Konstruera en XML-del som innehåller data och lägg till den i dokumentets CustomXmlPart-samling.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Skapa en StructuredDocumentTag som visar innehållet i vår CustomXmlPart i dokumentet.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// Om vi ställer in en mappning för vår StructuredDocumentTag,
	// den visar bara en del av CustomXmlPart som XPath pekar på.
	// Denna XPath kommer att peka på innehållets andra "<text>"-element i det första "<root>"-elementet i vår CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

Det är allt! Du har framgångsrikt ställt in XML-mappning för ett strukturerat dokumenttaggintervall i ditt Word-dokument med Aspose.Words för .NET.