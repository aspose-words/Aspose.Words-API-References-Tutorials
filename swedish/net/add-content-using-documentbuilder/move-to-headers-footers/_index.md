---
title: Flytta till sidhuvuden Sidfötter
linktitle: Flytta till sidhuvuden Sidfötter
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder Aspose.Words för .NET för att navigera och ändra sidhuvuden och sidfötter i Word-dokument med denna steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/move-to-headers-footers/
---

det här exemplet kommer vi att utforska funktionen Move To Headers Footers i Aspose.Words för .NET. Aspose.Words är ett kraftfullt dokumentmanipuleringsbibliotek som låter utvecklare skapa, modifiera och konvertera Word-dokument programmatiskt. Funktionen Flytta till sidhuvuden/sidfötter gör att vi kan navigera till olika sidhuvuden och sidfötter i ett dokument och lägga till innehåll till dem.

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

// Ange att vi vill ha olika sidhuvuden och sidfötter för första, jämna och udda sidor.
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
