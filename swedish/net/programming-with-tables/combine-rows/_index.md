---
title: Kombinera rader
linktitle: Kombinera rader
second_title: Aspose.Words Document Processing API
description: Lär dig hur du kombinerar tabellrader i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/combine-rows/
---

I den här handledningen kommer vi att lära oss hur man använder Aspose.Words för .NET för att kombinera rader med tabeller i ett Word-dokument. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna manipulera och slå samman tabellrader i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet och komma åt tabellerna
För att starta ordbehandling med tabeller måste vi ladda dokumentet som innehåller dem och komma åt dem. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "Tables.docx");

// Tillgång till bord
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Kombinera tabellrader
Därefter kommer vi att kombinera raderna i den andra tabellen till slutet av den första tabellen. Använd följande kod:

```csharp
// Kombination av tabellrader
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Här använder vi en`while` loop för att iterera över alla rader i den andra arrayen och lägg till dem i slutet av den första arrayen med`Add` metod. Därefter tar vi bort den andra tabellen från dokumentet med hjälp av`Remove` metod.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det ändrade dokumentet med de kombinerade tabellraderna. Använd följande kod:

```csharp
// Spara det ändrade dokumentet
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Combine Rows med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Raderna från den andra tabellen kommer att läggas till i slutet av den första tabellen.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Lägg till alla rader från den aktuella tabellen till nästa tabell
	// med olika cellantal och bredder kan sammanfogas till en tabell.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man kombinerar rader med tabeller i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du manipulera tabellrader i dina Word-dokument programmatiskt. Med den här funktionen kan du effektivt slå samman och organisera dina data till en tabell.