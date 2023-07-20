---
title: Listformatering på flera nivåer i Word-dokument
linktitle: Listformatering på flera nivåer i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du skapar en flernivålista och tillämpar anpassad formatering i word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/document-formatting/multilevel-list-formatting/
---
I den här handledningen kommer vi att visa dig hur du använder listformatering på flera nivåer i Word-dokument med Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och tillämpa ändringarna.

## Steg 1: Skapa och konfigurera dokumentet

Börja med att skapa ett nytt dokument och ett tillhörande DocumentBuilder-objekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Formatera flernivålistan

Vi kommer nu att tillämpa listformateringen på flera nivåer med metoderna som är tillgängliga i DocumentBuilder-objektet. Här är hur:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Steg 3: Spara dokumentet

 När du har infogat formulärfältet för textinmatning sparar du dokumentet på önskad plats med hjälp av`Save` metod. Se till att ange rätt sökväg:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Exempel på källkod för multilevel listformatering med Aspose.Words för .NET

Här är den fullständiga källkoden för listformateringsfunktionen med flera nivåer med Aspose.Words för .NET:


```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Med den här koden kommer du att kunna skapa en flernivålista och tillämpa korrekt formatering på varje nivå med Aspose.Words för .NET.


## Slutsats

I den här handledningen har vi utforskat processen för att använda funktionen för formatering av listor på flera nivåer i ett Word-dokument med Aspose.Words för .NET. Genom att följa de skisserade stegen kan du skapa välorganiserade listor med flera nivåer, vilket förbättrar strukturen och läsbarheten för dina dokument.

### FAQ's

#### F: Vad är en flernivålista i ett Word-dokument?

S: En flernivålista i ett Word-dokument är en hierarkisk lista som låter dig organisera objekt i olika nivåer av underobjekt. Det hjälper till att presentera information på ett strukturerat sätt, vilket gör det lättare för läsare att förstå innehållet.

#### F: Kan jag anpassa utseendet på flernivålistan?

S: Ja, du kan anpassa utseendet på flernivålistan i ditt Word-dokument. Genom att använda olika stilar, som punktpunkter, siffror eller bokstäver, och justera indrag och avstånd, kan du skapa en visuellt tilltalande och organiserad lista.

#### F: Stöder Aspose.Words for .NET andra listformateringsalternativ?

S: Ja, Aspose.Words för .NET tillhandahåller en omfattande uppsättning funktioner för listformatering. Den stöder olika listtyper, inklusive punktlistor, numrerade listor och flernivålistor. Du kan manipulera formateringen av listor, lägga till eller ta bort objekt och anpassa deras utseende.

#### F: Kan jag använda Aspose.Words för .NET för att arbeta med andra dokumentelement?

S: Ja, Aspose.Words för .NET erbjuder omfattande möjligheter för att arbeta med olika dokumentelement, såsom stycken, tabeller, bilder och mer. Det gör att du kan skapa, ändra och konvertera Word-dokument programmatiskt, vilket effektiviserar dokumentbearbetningsuppgifterna.