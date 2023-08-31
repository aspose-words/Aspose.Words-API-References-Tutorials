---
title: Ställ in formatering av tabellrader
linktitle: Ställ in formatering av tabellrader
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ställa in tabellradsformatering med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

I den här handledningen går vi igenom steg-för-steg-processen för att ställa in tabellradsformatering med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du justerar höjden och fyllningarna på en tabellrad i dina Word-dokument med Aspose.Words för .NET.

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

## Steg 3: Starta en ny tabell och lägg till en cell
För att börja skapa tabellen använder vi`StartTable()` metoden för dokumentkonstruktorn lägger vi till en cell i tabellen med hjälp av`InsertCell()` metod.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Steg 4: Definiera linjeformateringen
 Nu kan vi ställa in radformateringen genom att komma åt`RowFormat` föremålet för`DocumentBuilder` objekt. Vi kan ställa in linjehöjden och marginalerna (utfyllnaderna) med hjälp av motsvarande egenskaper.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Steg 5: Ställ in tabellmarginaler
 Därefter kan vi ställa in tabellfyllningarna genom att komma åt motsvarande egenskaper för`Table` objekt. Dessa marginaler kommer att tillämpas på alla rader i tabellen.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Steg 6: Lägg till innehåll i raden
 Slutligen kan vi lägga till innehåll på raden med hjälp av dokumentbyggarens`Writeln()` metod.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Steg 7: Avsluta tabellen och spara dokumentet
I

 slutar vi att skapa tabellen med hjälp av`EndRow()` och`EndTable()` metod, sedan sparar vi det ändrade dokumentet till en fil.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Exempel på källkod för Set Table Row-formatering med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Dessa formateringsegenskaper ställs in i tabellen och tillämpas på alla rader i tabellen.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man ställer in tabellradsformatering med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt justera tabellradshöjd och marginaler i dina Word-dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att manipulera och formatera tabeller i dina dokument. Med denna kunskap kan du anpassa den visuella layouten av dina bord till dina specifika behov.