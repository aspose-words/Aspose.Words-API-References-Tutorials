---
title: Expandera formatering på celler och rad från stil
linktitle: Expandera formatering på celler och rad från stil
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att utöka formateringen till celler och rader från en tabellstil med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

I den här handledningen går vi igenom steg-för-steg-processen för att utöka formateringen till celler och rader från en stil med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du använder tabellformatering på specifika celler och rader i dina Word-dokument med Aspose.Words för .NET.


## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det är här ditt Word-dokument finns. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda befintligt dokument
 Därefter måste du ladda det befintliga Word-dokumentet i en instans av`Document` klass.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Steg 3: Gå till den första cellen i den första tabellen
 För att börja måste vi navigera till den första cellen i den första tabellen i dokumentet. Vi använder`GetChild()` och`FirstRow.FirstCell` metoder för att få referensen till den första cellen.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Steg 4: Visa initial cellformatering
Innan vi expanderar stilarna i tabellen visar vi cellens aktuella bakgrundsfärg. Detta bör vara tomt eftersom den aktuella formateringen lagras i tabellens stil.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Steg 5: Expandera tabellstilar till direktformatering
 Nu utökar vi tabellstilarna till direktformatering med hjälp av dokumentets`ExpandTableStylesToDirectFormatting()` metod.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Steg 6: Visa cellformatering efter formatexpansion
Nu visar vi bakgrundsfärgen för cellen efter att ha utökat tabellstilarna. En blå bakgrundsfärg bör appliceras från tabellstilen.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Exempel på källkod för expandera formatering på celler och rad från stil med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Hämta den första cellen i den första tabellen i dokumentet.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Skriv först ut färgen på cellskuggningen.
	// Detta bör vara tomt eftersom den aktuella skuggningen lagras i tabellstilen.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Skriv nu ut cellskuggningen efter att ha utökat tabellstilar.
	// En blå bakgrundsfärg borde ha använts från bordsstilen.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Slutsats
den här handledningen lärde vi oss hur man utökar formatering till celler och rader från en tabellstil med Aspose.Words för .NET. Genom att följa den här steg-för-steg-guiden kan du enkelt tillämpa tabellformatering på specifika celler och rader i dina Word-dokument. Aspose.Words erbjuder ett kraftfullt och flexibelt API för att manipulera och formatera tabeller i dina dokument. Med denna kunskap kan du ytterligare anpassa layouten och presentationen av dina Word-dokument.