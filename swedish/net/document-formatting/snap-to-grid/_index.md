---
title: Snap To Grid
linktitle: Snap To Grid
second_title: Aspose.Words Document Processing API
description: Steg för steg guide för att förklara C#-källkoden för Snap to Grid-funktionen med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/snap-to-grid/
---

I den här handledningen går vi igenom hur du använder funktionen Snap to Grid med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa ändringarna.

## Steg 1: Skapa och konfigurera dokumentet

Börja med att skapa ett nytt dokument och ett tillhörande DocumentBuilder-objekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Rutnätsjustering

Nu kommer vi att tillämpa rutnätsjustering på ett specifikt stycke och teckensnittet som används i stycket. Här är hur:

```csharp
// Aktivera rutnätsjustering för stycket
Paragraph by = doc.FirstSection.Body.FirstParagraph;
par.ParagraphFormat.SnapToGrid = true;

// Skriv text i stycket
builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod" +
                 "tempor incident ut labore et dolore magna aliqua.");

// Aktivera rutnätsjustering för teckensnittet som används i stycket
par.Runs[0].Font.SnapToGrid = true;
```

## Steg 3: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save` metod. Se till att ange rätt sökväg:

```csharp
doc.Save(dataDir + "Paragraph.SnapToGrid.docx");
```

### Exempel på källkod för Snap To Grid med Aspose.Words för .NET

Här är den fullständiga källkoden för Snap to Grid-funktionen med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Optimera layouten när du skriver med asiatiska tecken.
	Paragraph par = doc.FirstSection.Body.FirstParagraph;
	par.ParagraphFormat.SnapToGrid = true;

	builder.Writeln("Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod " +
					"tempor incididunt ut labore et dolore magna aliqua.");
	
	par.Runs[0].Font.SnapToGrid = true;

	doc.Save(dataDir + "Paragraph.SnapToGrid.docx");

```

Med denna kod kommer du att kunna anpassa din text till rutnätet och optimera utseendet på ditt dokument med Aspose.Words för .NET.

