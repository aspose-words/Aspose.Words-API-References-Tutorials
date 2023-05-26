---
title: Ranges Get Text
linktitle: Ranges Get Text
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du enkelt extraherar text från ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-ranges/ranges-get-text/
---

Aspose.Words för .NET är ett kraftfullt bibliotek för att skapa, redigera och manipulera Word-dokument i en C#-applikation. Bland funktionerna som erbjuds av Aspose.Words är möjligheten att få texten i specifika områden i ett dokument. I den här guiden går vi igenom hur du använder C#-källkoden för Aspose.Words för .NET för att extrahera text från ett Word-dokument.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett populärt bibliotek som gör arbetet med Word-dokument enkelt och effektivt. Den erbjuder ett brett utbud av funktioner för att skapa, redigera och manipulera Word-dokument, inklusive extrahering av text från specifika områden.

## Laddar Word-dokumentet

Det första steget är att ladda Word-dokumentet som du vill extrahera texten från. Använd klassen Document för att ladda dokumentet från källfilen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Document.docx");
```

I det här exemplet laddar vi dokumentet "Document.docx" som finns i dokumentkatalogen.

## Extrahera text från ett specifikt intervall

När dokumentet har laddats kan du komma åt dokumentets olika intervall och extrahera önskad text. I det här exemplet extraherar vi all text från dokumentet. Här är hur:

```csharp
string text = doc.Range.Text;
```

I det här exemplet använder vi egenskapen Range för klassen Document för att komma åt hela dokumentområdet. Sedan använder vi egenskapen Text för att få texten i det intervallet.

## Visning av extraherad text

Nu när vi har extraherat texten från det angivna intervallet kan vi visa eller bearbeta den efter behov av din applikation. Du kan till exempel visa den på skärmen eller spara den i en utdatafil. Här är ett exempel för att visa den extraherade texten:

```csharp
Console.WriteLine(text);
```

I det här exemplet använder vi metoden WriteLine i klassen Console för att visa den extraherade texten i konsolen.

### Exempel på källkod för funktionen "Hämta text från intervall" med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Ladda Word-dokumentet
Document doc = new Document(dataDir + "Document.docx");

// Extrahera texten från dokumentet
string text = doc.Range.Text;

// Visa den extraherade texten
Console.WriteLine(text);
```

## Slutsats

den här guiden har vi täckt hur man använder Aspose.Words för .NET för att extrahera text från ett Word-dokument med den medföljande C#-källkoden. Genom att följa de angivna stegen kan du enkelt extrahera text från specifika områden i dina Word-dokument i ditt C#-program. Aspose.Words erbjuder enorm flexibilitet och kraft för att arbeta med dokumentinnehåll, så att du kan bearbeta och använda text enligt dina specifika behov.