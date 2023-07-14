---
title: Håll ihop bordet
linktitle: Håll ihop bordet
second_title: Aspose.Words Document Processing API
description: Lär dig hur du håller ihop ett bord i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/keep-table-together/
---

I den här handledningen ska vi lära oss hur man håller ihop en tabell i ett Word-dokument med Aspose.Words för .NET. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av den här handledningen kommer du att kunna behålla en tabell intakt utan att den delas över flera sidor i dina Word-dokument.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Ladda dokumentet och hämta tabellen
För att starta ordbehandling med tabellen måste vi ladda dokumentet och hämta tabellen vi vill behålla tillsammans. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Hämta bordet
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Aktivera alternativet "KeepWithNext".
För att hålla ihop tabellen och förhindra att den delas upp över flera sidor, måste vi aktivera alternativet "KeepWithNext" för varje stycke i tabellen förutom de sista styckena i den sista raden i tabellen. Använd följande kod:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Här går vi igenom varje cell i tabellen och aktiverar alternativet "KeepWithNext" för varje stycke i cellen förutom de sista styckena i den sista raden i tabellen.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det ändrade dokumentet med tabellen sammanhållen. Använd följande kod:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.

### Exempel på källkod för Keep Table Together med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Vi måste aktivera KeepWithNext för varje stycke i tabellen för att förhindra att den bryts över en sida,
	// förutom de sista styckena i den sista raden i tabellen.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man håller ihop en tabell i ett Word-dokument med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden och implementera den medföljande C#-koden kan du behålla en tabell intakt och förhindra att den delas upp på flera sidor i dina dokument. Den här funktionen ger dig mer kontroll över utseendet och layouten på dina tabeller i dina dokument.