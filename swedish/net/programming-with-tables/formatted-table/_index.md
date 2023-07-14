---
title: Formaterad tabell
linktitle: Formaterad tabell
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar en formaterad tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/formatted-table/
---

I den här handledningen kommer vi att lära oss hur man skapar en formaterad tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna skapa tabeller med anpassad formatering i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Skapa dokumentet och initialisera dokumentgeneratorn
För att börja bygga den formaterade tabellen måste vi skapa ett nytt dokument och initiera dokumentgeneratorn. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och initiera dokumentgeneratorn
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Bygg den formaterade tabellen
Därefter bygger vi den formaterade tabellen med de metoder som tillhandahålls av dokumentbyggaren. Använd följande kod:

```csharp
// Börja arraykonstruktion
Table table = builder. StartTable();

// Konstruktion av tabellhuvudraden
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Konstruktion av arraykroppen
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Slut på arraykonstruktion
builder. EndTable();
```

 Här använder vi dokumentbyggaren för att bygga tabellen steg för steg. Vi börjar med att ringa`StartTable()` för att initiera tabellen. Då använder vi`InsertCell()` att infoga celler och`Write()` för att lägga till innehåll i varje cell. Vi använder också olika formateringsegenskaper för att definiera formateringen av tabellrader, celler och text.

## Steg 4: Spara dokumentet
Slutligen måste vi spara dokumentet som innehåller den formaterade tabellen. Använd följande kod:

```csharp
// Spara dokumentet
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för formaterad tabell med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Tabellbreddformatering måste tillämpas efter att minst en rad finns i tabellen.
	table.LeftIndent = 20.0;
	// Ställ in höjd och definiera höjdregeln för rubrikraden.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// Vi behöver inte ange den här cellens bredd eftersom den ärvs från föregående cell.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Återställ höjden och definiera en annan höjdregel för tabellkroppen.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Återställ teckensnittsformatering.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man skapar en formaterad tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du skapa anpassade tabeller med specifik formatering i dina Word-dokument programmatiskt. Denna funktion låter dig presentera och strukturera dina data på ett visuellt tilltalande och organiserat sätt.