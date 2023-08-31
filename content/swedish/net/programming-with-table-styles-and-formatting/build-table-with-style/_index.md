---
title: Bygg bord med stil
linktitle: Bygg bord med stil
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att bygga en tabell med en anpassad stil med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

den här handledningen går vi igenom processen steg-för-steg för att bygga en formaterad tabell med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du skapar en tabell med en anpassad stil i dina Word-dokument med Aspose.Words för .NET.

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

## Steg 3: Starta en ny tabell och infoga en cell
 För att börja bygga bordet använder vi`StartTable()` metoden för dokumentbyggaren, så infogar vi en cell i tabellen med hjälp av`InsertCell()` metod.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Steg 4: Definiera stilen på tabellen
 Nu kan vi ställa in tabellstilen med hjälp av`StyleIdentifier` fast egendom. I det här exemplet använder vi stilen "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Steg 5: Använd stilalternativ på tabellen
 Vi kan specificera vilka egenskaper som ska formateras av stilen med hjälp av`StyleOptions`egenskapen hos arrayen. I det här exemplet använder vi följande alternativ: "FirstColumn", "RowBands" och "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Steg 6: Justera bordsstorleken automatiskt
 För att automatiskt justera storleken på arrayen baserat på dess innehåll använder vi`AutoFit()` metod med`AutoFitBehavior.AutoFitToContents` beteende.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Steg 7: Lägg till innehåll i celler
 Nu kan vi lägga till innehåll i celler med hjälp av`Writeln()` och`InsertCell()` dokumentbyggarens metoder. I det här exemplet lägger vi till rubrikerna för "Artikel" och "Quantity (

kg)" och motsvarande data.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Steg 8: Spara det ändrade dokumentet
Slutligen sparar vi det ändrade dokumentet till en fil. Du kan välja ett lämpligt namn och plats för utdatadokumentet.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Grattis! Du har nu byggt en anpassad tabell med Aspose.Words för .NET.

### Exempel på källkod för Bygg tabell med stil med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// Vi måste infoga minst en rad först innan vi ställer in någon tabellformatering.
	builder.InsertCell();
	// Ställ in tabellstilen som används baserat på den unika stilidentifieraren.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Använd vilka funktioner som ska formateras av stilen.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man bygger en formaterad tabell med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt anpassa stilen på dina tabeller i dina Word-dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att manipulera och formatera tabeller i dina dokument. Med denna kunskap kan du förbättra den visuella presentationen av dina Word-dokument och möta specifika behov.