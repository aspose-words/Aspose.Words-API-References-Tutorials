---
title: Betoningar
linktitle: Betoningar
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder betoningar (fet och kursiv stil) med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/emphases/
---

I det här exemplet kommer vi att förklara hur man använder emphases med Aspose.Words för .NET. betoningar används för att framhäva vissa delar av texten, som fetstil och kursiv stil.

## Steg 1: Dokumentinitiering

 Först initierar vi dokumentet genom att skapa en instans av`Document` klass.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Steg 2: Använda en dokumentgenerator

Därefter använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Lägg till text med betoningar

Vi kan lägga till betoningstext genom att ändra dokumentgeneratorns teckensnittsegenskaper. I det här exemplet använder vi fetstil och kursiv stil för att framhäva olika delar av texten.

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## Steg 4: Spara dokumentet

 Slutligen kan vi spara dokumentet i önskat format. I det här exemplet använder vi`.md` tillägg för ett Markdown-format.

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

Grattis! Du har nu lärt dig hur du använder emphases med Aspose.Words för .NET.

### Exempel på källkod för emphases med Aspose.Words för .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### FAQ's

#### F: Hur markerar jag text med Markdown?

 S: För att markera text med Markdown, omge bara texten med lämpliga symboler. Använda sig av`*` eller`_` för kursiv stil,`**` eller`__` för fetstil, och`~~` för genomstrykning.

#### F: Kan vi kombinera olika höjdpunkter i samma text?

 S: Ja, det är möjligt att kombinera olika höjdpunkter i samma text. Du kan till exempel göra ett ord i fetstil och kursiv stil genom att använda båda`**`och`*` runt ordet.

#### F: Vilka framhävningsalternativ finns i Markdown?

A: Markeringsalternativ som är tillgängliga i Markdown är kursiv (`*` eller`_`), fet (`**` eller`__`), och genomstruken (`~~`).

#### F: Hur hanterar jag fall där texten innehåller specialtecken som används av Markdown för att markera?

 S: Om din text innehåller specialtecken som används av Markdown för att markera, kan du undvika dem genom att föregå dem med en`\` . Till exempel,`\*` kommer att visa en bokstavlig asterisk.

#### F: Kan vi anpassa utseendet på markering med CSS?

S: Markering i Markdown renderas vanligtvis med webbläsarens standardstilar. Om du konverterar din Markdown till HTML kan du anpassa utseendet på markeringen med hjälp av CSS-regler.