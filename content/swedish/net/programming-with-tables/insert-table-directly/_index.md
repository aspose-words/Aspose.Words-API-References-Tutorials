---
title: Sätt in tabell direkt
linktitle: Sätt in tabell direkt
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar en tabell direkt i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/insert-table-directly/
---

I den här handledningen kommer vi att lära oss hur du direkt infogar en tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna infoga tabeller direkt i dina Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Skapa dokumentet och tabellen
För att starta ordbehandling med arrayen måste vi skapa ett nytt dokument och initiera arrayen. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument
Document doc = new Document();

//Skapa arrayen
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Bygg arrayen
Därefter bygger vi tabellen genom att lägga till rader och celler. Använd följande kod som exempel:

```csharp
// Skapa den första raden
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Skapa den första cellen
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Duplicera cellen för den andra cellen i raden
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Här skapar vi en rad med`AllowBreakAcrossPages` egenskapen inställd på`true` för att tillåta sidbrytning mellan raderna. Vi skapar sedan en cell med färgad bakgrund, fast bredd och specificerat textinnehåll. Vi duplicerar sedan denna cell för att skapa den andra cellen i raden.

## Steg 4: Automatisk anpassningstabell
Vi kan använda automatiska justeringar av tabellen för att formatera den korrekt. Använd följande kod:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Denna kodrad tillämpar en automatisk anpassning baserat på fasta kolumnbredder.

## Steg 5: Registrera

  ändrat dokument
Slutligen måste vi spara det ändrade dokumentet med tabellen direkt infogat. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Infoga tabell direkt med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// Vi börjar med att skapa tabellobjektet. Observera att vi måste skicka dokumentobjektet
	//till konstruktören för varje nod. Detta beror på att varje nod vi skapar måste tillhöra
	// till något dokument.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Här skulle vi kunna ringa EnsureMinimum för att skapa raderna och cellerna åt oss. Denna metod används
	// för att säkerställa att den angivna noden är giltig. I det här fallet bör en giltig tabell ha minst en rad och en cell.
	// Istället kommer vi att hantera att skapa raden och tabellen själva.
	// Detta skulle vara det bästa sättet att göra detta om vi skapade en tabell i en algoritm.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// Vi kan nu tillämpa alla inställningar för automatisk passning.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Vi skulle sedan upprepa processen för de andra cellerna och raderna i tabellen.
	// Vi kan också påskynda saker och ting genom att klona befintliga celler och rader.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man direkt infogar en tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du infoga tabeller direkt i dina Word-dokument programmatiskt. Denna funktion låter dig skapa och anpassa tabeller efter dina specifika behov.