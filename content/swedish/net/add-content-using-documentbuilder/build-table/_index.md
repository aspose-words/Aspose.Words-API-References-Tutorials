---
title: Bygg tabell i Word-dokument
linktitle: Bygg tabell i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du bygger en tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/build-table/
---
I denna steg-för-steg handledning kommer du att lära dig hur du bygger en tabell i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna skapa en tabell med anpassad formatering och innehåll med hjälp av klassen DocumentBuilder.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument
För att börja skapa ett nytt dokument med klassen Document:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Starta tabellen
Använd sedan StartTable-metoden i klassen DocumentBuilder för att börja bygga tabellen:

```csharp
Table table = builder.StartTable();
```

## Steg 3: Infoga celler och lägg till innehåll
Nu kan du infoga celler i tabellen och lägga till innehåll till dem med metoderna InsertCell och Write i klassen DocumentBuilder. Anpassa cellformateringen efter behov:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Steg 4: Avsluta raden
Efter att ha lagt till innehåll i cellerna i den första raden, använd EndRow-metoden i klassen DocumentBuilder för att avsluta raden:

```csharp
builder.EndRow();
```

## Steg 5: Anpassa radformatering
Du kan anpassa formateringen av en rad genom att ställa in egenskaperna för RowFormat- och CellFormat-objekten:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Steg 6: Avsluta tabellen
För att slutföra tabellen, använd EndTable-metoden i klassen DocumentBuilder:

```csharp
builder.EndTable();
```

### Exempel på källkod för att bygga en tabell med Aspose.Words för .NET
Här är den fullständiga källkoden för att bygga en tabell med Aspose.Words för .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur man bygger en tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande källkoden kan du nu skapa tabeller med anpassad formatering.

### Vanliga frågor för att bygga tabell i word-dokument

#### F: Vad är Aspose.Words för .NET?

S: Aspose.Words för .NET är ett kraftfullt dokumentbehandlingsbibliotek som låter utvecklare skapa, läsa, redigera och konvertera Microsoft Word-dokument programmatiskt i .NET-applikationer. Det ger ett brett utbud av funktioner för att arbeta med Word-dokument, såsom textmanipulering, skapande av tabeller, dokumentskydd, formatering och mer.

#### F: Hur kan jag bygga en tabell i ett Word-dokument med Aspose.Words för .NET?

S: För att bygga en tabell i ett Word-dokument med Aspose.Words för .NET kan du följa dessa steg:
1.  Skapa en ny instans av`Document` klass och a`DocumentBuilder` objekt.
2.  Använd`StartTable` metod för`DocumentBuilder`klass för att börja bygga bordet.
3.  Infoga celler i tabellen och lägg till innehåll med hjälp av`InsertCell` och`Write` metoder för`DocumentBuilder` klass.
4.  Avsluta raden med hjälp av`EndRow` metod för`DocumentBuilder` klass.
5.  Anpassa radformatering genom att ställa in egenskaper för`RowFormat` och`CellFormat` föremål.
6.  Avsluta bordet med hjälp av`EndTable` metod för`DocumentBuilder` klass.
7. Spara dokumentet.

#### F: Hur kan jag anpassa formateringen av tabellen och dess celler?

 S: Du kan anpassa formateringen av tabellen och dess celler genom att ställa in olika egenskaper för`RowFormat` och`CellFormat` föremål. Du kan till exempel justera celljustering, vertikal och horisontell textorientering, cellhöjd, radhöjd med mera. Genom att använda dessa egenskaper kan du uppnå önskat utseende för tabellen och dess innehåll.

#### F: Kan jag bygga komplexa tabeller med sammanslagna celler och andra avancerade funktioner?

 S: Ja, Aspose.Words för .NET tillhandahåller avancerade funktioner för att bygga komplexa tabeller, inklusive stöd för sammanslagna celler, kapslade tabeller och komplexa tabelllayouter. Du kan använda`MergeCells` metod för att slå samman celler,`StartTable`metod för att skapa kapslade tabeller och andra metoder för att uppnå önskad tabellstruktur.

#### F: Är Aspose.Words för .NET kompatibelt med olika Word-dokumentformat?

S: Ja, Aspose.Words för .NET är kompatibelt med olika Word-dokumentformat, inklusive DOC, DOCX, RTF och mer. Den stöder både äldre format (DOC) och moderna XML-baserade format (DOCX) och låter dig arbeta med dokument i olika format utan problem.

#### F: Var kan jag hitta mer information och dokumentation för Aspose.Words för .NET?

 S: Du kan hitta omfattande dokumentation och kodexempel på[API-referenser](https://reference.aspose.com/words/net/). Dokumentationen kommer att ge detaljerad information om bibliotekets funktioner och hur du använder dem i dina .NET-applikationer.