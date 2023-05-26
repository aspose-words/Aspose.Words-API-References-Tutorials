---
title: Horisontell sammanfogning
linktitle: Horisontell sammanfogning
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du sammanfogar celler horisontellt i en Word-tabell med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/horizontal-merge/
---

I den här handledningen kommer vi att lära oss hur man horisontellt sammanfogar celler i en tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna slå samman celler horisontellt i dina Word-tabeller programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Skapa dokumentet och initialisera dokumentgeneratorn
För att börja arbeta med tabellen och cellerna måste vi skapa ett nytt dokument och initiera dokumentgeneratorn. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och initiera dokumentgeneratorn
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Bygg tabellen med horisontell sammanslagning av celler
Därefter bygger vi tabellen och tillämpar horisontell cellsammanslagning med egenskaperna som tillhandahålls av Aspose.Words för .NET. Använd följande kod:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Den här cellen slås samman med den föregående och bör vara tom.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Här använder vi dokumentbyggaren för att bygga tabellen och ställa in cellens horisontella sammanfogningsegenskaper. Vi använder`HorizontalMerge` egendom av`CellFormat` objekt för att ange vilken typ av horisontell sammanslagning som ska tillämpas på varje cell. Använder sig av`CellMerge.First` vi slår samman den första cellen med nästa, medan vi använder`CellMerge.Previous` vi slår samman den nuvarande cellen med den föregående cellen.`CellMerge.None` indikerar att cellen inte ska slås samman.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det modifierade dokumentet med cellerna sammanslagna horisontellt. Använd följande kod:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Horizontal Merge med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Den här cellen slås samman med den föregående och bör vara tom.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man horisontellt sammanfogar celler i en tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du tillämpa horisontell cellsammanfogning i dina Word-tabeller programmatiskt. Den här funktionen låter dig skapa mer komplexa tabelllayouter och bättre organisera dina data.