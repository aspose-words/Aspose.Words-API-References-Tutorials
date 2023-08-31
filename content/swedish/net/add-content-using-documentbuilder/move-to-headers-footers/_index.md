---
title: Flytta till sidhuvuden Sidfötter i Word-dokument
linktitle: Flytta till sidhuvuden Sidfötter i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder Aspose.Words för .NET för att navigera och ändra sidhuvuden och sidfötter i Word-dokument med denna steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/move-to-headers-footers/
---
I det här exemplet kommer vi att utforska funktionen Move To Headers Footers i Aspose.Words för .NET. Aspose.Words är ett kraftfullt dokumentmanipuleringsbibliotek som låter utvecklare skapa, modifiera och konvertera Word-dokument programmatiskt. Funktionen Flytta till sidhuvuden/sidfötter gör att vi kan navigera till olika sidhuvuden och sidfötter i ett dokument och lägga till innehåll till dem.

Låt oss gå igenom källkoden steg för steg för att förstå hur man använder funktionen Flytta till sidhuvuden/sidfot med Aspose.Words för .NET.

## Steg 1: Initiera dokument- och dokumentbyggaren

Initiera först Document- och DocumentBuilder-objekten:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Konfigurera sidhuvuden och sidfötter

Ange inställningar för sidhuvud/sidfot för dokumentet. I det här exemplet ställer vi in sidhuvuden och sidfötter så att de är olika för första sidan och för udda/jämna sidor:

```csharp
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;
```

## Steg 3: Skapa rubriker för olika sidor

Flytta till varje rubriktyp och lägg till innehåll till dem. I det här exemplet skapar vi rubriker för första sidan, jämna sidor och alla andra sidor:

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");

builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");
```

## Steg 4: Skapa sidor i dokumentet
Lägg till innehåll i dokumentet för att skapa flera sidor. Till exempel:

```csharp
// Skapa två sidor i dokumentet.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");
```
## Steg 5: Spara dokumentet

Spara det ändrade dokumentet på önskad plats:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

Se till att ange lämplig sökväg och filformat (t.ex. DOCX).

### Exempel på källkod för Flytta till sidhuvuden/sidfötter med Aspose.Words för .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

//Ange att vi vill ha olika sidhuvuden och sidfötter för första, jämna och udda sidor.
builder.PageSetup.DifferentFirstPageHeaderFooter = true;
builder.PageSetup.OddAndEvenPagesHeaderFooter = true;

// Skapa rubrikerna.
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.Write("Header for the first page");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderEven);
builder.Write("Header for even pages");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Header for all other pages");

// Skapa två sidor i dokumentet.
builder.MoveToSection(0);
builder.Writeln("Page1");
builder.InsertBreak(BreakType.PageBreak);
builder.Writeln("Page2");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
```

## Slutsats

I det här exemplet utforskade vi funktionen Flytta till sidhuvuden/sidfot i Aspose.Words för .NET. Vi lärde oss att navigera till olika sidhuvuden och sidfötter i ett Word-dokument och lägga till innehåll till dem med hjälp av klassen DocumentBuilder. Den här funktionen tillåter utvecklare att anpassa sidhuvuden och sidfötter för specifika sidor eller avsnitt, vilket ger flexibilitet när det gäller att skapa professionella och strukturerade dokument. Aspose.Words för .NET tillhandahåller en kraftfull uppsättning verktyg för programmatisk manipulering av Word-dokument, vilket gör det till ett viktigt bibliotek för dokumentbehandlingsprogram.

### Vanliga frågor för att flytta till sidhuvudena sidfötter i word-dokument

#### F: Vad är syftet med funktionen Flytta till sidhuvuden/sidfot i Aspose.Words för .NET?

S: Funktionen Flytta till sidhuvuden/sidfot i Aspose.Words för .NET tillåter utvecklare att navigera till olika sidhuvuden och sidfötter i ett Word-dokument och lägga till innehåll till dem programmatiskt. Det är användbart när du behöver anpassa sidhuvuden och sidfötter för olika sidor eller avsnitt i dokumentet.

#### F: Kan jag ha olika sidhuvuden och sidfötter för olika sidor i dokumentet?

S: Ja, du kan ange olika sidhuvuden och sidfötter för första sidan, jämna sidor och udda sidor med egenskaperna PageSetup.DifferentFirstPageHeaderFooter respektive PageSetup.OddAndEvenPagesHeaderFooter.

#### F: Hur kan jag lägga till innehåll i specifika sidhuvuden och sidfötter?

S: För att lägga till innehåll till specifika sidhuvuden och sidfötter, använd MoveToHeaderFooter-metoden i klassen DocumentBuilder. Du kan flytta till sidhuvudena HeaderFirst, HeaderEven och HeaderPrimary eller FooterFirst, FooterEven och FooterPrimary baserat på dina krav.

#### F: Kan jag skapa sidhuvuden och sidfötter för ett specifikt avsnitt i dokumentet?

S: Ja, du kan använda metoden MoveToSection i klassen DocumentBuilder för att flytta till en specifik sektion i dokumentet och sedan skapa sidhuvuden och sidfötter inom det avsnittet.

#### F: Hur kan jag spara det ändrade dokumentet till en fil med Aspose.Words för .NET?

S: Du kan spara det ändrade dokumentet på önskad plats och format med hjälp av Spara-metoden för klassen Document. Se till att ange lämplig sökväg och filformat (t.ex. DOCX).