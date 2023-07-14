---
title: Delat bord
linktitle: Delat bord
second_title: Aspose.Words Document Processing API
description: Lär dig hur du delar upp en tabell i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/split-table/
---

I den här handledningen ska vi lära oss hur man delar upp en tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna dela en tabell från en viss rad i dina Word-dokument.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet
Följ dessa steg för att starta ordbehandling med dokumentet:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "Tables.docx");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog och ange korrekt filnamn.

## Steg 3: Dela bordet
Därefter delar vi bordet från en viss rad. Använd följande kod:

```csharp
// Hämta det första bordet
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Bestämning av linjen från vilken tabellen ska delas
Row row = firstTable.Rows[2];

// Skapa en ny behållare för den delade tabellen
Table table = (Table)firstTable.Clone(false);

// Sätt i behållaren efter originalbordet
firstTable.ParentNode.InsertAfter(table, firstTable);

// Lägg till ett buffertstycke för att behålla ett avstånd mellan tabellerna
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Flytta rader från den ursprungliga tabellen till den delade tabellen
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Här använder vi dokumentet för att hämta den första tabellen från dokumentnoden. Sedan bestämmer vi raden som vi vill dela tabellen från, i detta exempel är det den tredje raden (index 2). Vi skapar sedan en ny behållare genom att klona den ursprungliga tabellen och sedan infoga den efter den ursprungliga tabellen. Vi lägger också till ett buffertstycke för att upprätthålla ett avstånd mellan de två tabellerna. Sedan flyttar vi rader från den ursprungliga tabellen till den delade tabellen med hjälp av en do-while loop tills vi når den angivna raden.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara

  dokument som ändrats med den delade tabellen. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Split Table med Aspose.Words för .NET 

```csharp
//Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// Vi delar bordet på tredje raden (inklusive).
Row row = firstTable.Rows[2];
// Skapa en ny behållare för den delade tabellen.
Table table = (Table) firstTable.Clone(false);
// Sätt i behållaren efter originalet.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Lägg till ett buffertstycke för att säkerställa att tabellerna håller isär.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man delar upp en tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du enkelt dela upp tabeller från en viss rad i dina Word-dokument.