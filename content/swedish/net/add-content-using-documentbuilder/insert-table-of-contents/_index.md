---
title: Infoga innehållsförteckning i Word-dokument
linktitle: Infoga innehållsförteckning i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du infogar en innehållsförteckning i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/insert-table-of-contents/
---
I den här omfattande handledningen kommer du att lära dig hur du infogar en innehållsförteckning i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna skapa en innehållsförteckning med lämpliga rubriker och sidnummer.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och DocumentBuilder
För att börja, skapa ett nytt dokument med klassen Document och initiera ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga en innehållsförteckning
Använd sedan metoden InsertTableOfContents i klassen DocumentBuilder för att infoga en innehållsförteckning. Ange de nödvändiga formateringsalternativen inom metoden:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Steg 3: Lägg till dokumentinnehåll
När du har infogat innehållsförteckningen lägger du till det faktiska dokumentinnehållet. Ställ in lämpliga rubrikstilar med StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Steg 4: Uppdatera innehållsförteckningen
Den nyligen infogade innehållsförteckningen kommer till en början att vara tom. För att fylla i det, uppdatera fälten i dokumentet:

```csharp
doc.UpdateFields();
```

## Steg 5: Spara dokumentet
Efter att ha infogat innehållsförteckningen och uppdaterat fälten, spara dokumentet till en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Exempel på källkod för Infoga innehållsförteckning med Aspose.Words för .NET
Här är den fullständiga källkoden för att infoga en innehållsförteckning med Aspose.Words för .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initiera DocumentBuilder med Document-objekt
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga innehållsförteckninga
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Starta själva dokumentinnehållet på den andra sidan.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// Den nyligen infogade innehållsförteckningen kommer till en början att vara tom.
// Den måste fyllas i genom att uppdatera fälten i dokumentet.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Slutsats

Grattis! Du har framgångsrikt lärt dig hur du infogar en innehållsförteckning i ett Word-dokument med Aspose.Words för .NET. Genom att följa denna steg-för-steg-guide och använda den medföljande källkoden kan du nu skapa en innehållsförteckning med lämpliga rubriker och sidnummer för dina dokument.

### Vanliga frågor för att infoga innehållsförteckning i word-dokument

#### F: Kan jag anpassa utseendet på innehållsförteckningen?

 S: Ja, du kan anpassa utseendet på innehållsförteckningen genom att ändra formateringsalternativen som anges i`InsertTableOfContents` metod. Parametrarna låter dig styra sidnummer, indrag och andra stilar.

#### F: Vad händer om jag vill inkludera specifika rubriknivåer i innehållsförteckningen?

 S: Du kan ange önskade rubriknivåer som ska inkluderas i innehållsförteckningen genom att justera värdet inom`InsertTableOfContents` metod. Till exempel att använda`"\\o \"1-3\""` kommer att innehålla rubriknivåerna 1 till 3.

#### F: Kan jag uppdatera innehållsförteckningen automatiskt om jag gör ändringar i dokumentets innehåll?

 S: Ja, du kan uppdatera innehållsförteckningen automatiskt genom att ringa`UpdateFields` metod på dokumentet. Detta säkerställer att alla ändringar som görs i dokumentinnehållet, som att lägga till eller ta bort rubriker, återspeglas i innehållsförteckningen.

#### F: Hur kan jag utforma rubriknivåerna i innehållsförteckningen annorlunda?

 S: Du kan utforma rubriknivåerna olika genom att använda olika styckestilar för varje rubriknivå. Genom att tilldela olika`StyleIdentifier` värden till`ParagraphFormat` av`DocumentBuilder`, kan du skapa distinkta stilar för varje rubriknivå.

#### F: Är det möjligt att lägga till ytterligare formatering till rubrikerna i innehållsförteckningen?

 S: Ja, du kan lägga till ytterligare formatering till rubrikerna i innehållsförteckningen, som typsnittsstilar, färger eller andra egenskaper. Genom att justera`Font` egenskaper hos`DocumentBuilder`, kan du använda anpassad formatering på rubrikerna.