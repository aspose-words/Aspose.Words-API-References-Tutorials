---
title: Skapa tabellstil
linktitle: Skapa tabellstil
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att skapa en anpassad tabellstil med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/create-table-style/
---

I den här handledningen går vi igenom processen steg-för-steg för att skapa en tabellstil med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du skapar en anpassad stil för dina tabeller i dina Word-dokument med Aspose.Words för .NET.

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
För att börja skapa tabellen använder vi`StartTable()` metoden för dokumentbyggaren lägger vi till celler i tabellen med hjälp av`InsertCell()` metod och vi skriver innehållet i cellerna till med hjälp av`Write()` metod.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## Steg 4: Skapa en tabellstil
 Nu kan vi skapa en tabellstil med hjälp av`TableStyle` klass och`Add()` metod från dokumentet`s `Samling av stilar. Vi definierar stilens egenskaper, såsom kanter, marginaler och stoppningar.

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## Steg 5: Tillämpa tabellstilen på tabellen
 Slutligen tillämpar vi tabellstilen vi skapade på tabellen med hjälp av`Style` tabellens egendom.

```csharp
table.Style = tableStyle;
```

## Steg 6: Spara det ändrade dokumentet
Spara slutligen det ändrade dokumentet till en fil. Du kan välja ett lämpligt namn och plats för utdatadokumentet.

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

Grattis! Du har nu skapat en anpassad stil för din tabell med Aspose.Words för .NET.

### Exempel på källkod för Skapa tabellstil med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man skapar en tabellstil med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt anpassa stilen på dina tabeller i dina Word-dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att manipulera och formatera tabeller i dina dokument. Med denna kunskap kan du förbättra den visuella presentationen av dina Word-dokument och möta specifika behov.