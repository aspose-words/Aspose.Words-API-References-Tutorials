---
title: Autopassa till sidbredd
linktitle: Autopassa till sidbredd
second_title: Aspose.Words Document Processing API
description: Lär dig hur du automatiskt anpassar en tabell till sidbredd i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-tables/auto-fit-to-page-width/
---

I den här handledningen kommer vi att lära oss hur man använder Aspose.Words för .NET för att automatiskt anpassa en tabell till sidbredd i ett Word-dokument. Vi kommer att följa en steg-för-steg-guide för att förstå koden och implementera den här funktionen. I slutet av denna handledning kommer du att kunna manipulera tabeller i Word-dokument programmatiskt.

## Steg 1: Projektinställning
1. Starta Visual Studio och skapa ett nytt C#-projekt.
2. Lägg till en referens till Aspose.Words for .NET-biblioteket.

## Steg 2: Skapa och konfigurera dokumentet
För att starta ordbehandling med tabellen måste vi skapa ett dokument och konfigurera dokumentgeneratorn. Följ dessa steg:

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och dokumentgeneratorn
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Se till att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Infoga och konfigurera tabellen
Därefter infogar vi en tabell i dokumentet med en bredd som tar upp halva sidans bredd. Använd följande kod:

```csharp
// Sätt in tabellen och konfigurera dess bredd
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Här använder vi dokumentbyggaren för att börja skapa tabellen, infoga celler och ställa in den föredragna bredden på tabellen till 50 % av sidbredden. Sedan lägger vi till text i varje cell.

## Steg 4: Spara det ändrade dokumentet
Slutligen måste vi spara det ändrade dokumentet med tabellen anpassad till sidans bredd. Använd följande kod:

```csharp
// Spara det ändrade dokumentet
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Var noga med att ange rätt sökväg och filnamn för utdatadokumentet.
  
### Exempel på källkod för Autopassa till sidabredd med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Infoga en tabell med en bredd som tar upp halva sidbredden.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Slutsats
den här handledningen lärde vi oss hur man automatiskt anpassar en tabell till sidbredd i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och implementera den medföljande C#-koden kan du manipulera tabeller i dina Word-dokument programmatiskt. Denna funktion gör att du dynamiskt kan anpassa tabellens bredd efter sidan, vilket ger ett professionellt och visuellt tilltalande dokument.