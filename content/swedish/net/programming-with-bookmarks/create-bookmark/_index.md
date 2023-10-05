---
title: Skapa bokmärke i Word-dokument
linktitle: Skapa bokmärke i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar bokmärken i Word-dokument och anger förhandsgranskningsnivåer för bokmärken i en PDF med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-bookmarks/create-bookmark/
---

I den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen Skapa bokmärke i Aspose.Words för .NET-biblioteket. Den här funktionen låter dig skapa bokmärken i ett dokument och ange förhandsgranskningsnivåer för bokmärken i en PDF-fil.

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

### Vanliga frågor

#### F: Vilka är förutsättningarna för att använda funktionen "Skapa bokmärken" i Aspose.Words för .NET?

S: För att använda funktionen "Skapa bokmärken" i Aspose.Words för .NET måste du ha grundläggande kunskaper i C#-språket. Du behöver också en .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

#### F: Hur skapar man ett dokument i Aspose.Words för .NET?

 S: För att skapa ett dokument i Aspose.Words för .NET kan du använda`Document` klass. Här är en exempelkod:

```csharp
Document doc = new Document();
```

#### F: Hur skapar man ett huvudbokmärke i ett dokument med Aspose.Words för .NET?

 S: För att skapa ett huvudbokmärke i ett dokument med Aspose.Words för .NET, kan du använda`StartBookmark` sätt att starta bokmärket, lägg till text eller andra bokmärken inuti och använd sedan` EndBookmark` att avsluta det. Här är en exempelkod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### F: Hur skapar man ett kapslat bokmärke i ett huvudbokmärke med Aspose.Words för .NET?

 S: För att skapa ett kapslat bokmärke i ett huvudbokmärke med Aspose.Words för .NET, kan du använda samma`StartBookmark` och`EndBookmark` metoder för att starta och avsluta det kapslade bokmärket. Här är en exempelkod:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### F: Hur anger man förhandsgranskningsnivåer för bokmärken i en utdata-PDF med Aspose.Words för .NET?

 S: För att ange förhandsgranskningsnivåer för bokmärken i en utdata-PDF med Aspose.Words för .NET, kan du använda`PdfSaveOptions` klass och`BookmarksOutlineLevels` fast egendom. Du kan lägga till huvudbokmärken och kapslade bokmärken med sina respektive nivåer. Här är en exempelkod:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### F: Hur sparar man ett dokument efter att ha skapat bokmärken med Aspose.Words för .NET?

 S: För att spara ett dokument efter att ha skapat bokmärken med Aspose.Words för .NET, kan du använda`Save` metod för`Document` objekt som anger destinationsfilens sökväg. Här är en exempelkod:

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### F: Hur anger man förhandsgranskningsnivåer för bokmärken i en utdata-PDF med Aspose.Words för .NET?

 S: För att ange förhandsgranskningsnivåer för bokmärken i en utdata-PDF med Aspose.Words för .NET, kan du använda`PdfSaveOptions` klass och`BookmarksOutlineLevels` fast egendom. Du kan lägga till huvudbokmärken och kapslade bokmärken med sina respektive nivåer. Här är en exempelkod:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### F: Hur skapar man kapslade bokmärken i ett huvudbokmärke med Aspose.Words för .NET?

 S: För att skapa kapslade bokmärken i ett huvudbokmärke med Aspose.Words för .NET, kan du använda samma`StartBookmark` och`EndBookmark` metoder för att starta och avsluta kapslade bokmärken. Var noga med att ange det överordnade bokmärket som en parameter när du anropar`StartBookmark` metod. Här är en exempelkod:

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### F: Hur lägger man till text i ett bokmärke med Aspose.Words för .NET?

 S: För att lägga till text i ett bokmärke med Aspose.Words för .NET, kan du använda`Write` metod för`DocumentBuilder`objekt som anger texten som ska läggas till. Här är en exempelkod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### F: Hur skapar man ett huvudbokmärke i ett dokument med Aspose.Words för .NET?

 S: För att skapa ett huvudbokmärke i ett dokument med Aspose.Words för .NET, kan du använda`StartBookmark` metod för att starta bokmärket och`EndBookmark` sätt att avsluta det. Här är en exempelkod:

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```