---
title: Lägg till Bidi Marks
linktitle: Lägg till Bidi Marks
second_title: Aspose.Words för .NET API Referens
description: Lär dig att lägga till Bidi-märken i ett Word-dokument med Aspose.Words för .NET och skapa professionella flerspråkiga dokument.
type: docs
weight: 10
url: /sv/net/programming-with-txtsaveoptions/add-bidi-marks/
---

Aspose.Words för .NET är ett kraftfullt bibliotek för att skapa, redigera och manipulera Word-dokument i en C#-applikation. Bland funktionerna som erbjuds av Aspose.Words är möjligheten att lägga till Bidi-märken (dubbelriktad) i ett dokument. I den här guiden går vi igenom hur du använder C#-källkoden för Aspose.Words för .NET för att lägga till Bidi-märken i ett dokument.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett populärt bibliotek som gör arbetet med Word-dokument enkelt och effektivt. Den erbjuder ett brett utbud av funktioner för att skapa, redigera och manipulera Word-dokument, inklusive att lägga till Bidi-märken.

## Skapa dokumentet och lägga till innehåll

Det första steget är att skapa ett nytt dokument och lägga till innehåll till det. Använd klassen Document för att skapa en ny dokumentinstans. Använd sedan klassen DocumentBuilder för att lägga till text i dokumentet. Här är ett exempel :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");
```

det här exemplet skapar vi ett nytt dokument och använder DocumentBuilder för att lägga till text. Vi har lagt till tre rader text: en på engelska, en på hebreiska och en på arabiska för att demonstrera hur man lägger till innehåll på olika språk.

## Lade till Bidi-märken

När innehållet har lagts till kan vi nu lägga till Bidi-märken i dokumentet. För detta använder vi klassen TxtSaveOptions och vi sätter egenskapen AddBidiMarks till true. Här är hur:

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

I det här exemplet skapar vi en instans av TxtSaveOptions och ställer in egenskapen AddBidiMarks på true. Därefter använder vi metoden Spara i klassen Document för att spara dokumentet med Bidi-märken.

### Exempel på källkod för "Add Bidi Marks"-funktionalitet med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och lägg till innehåll
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. Writen("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder. Writen("שלום עולם!");
builder. Writen("مرحبا بالعالم!");

// Lägg till Bidi-märken
TxtSaveOptions saveOptions = new TxtSaveOptions { AddBidiMarks = true

  };
doc.Save(dataDir + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
```

## Slutsats

den här guiden har vi förklarat hur man använder Aspose.Words för .NET för att lägga till Bidi-märken till ett Word-dokument med den medföljande C#-källkoden. Genom att följa de medföljande stegen kan du enkelt lägga till Bidi-märken till dina Word-dokument i din C#-applikation. Aspose.Words erbjuder enorm flexibilitet och kraft för att arbeta med textformatering och språkhantering, vilket gör att du kan skapa flerspråkiga dokument professionellt.