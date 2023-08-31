---
title: Tillåt cellavstånd
linktitle: Tillåt cellavstånd
second_title: Aspose.Words Document Processing API
description: Steg för steg guide för att tillåta cellavstånd med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/allow-cell-spacing/
---

I den här handledningen går vi igenom processen steg-för-steg för att tillåta cellavstånd i tabeller med Aspose.Words för .NET. Vi kommer att förklara C#-källkoden som utför denna uppgift och tillhandahålla en omfattande guide som hjälper dig att förstå och implementera den i dina egna projekt. I slutet av denna handledning kommer du att ha en klar förståelse för hur du manipulerar tabellformatering i dina Word-dokument med Aspose.Words för .NET.

## Steg 1: Ställ in dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där ditt Word-dokument lagras. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Ladda dokumentet
 Därefter måste du ladda Word-dokumentet i en instans av`Document` klass.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Steg 3: Gå till tabellen
 För att tillåta cellavstånd måste vi komma åt tabellen i dokumentet. De`Table` klass representerar en tabell i Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Steg 4: Aktivera cellavstånd
 Nu kan vi aktivera cellavstånd genom att ställa in`AllowCellSpacing` egenskap av tabellen till`true`. Den här egenskapen avgör om tabellen kan ha cellavstånd.

```csharp
table.AllowCellSpacing = true;
```

## Steg 5: Ställ in cellavstånd
 För att ange mängden utrymme mellan celler använder vi`CellSpacing` tabellens egendom. I det här exemplet sätter vi cellavståndet till 2 punkter.

```csharp
table. CellSpacing = 2;
```

## Steg 6: Spara det ändrade dokumentet
Slutligen sparar vi det ändrade dokumentet till en fil. Du kan välja ett lämpligt namn och plats för utdatadokumentet.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.AllowCellSpacing.docx");
```

Grattis! Du har framgångsrikt tillåtit cellavstånd i tabeller med Aspose.Words för .NET.

### Exempel på källkod för Tillåt cellavstånd med Aspose.Words för .NET 

```csharp
	//Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AllowCellSpacing = true;
	table.CellSpacing = 2;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.AllowCellSpacing.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man aktiverar cellavstånd i tabeller med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden kan du enkelt införliva denna funktion i dina C#-projekt. Att manipulera tabellformatering är en viktig aspekt av dokumentbehandling, och Aspose. Words tillhandahåller ett kraftfullt och flexibelt API för att uppnå detta. Med denna kunskap kan du förbättra den visuella presentationen av dina Word-dokument och uppfylla specifika formateringskrav.