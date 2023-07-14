---
title: Flytande bordsposition
linktitle: Flytande bordsposition
second_title: Aspose.Words Document Processing API
description: Lär dig hur du placerar en tabell i en flytande position i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/floating-table-position/
---

I den här handledningen ska vi lära oss hur man använder Aspose.Words för .NET för att placera en tabell i en flytande position i ett Word-dokument. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna styra positionen och justeringen av flytande tabeller i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet och komma åt tabellen
För att starta ordbehandling med tabellen måste vi ladda dokumentet som innehåller den och komma åt den. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Tillgång till arrayen
Table table = doc.FirstSection.Body.Tables[0];
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog. Se också till att dokumentet innehåller en tabell som kommer att placeras i en flytande position.

## Steg 3: Placering av den flytande brädan
Därefter placerar vi tabellen i en flytande position med hjälp av egenskaperna som tillhandahålls av Aspose.Words för .NET. Använd följande kod:

```csharp
// Placering av det flytande bordet
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Här använder vi`AbsoluteHorizontalDistance` egenskap för att ställa in det absoluta horisontella avståndet för tabellen från sidans vänstra kant. Vi använder också`RelativeVerticalAlignment` egenskap för att ställa in tabellens relativa vertikala anpassning till det omgivande innehållet.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det modifierade dokumentet med tabellen placerad i en flytande position. Använd följande kod:

```csharp
// Spara det ändrade dokumentet
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för flytande bordsposition med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man placerar en tabell i en flytande position i ett Word-dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden och implementera den medföljande C#-koden kan du styra positionen och justeringen av flytande tabeller i dina Word-dokument programmatiskt.