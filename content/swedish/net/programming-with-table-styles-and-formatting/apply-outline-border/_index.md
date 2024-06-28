---
title: Använd konturgräns
linktitle: Använd konturgräns
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att applicera en konturram på en tabell med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

den här handledningen går vi igenom processen steg-för-steg för att applicera en konturram på en tabell med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att ha en klar förståelse för hur du manipulerar tabellkanter i dina Word-dokument med Aspose.Words för .NET.

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det är här ditt Word-dokument lagras. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda upp dokumentet
 Därefter måste du ladda Word-dokumentet i en instans av`Document` klass.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Steg 3: Gå till tabellen
 För att tillämpa en konturgräns måste vi komma åt tabellen i dokumentet. De`Table` klass representerar en tabell i Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Steg 4: Rikta in tabellen mot mitten av sidan
 Nu kan vi anpassa tabellen till mitten av sidan med hjälp av`Alignment` tabellens egendom.

```csharp
table. Alignment = Table Alignment. Center;
```

## Steg 5: Radera befintliga bordskanter.
För att börja med en ny konturgräns måste vi först radera alla befintliga gränser från tabellen. Detta kan göras med hjälp av`ClearBorders()` metod.

```csharp
table. ClearBorders();
```

## Steg 6: Definiera en grön ram runt bordet
 Vi kan nu sätta en grön ram runt bordet med hjälp av`SetBorder()` metod för varje sida av bordet. I det här exemplet använder vi en kant av typen "Single" med en tjocklek på 1,5 punkter och en grön färg.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Steg 7: Fyll cellerna med en bakgrundsfärg.
För att förbättra den visuella presentationen av tabellen kan vi fylla cellerna med en grundbakgrundsfärg.

aning. I det här exemplet använder vi en ljusgrön färg.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Steg 8: Spara det ändrade dokumentet
Slutligen sparar vi det ändrade dokumentet till en fil. Du kan välja ett lämpligt namn och plats för utdatadokumentet.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Grattis! Du har nu använt en konturram på en tabell med Aspose.Words för .NET.

### Exempel på källkod för Apply Outline Border med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Rikta in tabellen mot mitten av sidan.
	table.Alignment = TableAlignment.Center;
	//Rensa alla befintliga gränser från tabellen.
	table.ClearBorders();
	// Sätt en grön ram runt bordet men inte inuti.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Fyll cellerna med en ljusgrön fast färg.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Slutsats
I den här handledningen lärde vi oss hur man applicerar en konturram på en tabell med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide kan du enkelt integrera denna funktionalitet i dina C#-projekt. Att manipulera tabellformatering är en viktig aspekt av dokumentbehandling, och Aspose.Words erbjuder ett kraftfullt och flexibelt API för att uppnå detta. Med denna kunskap kan du förbättra den visuella presentationen av dina Word-dokument och uppfylla specifika krav.