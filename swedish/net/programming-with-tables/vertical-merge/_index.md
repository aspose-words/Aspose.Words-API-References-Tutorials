---
title: Vertikal sammanfogning
linktitle: Vertikal sammanfogning
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du sammanfogar celler vertikalt i en tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/vertical-merge/
---

I den här handledningen kommer vi att lära oss hur man vertikalt sammanfogar celler i en tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna sammanfoga celler vertikalt i dina tabeller i Word-dokument.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet
För att börja arbeta med dokumentet, följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa ett nytt dokument
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Sammanfoga celler vertikalt
Därefter kommer vi att slå samman cellerna vertikalt i tabellen. Använd följande kod:

```csharp
// Infoga en cell
builder. InsertCell();

// Använd den vertikala sammanfogningen på den första cellen
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Infoga en annan cell
builder. InsertCell();

// Använd ingen vertikal sammanfogning på cellen
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Infoga en cell
builder. InsertCell();

// Använd den vertikala sammanfogningen med föregående cell
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Infoga en annan cell
builder. InsertCell();

// Använd ingen vertikal sammanfogning på cellen
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Avsluta skapandet av tabellen
builder. EndTable();
```

I den här koden använder vi DocumentBuilder-konstruktorn för att infoga celler i en tabell. Vi tillämpar vertikal sammanslagning på celler med egenskapen CellFormat.VerticalMerge. Vi använder CellMerge.First för den första cellsammanfogningen, CellMerge.Previous för att slå samman med föregående cell och CellMerge.None för ingen vertikal sammanfogning.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det ändrade dokumentet med de sammanslagna cellerna. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Vertical Merge med Aspose.Words för .NET 
```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Denna cell är vertikalt sammanfogad med cellen ovan och bör vara tom.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man vertikalt sammanfogar celler i en tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du enkelt slå samman celler Vertikal i dina tabeller.