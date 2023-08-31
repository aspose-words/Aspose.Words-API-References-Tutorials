---
title: Kapslad tabell
linktitle: Kapslad tabell
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar en kapslad tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/nested-table/
---

I den här handledningen kommer vi att lära oss hur man skapar en kapslad tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna skapa kapslade tabeller i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Skapa dokumentet och initialisera dokumentgeneratorn
För att starta ordbehandling med dokument- och dokumentgeneratorn, följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument
Document doc = new Document();

// Initiera dokumentgeneratorn
DocumentBuilder builder = new DocumentBuilder(doc);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Bygg det kapslade bordet
Därefter bygger vi den kapslade tabellen genom att infoga celler i den yttre tabellen och skapa en ny tabell inuti den första cellen. Använd följande kod:

```csharp
// Infoga den första cellen i den yttre tabellen
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Infoga den andra cellen i den yttre tabellen
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Avslutning av ytterbordet
builder. EndTable();

// Flytta till den första cellen i den yttre tabellen
builder.MoveTo(cell.FirstParagraph);

// Bygg det inre bordet
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Slutet på det inre bordet
builder. EndTable();
```

Här använder vi dokumentbyggaren för att infoga celler och innehåll i den yttre tabellen. Sedan flyttar vi dokumentbyggaren till den första cellen i den yttre tabellen och bygger en ny tabell inuti genom att infoga celler och innehåll.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det modifierade dokumentet med den kapslade tabellen. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Var noga med att ange rätt sökväg och namnfil för utdatadokumentet.

### Exempel på källkod för Nested Table med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Detta anrop är viktigt för att skapa en kapslad tabell i den första tabellen.
	// Utan detta anrop kommer cellerna som infogas nedan att läggas till i den yttre tabellen.
	builder.EndTable();
	// Flytta till den första cellen i den yttre tabellen.
	builder.MoveTo(cell.FirstParagraph);
	// Bygg det inre bordet.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man skapar en kapslad tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du skapa kapslade tabeller enligt dina specifika behov i dina Word-dokument programmatiskt.
