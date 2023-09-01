---
title: Få bordsposition
linktitle: Få bordsposition
second_title: Aspose.Words Document Processing API
description: Lär dig hur du får positionen för en tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/get-table-position/
---

I den här handledningen ska vi lära oss hur man får positionen för en tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna få tabellpositioneringsegenskaper i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet och komma åt tabellen
För att starta ordbehandling med tabellen måste vi ladda dokumentet som innehåller den och komma åt den. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "Tables.docx");

// Tillgång till arrayen
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog. Se också till att dokumentet innehåller tabellen vars position du vill få.

## Steg 3: Hämta egenskaper för arraypositionering
Därefter kommer vi att kontrollera positioneringstypen för arrayen och få lämpliga positioneringsegenskaper. Använd följande kod:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Här använder vi ett villkor för att kontrollera om arrayen är av floattyp. I så fall skriver vi ut`RelativeHorizontalAlignment` och`RelativeVerticalAlignment` egenskaper för att få tabellens relativa horisontella och vertikala inriktning. Annars skriver vi ut`Alignment` egenskap för att få arrayjusteringen.

### Exempel på källkod för Get Table Position med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Slutsats
den här handledningen lärde vi oss hur man får positionen för en tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du få tabellpositioneringsegenskaper i dina Word-dokument programmatiskt. Den här funktionen låter dig analysera och manipulera arrayer enligt deras specifika positioner.