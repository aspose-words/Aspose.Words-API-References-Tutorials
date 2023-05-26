---
title: Skapa bokmärke
linktitle: Skapa bokmärke
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar bokmärken i ett dokument och anger förhandsgranskningsnivåer för bokmärken i en PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/create-bookmark/
---

den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen Skapa bokmärke i Aspose.Words för .NET-biblioteket. Den här funktionen låter dig skapa bokmärken i ett dokument och ange förhandsgranskningsnivåer för bokmärken i en PDF-fil.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skapa dokumentet och generatorn

 Innan vi skapar bokmärken måste vi skapa ett dokument och en dokumentbyggare med hjälp av`Document` och`DocumentBuilder` föremål:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Skapa huvudbokmärket

 Vi använder`StartBookmark` metod för att starta ett huvudbokmärke och`EndBookmark` sätt att avsluta det. Däremellan kan vi lägga till text och andra bokmärken:

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

// Lägg till fler bokmärken eller text här.

builder. EndBookmark("My Bookmark");
```

## Steg 3: Skapa kapslade bokmärken

 Vi kan också skapa kapslade bokmärken inuti ett huvudbokmärke. Vi använder samma`StartBookmark` och`EndBookmark` metoder för att skapa och avsluta kapslade bokmärken:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## Steg 4: Ange förhandsgranskningsnivåer för bokmärken i PDF-filen

 Vi använder`PdfSaveOptions` objekt för att ange förhandsgranskningsnivåer för bokmärken i PDF-filen. Vi använder`BookmarksOutlineLevels` fast egendom

  för att lägga till huvudbokmärken och kapslade bokmärken med sina respektive nivåer:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Exempel på källkod för Skapa bokmärke med Aspose.Words för .NET

Här är den fullständiga källkoden som visar hur du skapar bokmärken med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Skapa bokmärke i Aspose.Words för .NET. Vi har följt en steg-för-steg-guide för att skapa bokmärken i ett dokument och ange förhandsgranskningsnivåer för bokmärken i en PDF-fil.