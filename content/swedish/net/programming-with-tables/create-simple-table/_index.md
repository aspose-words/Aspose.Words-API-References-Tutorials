---
title: Skapa en enkel tabell
linktitle: Skapa en enkel tabell
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar en enkel tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/create-simple-table/
---

I den här handledningen ska vi lära oss hur man skapar en enkel tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna skapa anpassade tabeller i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Skapa dokumentet och initialisera dokumentgeneratorn
För att börja bygga tabellen måste vi skapa ett nytt dokument och initiera dokumentbyggaren. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och initiera dokumentgeneratorn
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Bygg arrayen
Därefter bygger vi tabellen med de metoder som tillhandahålls av dokumentbyggaren. Använd följande kod:

```csharp
// Börja arraykonstruktion
builder. StartTable();

// Konstruktion av den första cellen i den första raden
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Konstruktion av den andra cellen i den första raden
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Anropa följande metod för att avsluta den första raden och starta en ny rad
builder. EndRow();

// Konstruktion av den första cellen i den andra raden
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Konstruktion av den andra cellen i den andra raden
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Anropa nästa metod för att avsluta den andra raden
builder. EndRow();

// Indikation på att konstruktionen av bordet är färdig
builder. EndTable();
```

 Här använder vi dokumentbyggaren för att bygga tabellen steg för steg. Vi börjar med att ringa`StartTable()` för att initiera tabellen och använd sedan`InsertCell()` att infoga celler och`Write()` för att lägga till innehåll i varje cell. Vi använder också`EndRow()` för att avsluta en rad och starta en ny rad. Till sist ringer vi`EndTable()` för att indikera att bordskonstruktionen är klar.

## Steg 4: Spara dokumentet
Äntligen måste vi spara

  dokumentet med den skapade tabellen. Använd följande kod:

```csharp
// Spara dokumentet
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Skapa enkel tabell med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Börja bygga bordet.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Bygg den andra cellen.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Anropa följande metod för att avsluta raden och starta en ny rad.
	builder.EndRow();
	// Bygg den första cellen i den andra raden.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Bygg den andra cellen.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Signalerar att vi har byggt klart bordet.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man skapar en enkel tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden och implementera den medföljande C#-koden kan du skapa anpassade tabeller i dina Word-dokument programmatiskt. Denna funktion låter dig formatera och organisera dina data på ett strukturerat och tydligt sätt.