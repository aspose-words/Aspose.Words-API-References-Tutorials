---
title: Konvertera till horisontellt sammanslagna celler
linktitle: Konvertera till horisontellt sammanslagna celler
second_title: Aspose.Words Document Processing API
description: Lär dig hur du konverterar tabellceller till horisontellt sammanslagna celler i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/convert-to-horizontally-merged-cells/
---

I den här handledningen kommer vi att lära oss hur man använder Aspose.Words för .NET för att konvertera tabellceller till horisontellt sammanslagna celler i ett Word-dokument. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna manipulera tabellceller i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet och komma åt tabellen
För att starta ordbehandling med tabellen måste vi ladda dokumentet som innehåller den och komma åt den. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "Table with merged cells.docx");

// Tillgång till arrayen
Table table = doc.FirstSection.Body.Tables[0];
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog. Se också till att dokumentet innehåller en tabell med horisontellt sammanfogade celler.

## Steg 3: Konvertera till horisontellt sammanslagna celler
 Därefter kommer vi att konvertera tabellcellerna till horisontellt sammanslagna celler med hjälp av`ConvertToHorizontallyMergedCells()` metod. Använd följande kod:

```csharp
// Konvertera till horisontellt sammanslagna celler
table. ConvertToHorizontallyMergedCells();
```

 Här kallar vi bara`ConvertToHorizontallyMergedCells()` metod på arrayen för att utföra konverteringen.

### Exempel på källkod för konvertera till horisontellt sammanslagna celler med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table with merged cells.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	// Nu har sammanslagna celler lämpliga sammanslagningsflaggor.
	table.ConvertToHorizontallyMergedCells();
```

## Slutsats
I den här handledningen lärde vi oss hur man konverterar tabellceller till horisontellt sammanslagna celler i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du manipulera tabellceller i dina Word-dokument programmatiskt. Denna funktion låter dig hantera och organisera dina data på ett flexibelt och personligt sätt i en tabell.