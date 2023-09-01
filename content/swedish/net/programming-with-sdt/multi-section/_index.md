---
title: Flersektion
linktitle: Flersektion
second_title: Aspose.Words Document Processing API
description: Lär dig hur du hämtar och bearbetar strukturerade dokumenttaggar i flera sektioner i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-sdt/multi-section/
---

Den här handledningen förklarar hur man arbetar med strukturerade dokumenttaggar i flera sektioner i ett Word-dokument med Aspose.Words för .NET. Du kan hämta och bearbeta sektionstaggarna som finns i dokumentet.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där ditt dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet och hämta taggar med flera sektioner
 Ladda Word-dokumentet med hjälp av`Document` konstruktor, skickar sökvägen till dokumentet som en parameter. Hämta alla startnoder för strukturerat dokumenttaggintervall i dokumentet med hjälp av`GetChildNodes` metod.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
```

## Steg 3: Bearbeta flersektionstaggarna
Iterera genom samlingen av strukturerade dokumenttaggintervallstartnoder. I det här exemplet skriver vi helt enkelt ut titeln på varje tagg till konsolen. Du kan utföra ytterligare bearbetning utifrån dina krav.

```csharp
foreach (StructuredDocumentTagRangeStart tag in tags)
    Console.WriteLine(tag.Title);
```

### Exempel på källkod för Multi Section med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true);
	foreach (StructuredDocumentTagRangeStart tag in tags)
		Console.WriteLine(tag.Title);
```

Det är allt! Du har framgångsrikt hämtat och bearbetat strukturerade dokumenttaggar i flera sektioner i ditt Word-dokument med Aspose.Words för .NET.