---
title: Ställ in cellutfyllnad
linktitle: Ställ in cellutfyllnad
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att ställa in tabellcellmarginaler med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

I den här handledningen går vi igenom processen steg-för-steg för att ställa in tabellcellmarginaler med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du justerar vänster, övre, höger och nedre marginaler (mellanrum) av cellinnehåll i dina tabeller i dina Word-dokument med Aspose.Words för .NET .

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
builder. StartTable();
builder. InsertCell();
```

## Steg 4: Ställ in cellmarginaler
 Nu kan vi ställa in cellmarginalerna med hjälp av`SetPaddings()` metod för`CellFormat` objekt. Marginaler definieras i punkter och anges i ordningen vänster, topp, höger och botten.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## Steg 5: Lägg till innehåll i cellen
 Sedan kan vi lägga till innehåll i cellen med hjälp av dokumentbyggarens`Writeln()` metod.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Steg 6: Gör klart tabellen och spara dokumentet
 Slutligen avslutar vi skapa tabellen med hjälp av`EndRow()` metod och`EndTable()`, sedan sparar vi det ändrade dokumentet till en fil.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Exempel på källkod för Set Cell Padding med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Ställer in mängden utrymme (i poäng) som ska läggas till till vänster/överst/höger/botten av cellens innehåll.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man ställer in marginalerna för en tabellcell med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden kan du enkelt justera cellmarginaler för att skapa utrymmen till vänster, överst, höger och längst ned i innehållet i dina tabeller i dina Word-dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att manipulera och formatera tabeller i dina dokument. Med denna kunskap kan du anpassa formateringen av dina tabeller efter dina specifika behov.