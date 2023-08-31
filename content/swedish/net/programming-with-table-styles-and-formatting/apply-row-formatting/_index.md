---
title: Använd radformatering
linktitle: Använd radformatering
second_title: Aspose.Words Document Processing API
description: Steg för steg guide för att tillämpa radformatering på en tabell med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/apply-row-formatting/
---

den här handledningen går vi igenom steg-för-steg-processen för att tillämpa radformatering på en tabell med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att ha en klar förståelse för hur du formaterar tabellrader i dina Word-dokument med Aspose.Words för .NET.

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

## Steg 3: Starta en ny bräda
 För att tillämpa radformatering måste vi först starta en ny tabell med hjälp av`StartTable()` dokumentkonstruktorns metod.

```csharp
Table table = builder. StartTable();
```

## Steg 4: Infoga cell och gå till radformat
Nu kan vi infoga en cell i tabellen och komma åt radformatet för den cellen med hjälp av dokumentbyggarens`InsertCell()` och`RowFormat` metoder.

```csharp
builder. InsertCell();
RowFormat rowFormat = builder.RowFormat;
```

## Steg 5: Ställ in radhöjd
 För att ställa in radhöjden använder vi`Height` och`HeightRule` egenskaperna för radformatet. I det här exemplet sätter vi en radhöjd på 100 poäng och använder`Exactly` regel.

```csharp
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Steg 6: Definiera tabellformatering
 Vissa formateringsegenskaper kan ställas in på själva tabellen och tillämpas på alla tabellrader. I det här exemplet ställer vi in tabellmarginalegenskaperna med hjälp av`LeftPadding`, `RightPadding`, `TopPadding` och`BottomPadding` egenskaper.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Steg 7: Lägg till innehåll i raden
Nu kan vi

 Vi kommer att lägga till innehåll på raden med hjälp av metoderna för dokumentkonstruktorn. I det här exemplet använder vi`Writeln()` metod för att lägga till text på raden.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Steg 8: Avsluta raden och tabellen
 När vi har lagt till innehållet i raden kan vi avsluta raden med hjälp av`EndRow()` metoden och avsluta sedan tabellen med hjälp av`EndTable()` metod.

```csharp
builder. EndRow();
builder. EndTable();
```

## Steg 9: Spara det ändrade dokumentet
Slutligen sparar vi det ändrade dokumentet till en fil. Du kan välja ett lämpligt namn och plats för utdatadokumentet.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

Grattis! Du har nu tillämpat radformatering på en tabell med Aspose.Words för .NET.

### Exempel på källkod för Apply Row Formatting med Aspose.Words för .NET 

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
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man tillämpar radformatering på en tabell med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt integrera denna funktionalitet i dina C#-projekt. Att manipulera tabellradsformatering är en viktig aspekt av dokumentbehandling, och Aspose.Words erbjuder ett kraftfullt och flexibelt API för att uppnå detta. Med denna kunskap kan du förbättra den visuella presentationen av dina Word-dokument och uppfylla specifika krav.