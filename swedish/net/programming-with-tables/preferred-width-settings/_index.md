---
title: Önskad breddinställningar
linktitle: Önskad breddinställningar
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in föredragna tabellcellbredder i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/preferred-width-settings/
---

I den här handledningen kommer vi att lära oss hur du ställer in föredragna breddinställningar för tabellceller i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna ange olika föredragna bredder för dina tabellceller i dina Word-dokument.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Skapa dokumentet och initialisera dokumentgeneratorn
För att börja arbeta med dokument- och dokumentgeneratorn, följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument
Document doc = new Document();

// Initiera dokumentgeneratorn
DocumentBuilder builder = new DocumentBuilder(doc);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Bygg bordet med önskade bredder
Därefter bygger vi en tabell med tre celler som har olika föredragna bredder. Använd följande kod:

```csharp
// Början av bordet
builder. StartTable();

// Infoga en cell av absolut storlek
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Infoga en cell av relativ storlek (i procent)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Infoga en cell med automatisk storlek
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Slut på bordet
builder. EndTable();
```

Här använder vi dokumentbyggaren för att bygga en tabell med tre celler. Den första cellen har en föredragen bredd på 40 punkter, den andra cellen har en föredragen bredd på 20 % av tabellbredden och den tredje cellen har en automatisk föredragen bredd som justeras

  beroende på tillgängligt utrymme.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det modifierade dokumentet med de önskade breddinställningarna definierade för tabellcellerna. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Preferred Width Settings med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Infoga en tabellrad som består av tre celler som har olika föredragna bredder.
	builder.StartTable();
	// Infoga en cell i absolut storlek.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Infoga en cell i relativ (procent) storlek.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Infoga en cell i automatisk storlek.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man ställer in föredragna breddinställningar för tabellceller i ett Word-dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden och implementera den medföljande C#-koden kan du anpassa dina tabellcellbredder till dina specifika behov i dina Word-dokument.