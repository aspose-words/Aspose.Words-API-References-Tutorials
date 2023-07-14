---
title: Radformat Inaktivera Break Across Pages
linktitle: Radformat Inaktivera Break Across Pages
second_title: Aspose.Words Document Processing API
description: Lär dig hur du inaktiverar radbrytning för en tabell över flera sidor i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/row-format-disable-break-across-pages/
---

den här handledningen ska vi lära oss hur man inaktiverar radbrytning för en flersidig tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna inaktivera radbrytning för alla rader i din tabell i dina Word-dokument.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet
Följ dessa steg för att starta ordbehandling med dokumentet:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog och ange korrekt filnamn.

## Steg 3: Inaktivera tabellradbrytning
Därefter kommer vi att inaktivera radbrytning för alla rader i tabellen. Använd följande kod:

```csharp
// Hämta bordet
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Inaktivera radbrytning för alla rader i tabellen
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Här använder vi dokumentet för att hämta den första tabellen och itererar sedan igenom alla rader i tabellen med hjälp av en foreach loop. Inne i slingan inaktiverar vi radbrytning för varje rad genom att ställa in`RowFormat.AllowBreakAcrossPages` egendom till`false`.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det ändrade dokumentet med tabellradbrytningen inaktiverad. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för radformat Inaktivera Break Across Pages med Aspose.Words för .NET 

```csharp
//Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Inaktivera delning över sidor för alla rader i tabellen.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man inaktiverar radbrytning för en flersidig tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du tillämpa denna inaktivering på dina tabeller i dina Word-dokument.