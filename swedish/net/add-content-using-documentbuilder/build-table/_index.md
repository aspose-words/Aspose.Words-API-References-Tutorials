---
title: Bygg bord
linktitle: Bygg bord
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du bygger en tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/build-table/
---

denna steg-för-steg handledning kommer du att lära dig hur du bygger en tabell i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna skapa en tabell med anpassad formatering och innehåll med hjälp av klassen DocumentBuilder.

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