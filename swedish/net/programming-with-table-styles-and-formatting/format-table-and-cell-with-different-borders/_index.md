---
title: Formatera Tabell Och Cell Med Olika Kanter
linktitle: Formatera Tabell Och Cell Med Olika Kanter
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att formatera tabell och cell med olika gränser med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

den här handledningen går vi igenom processen steg-för-steg för att formatera en tabell och en cell med olika kanter med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av den här handledningen kommer du att veta hur du tillämpar anpassade ramar på specifika tabeller och celler i dina Word-dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där du vill spara ditt redigerade Word-dokument. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa ett nytt dokument- och dokumentbyggare
 Därefter måste du skapa en ny instans av`Document` klass och en dokumentkonstruktor för det dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Starta en ny tabell och lägg till celler
För att börja skapa tabellen använder vi`StartTable()` metoden för dokumentbyggaren lägger vi till celler i tabellen med hjälp av`InsertCell()` metod och vi skriver innehållet i cellerna till med hjälp av`Writeln()` metod.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Sätt ramar för hela bordet.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Ställ in utfyllnad för den här cellen.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Ange en annan cellfyllning för den andra cellen.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Rensa cellformatering från tidigare operationer.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Skapa tjockare ramar för den första cellen i den här raden. Det blir annorlunda
// i förhållande till gränserna definierade för tabellen.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Steg 4: Spara dokumentet

  ändras
Spara slutligen det ändrade dokumentet till en fil. Du kan välja ett lämpligt namn och plats för utdatadokumentet.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Grattis! Du har nu formaterat en tabell och en cell med olika ramar med Aspose.Words för .NET.

### Exempel på källkod för formatera tabell och cell med olika gränser med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Ställ in gränserna för hela bordet.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Ställ in cellskuggningen för den här cellen.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Ange en annan cellskuggning för den andra cellen.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Rensa cellformateringen från tidigare operationer.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Skapa större ramar för den första cellen i denna rad. Detta kommer att bli annorlunda
	// jämfört med gränserna för tabellen.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man formaterar en tabell och en cell med olika ramar med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt anpassa dina tabell- och cellkanter i dina Word-dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att manipulera och formatera tabeller i dina dokument. Med denna kunskap kan du förbättra den visuella presentationen av dina Word-dokument och möta specifika behov.