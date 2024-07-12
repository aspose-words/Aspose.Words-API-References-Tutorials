---
title: Klona komplett tabell
linktitle: Klona komplett tabell
second_title: Aspose.Words Document Processing API
description: Lär dig hur du klona en hel tabell till ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/clone-complete-table/
---

I den här handledningen kommer vi att lära oss hur man använder Aspose.Words för .NET för att klona en hel tabell till ett Word-dokument. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna klona tabeller i dina Word-dokument programmatiskt.

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

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Full Array Clone
Därefter klona vi hela tabellen och infogar den i dokumentet efter originalet. Använd följande kod:

```csharp
// Klona arrayen
Table tableClone = (Table)table.Clone(true);

//Infoga den klonade tabellen i dokumentet efter originalet
table.ParentNode.InsertAfter(tableClone, table);

// Infoga ett tomt stycke mellan de två tabellerna
// Annars kommer de att kombineras till en vid spara (detta beror på dokumentvalidering)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Här använder vi`Clone` metod för att skapa en komplett kopia av arrayen. Då använder vi`InsertAfter` för att infoga den klonade tabellen i dokumentet, efter den ursprungliga tabellen. Vi lägger också till ett tomt stycke mellan de två tabellerna för att förhindra att de slås samman när du sparar.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det modifierade dokumentet med den klonade tabellen. Använd följande kod:

```csharp
// Spara det ändrade dokumentet
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.
  
### Exempel på källkod för Clone Complete Table med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Klona tabellen och infoga den i dokumentet efter originalet.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Infoga ett tomt stycke mellan de två tabellerna,
	// annars kommer de att kombineras till en när du sparar detta har att göra med dokumentvalidering.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man klona en hel tabell till ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du klona tabeller i dina Word-dokument programmatiskt. Den här funktionen låter dig utföra avancerade manipulationer på arrayer för att passa dina specifika behov.