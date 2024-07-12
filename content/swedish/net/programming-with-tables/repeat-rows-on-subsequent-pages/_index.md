---
title: Upprepa rader på efterföljande sidor
linktitle: Upprepa rader på efterföljande sidor
second_title: Aspose.Words Document Processing API
description: Lär dig hur du upprepar tabellrader på efterföljande sidor i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

I den här handledningen kommer vi att lära oss hur man upprepar raderna i en tabell på efterföljande sidor i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna ange rader som ska upprepas på efterföljande sidor i din tabell i dina Word-dokument.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Skapa dokumentet och initialisera dokumentgeneratorn
För att starta ordbehandling med dokument- och dokumentgeneratorn, följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument
Document doc = new Document();

// Initiera dokumentgeneratorn
DocumentBuilder builder = new DocumentBuilder(doc);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Bygg tabellen med upprepade rader
Därefter bygger vi en tabell med upprepade rader på efterföljande sidor. Använd följande kod:

```csharp
// Början av bordet
builder. StartTable();

// Konfiguration av parametrarna på första raden (huvudrader)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

//Infoga den första cellen i den första raden
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Infoga den andra cellen i den första raden
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Konfigurera parametrarna för följande rader
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Slinga för att infoga cellerna i följande rader
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Slut på bordet
builder. EndTable();
```

 Här använder vi dokumentbyggaren för att bygga en tabell med två rubrikrader och flera datarader. De`RowFormat.HeadingFormat` parametrar används för att markera rubrikrader som ska upprepas på efterföljande sidor.

## Steg 4: Spara det ändrade dokumentet
Äntligen USA

  måste spara det ändrade dokumentet med rubrikraderna som upprepas på efterföljande sidor i tabellen. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för upprepade rader på efterföljande sidor med Aspose.Words för .NET 

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man upprepar raderna i en tabell på efterföljande sidor i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du specificera vilka rader som ska upprepas enligt dina specifika behov i dina Word-dokument.