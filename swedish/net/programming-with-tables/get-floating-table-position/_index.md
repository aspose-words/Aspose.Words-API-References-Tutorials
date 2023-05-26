---
title: Få flytande bordsposition
linktitle: Få flytande bordsposition
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du får positionen för flytande tabeller i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/get-floating-table-position/
---

I den här handledningen kommer vi att lära oss hur man får positionen för ett flytande bord i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna få positioneringsegenskaperna för ett flytande bord i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet och komma åt tabellerna
För att börja arbeta med tabeller måste vi ladda dokumentet som innehåller dem och komma åt dem. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Ladda dokumentet
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog. Se också till att dokumentet innehåller flytande tabeller.

## Steg 3: Få flytande bordspositioneringsegenskaper
Därefter går vi igenom alla tabeller i dokumentet och får egenskaperna för placering av flytande bord. Använd följande kod:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Om matrisen är en flytande typ, skriv ut dess positioneringsegenskaper.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Här använder vi en`foreach` loop till loop genom alla arrayer i dokumentet. Vi kontrollerar om arrayen är flytande typ genom att kontrollera`TextWrapping` fast egendom. Om så är fallet skriver vi ut tabellens positioneringsegenskaper, såsom horisontellt ankare, vertikalt ankare, absoluta horisontella och vertikala avstånd, överlappande tillstånd, absolut horisontellt avstånd och vertikal justering relativ.
 
### Exempel på källkod för Get Floating Table Position med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Om tabellen är flytande, skriv ut dess positioneringsegenskaper.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Slutsats
den här handledningen lärde vi oss hur man får positionen för ett flytande bord i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du få positioneringsegenskaperna för flytande tabeller i dina Word-dokument programmatiskt. Denna funktion låter dig analysera och manipulera flytande tabeller enligt dina specifika behov.