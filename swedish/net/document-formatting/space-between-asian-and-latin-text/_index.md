---
title: Utrymmet mellan asiatisk och latinsk text
linktitle: Utrymmet mellan asiatisk och latinsk text
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du automatiskt justerar utrymmet mellan asiatisk och latinsk text i ditt dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/space-between-asian-and-latin-text/
---

I den här handledningen kommer vi att visa dig hur du använder Space-funktionen mellan asiatisk och latinsk text med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa ändringarna.

## Steg 1: Skapa och konfigurera dokumentet

Börja med att skapa ett nytt dokument och ett tillhörande DocumentBuilder-objekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Ställ in utrymmet mellan asiatisk och latinsk text

Vi kommer nu att konfigurera utrymmet mellan asiatisk och latinsk text med hjälp av egenskaperna för objektet ParagraphFormat. Här är hur:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Steg 3: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save` metod. Se till att ange rätt sökväg:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Exempel på källkod för Space Between Asian And Latin Text med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen Space Between Asian and Latin Text med Aspose.Words för .NET:


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	ParagraphFormat paragraphFormat = builder.ParagraphFormat;
	paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
	paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

	builder.Writeln("Automatically adjust space between Asian and Latin text");
	builder.Writeln("Automatically adjust space between Asian text and numbers");

	doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
        
```

Med denna kod kommer du att automatiskt kunna justera utrymmet mellan asiatisk och latinsk text i ditt dokument med Aspose.Words för .NET.



