---
title: Bygg bord med gränser
linktitle: Bygg bord med gränser
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att bygga en tabell med gränser med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/build-table-with-borders/
---

den här handledningen går vi igenom processen steg-för-steg för att bygga en tabell med kanter med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du skapar en tabell med anpassade ramar i dina Word-dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det är här ditt Word-dokument lagras. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda befintligt dokument
 Därefter måste du ladda det befintliga Word-dokumentet i en instans av`Document` klass.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Steg 3: Gå till tabellen och ta bort befintliga gränser
 För att börja bygga tabellen med gränser måste vi navigera till tabellen i dokumentet och ta bort de befintliga gränserna. De`ClearBorders()` metoden tar bort alla ramar från tabellen.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table. ClearBorders();
```

## Steg 4: Ställ in bordsgränser
 Nu kan vi ställa in bordsgränserna med hjälp av`SetBorders()` metod. I det här exemplet använder vi en grönfärgad kant med en tjocklek på 1,5 punkter.

```csharp
table.SetBorders(LineStyle.Single, 1.5, Color.Green);
```

## Steg 5: Spara det ändrade dokumentet
Slutligen sparar vi det ändrade dokumentet till en fil. Du kan välja ett lämpligt namn och plats för utdatadokumentet.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

Grattis! Du har nu byggt en tabell med anpassade ramar med Aspose.Words för .NET.

### Exempel på källkod för Build Table With Borders med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Rensa alla befintliga gränser från tabellen.
	table.ClearBorders();
	// Sätt en grön kant runt och innanför bordet.
	table.SetBorders(LineStyle.Single, 1.5, Color.Green);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man bygger en tabell med gränser med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt anpassa dina tabellkanter i dina Word-dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att manipulera och formatera tabeller i dina dokument. Med denna kunskap kan du förbättra den visuella presentationen av dina Word-dokument och möta specifika behov.