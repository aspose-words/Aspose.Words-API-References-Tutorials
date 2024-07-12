---
title: Få avstånd mellan tabellens omgivande text
linktitle: Få avstånd mellan tabellens omgivande text
second_title: Aspose.Words Document Processing API
description: Steg-för-steg guide för att få avståndet mellan text och en tabell i ett Word-dokument med hjälp av Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

den här handledningen går vi igenom processen steg-för-steg för att få avståndet mellan omgivande text i en tabell med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du kommer åt de olika avstånden mellan en tabell och den omgivande texten i dina Word-dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det är här ditt Word-dokument finns. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda befintligt dokument
 Därefter måste du ladda det befintliga Word-dokumentet i en instans av`Document` klass.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Steg 3: Få avståndet mellan tabellen och den omgivande texten
 För att få avståndet mellan tabellen och den omgivande texten måste vi komma åt tabellen i dokumentet med hjälp av`GetChild()` metoden och`NodeType.Table` fast egendom. Vi kan sedan visa de olika avstånden med hjälp av arrayegenskaperna`DistanceTop`, `DistanceBottom`, `DistanceRight`och`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Exempel på källkod för Get Distance Between Table Surrounding Text med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Slutsats
den här handledningen lärde vi oss hur man får avståndet mellan omgivande text i en tabell med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kommer du enkelt åt de olika avstånden mellan en tabell och den omgivande texten i dina Word-dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att manipulera och formatera tabeller i dina dokument. Med denna kunskap kan du analysera layouten på dina tabeller i förhållande till texten och möta specifika behov.