---
title: Flytta till tabellcell i Word-dokument
linktitle: Flytta till tabellcell i Word-dokument
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att använda Flytta till tabellcell i Word-dokumentfunktionen i Aspose.Words för .NET
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/move-to-table-cell/
---
det här exemplet kommer vi att gå igenom hur du använder funktionen Flytta till tabellcell i Word-dokument i Aspose.Words för .NET med hjälp av den medföljande C#-källkoden steg för steg. Den här funktionen låter dig navigera och manipulera specifika celler i en tabell i ett Word-dokument. Följ stegen nedan för att integrera den här funktionen i din applikation.

## Steg 1: Ladda dokumentet som innehåller tabellen

Först måste vi ladda dokumentet som innehåller tabellen som vi vill flytta cellen till. Använd följande kod för att utföra detta steg:

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

Denna kod laddar det angivna dokumentet (ersätt "MyDir + "Tables.docx"" med den faktiska sökvägen till ditt dokument som innehåller tabellen).

## Steg 2: Flytta DocumentBuilder till en specifik tabellcell

Därefter flyttar vi DocumentBuilder till en specifik tabellcell. Använd följande kod för att utföra detta steg:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

Den här koden skapar en DocumentBuilder från det befintliga dokumentet och flyttar sedan markören från DocumentBuilder till den angivna tabellcellen. Slutligen lägger den till innehåll till den cellen med hjälp av DocumentBuilder's`Write()` metod.

## Steg 3: Kontrollera resultatet

Du kan nu verifiera att flytten till tabellcellen lyckades. Använd följande kod för att utföra detta steg:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

Den här koden verifierar att den angivna cellen verkligen är den aktuella cellen i DocumentBuilder. Den verifierar också att innehållet som lagts till av DocumentBuilder har sparats korrekt i tabellcellen.

Det är allt ! Du har nu förstått hur du använder flytt till tabellcellfunktionaliteten i Aspose.Words för .NET med den medföljande källkoden. Du kan nu integrera denna funktionalitet i ditt eget program och manipulera specifika tabellceller i Word-dokument.


### Exempel på källkod för att flytta till en tabellcell med Aspose.Words för .NET


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

// Flytta byggaren till rad 3, cell 4 i den första tabellen.
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## Slutsats

det här exemplet utforskade vi funktionen Flytta till tabellcell i Aspose.Words för .NET. Vi lärde oss hur man laddar ett dokument som innehåller en tabell, flyttar DocumentBuilder till en specifik tabellcell och lägger till innehåll i den cellen. Den här funktionen ger utvecklare kraftfulla verktyg för att navigera och manipulera specifika celler i Word-dokumenttabeller programmatiskt med Aspose.Words för .NET. Det kan vara ett värdefullt tillägg till din ansökan för dynamisk Word-dokumentbehandling och hantering av tabellinnehåll.

### Vanliga frågor för att flytta till tabellcell i Word-dokument

#### F: Vad är syftet med funktionen Flytta till tabellcell i Aspose.Words för .NET?

S: Funktionen Flytta till tabellcell i Aspose.Words för .NET tillåter utvecklare att navigera till och manipulera specifika celler i en tabell i ett Word-dokument programmatiskt. Det ger möjlighet att infoga, ändra eller ta bort innehåll i en viss cell.

#### F: Hur flyttar jag DocumentBuilder till en specifik tabellcell i ett Word-dokument?

S: För att flytta DocumentBuilder till en specifik tabellcell i ett Word-dokument kan du använda MoveToCell-metoden i klassen DocumentBuilder. Denna metod tar indexen för målraden och cellen i tabellen som parametrar och placerar markören i början av den cellen.

#### F: Kan jag lägga till eller ändra innehåll efter att ha flyttat till en specifik tabellcell med funktionen Flytta till tabellcell?

S: Ja, när DocumentBuilder är placerad vid önskad tabellcell med hjälp av MoveToCell, kan du använda olika metoder i klassen DocumentBuilder, såsom Write, Writeln eller InsertHtml, för att lägga till eller ändra innehållet i den cellen.

#### F: Hur kan jag verifiera att flytten till tabellcellen lyckades?

S: Du kan verifiera att flyttningen till tabellcellen lyckades genom att kontrollera positionen för DocumentBuilders markör. Du kan till exempel jämföra den aktuella noden i DocumentBuilder med cellen du tänkt flytta till och verifiera att innehållet som lagts till av DocumentBuilder är korrekt sparat i tabellcellen.