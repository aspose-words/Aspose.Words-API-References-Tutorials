---
title: Flytta till bokmärkesslut
linktitle: Flytta till bokmärkesslut
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder Aspose.Words för .NET för att flytta till slutet av ett bokmärke i Word-dokument med denna steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/move-to-bookmark-end/
---

det här exemplet kommer vi att utforska funktionen Move To Bookmark End i Aspose.Words för .NET. Aspose.Words är ett kraftfullt dokumentmanipuleringsbibliotek som gör det möjligt för utvecklare att skapa, ändra och konvertera Word-dokument programmatiskt. Funktionen Flytta till bokmärkesslut låter oss navigera till slutet av ett specifikt bokmärke i ett dokument och lägga till innehåll efter det.

## Att sätta upp miljön

Innan vi går in i implementeringsdetaljerna, låt oss se till att vi har den nödvändiga miljön inställd för att fungera med Aspose.Words för .NET. Se till att du har följande:

- En fungerande installation av Aspose.Words för .NET-biblioteket
- Grundläggande kunskaper i programmeringsspråket C#
- Tillgång till en .NET-utvecklingsmiljö

## Förstå funktionen Move To Bookmark End i Aspose.Words för .NET

Funktionen Flytta till bokmärkesslut låter dig navigera till slutet av ett bokmärke i ett Word-dokument med Aspose.Words för .NET. Den här funktionen är användbar när du vill lägga till innehåll efter ett specifikt bokmärke i ditt dokument programmatiskt.

## Förklara källkoden steg för steg

Låt oss dela upp den medföljande källkoden steg för steg för att förstå hur man använder funktionen Flytta till bokmärkesslut i Aspose.Words för .NET.

## Steg 1: Initiera dokument- och dokumentbyggaren

 Först måste vi initiera`Document` och`DocumentBuilder` föremål:

```csharp
Document doc = new Document(MyDir + "Bookmarks.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Flytta till bokmärkesslutet

 För att flytta till slutet av ett bokmärke, använd`MoveToBookmark` metod för`DocumentBuilder` klass:

```csharp
builder.MoveToBookmark("MyBookmark1", false, true);
```

 De`MoveToBookmark` Metoden tar tre parametrar:
- Bokmärkesnamn: Ange namnet på bokmärket du vill flytta till.
-  IsBookmarkStart: Ställ in på`false` för att flytta till slutet av bokmärket.
-  IsBookmarkEnd: Ställ in på`true` för att indikera att du vill flytta till bokmärkesänden.

## Steg 3: Lägg till innehåll i bokmärkesänden

När du har flyttat till bokmärkesänden kan du lägga till innehåll med de olika metoderna som tillhandahålls av`DocumentBuilder` klass. I det här exemplet använder vi`Writeln` metod för att skriva en textrad:

```csharp
builder.Writeln("This is a bookmark.");
```

 De`Writeln` metod lägger till den angivna texten som ett nytt stycke vid den aktuella positionen för`DocumentBuilder`.

### Exempel på källkod för Move To Bookmark End med Aspose.Words för .NET

```csharp

	Document doc = new Document(MyDir + "Bookmarks.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.MoveToBookmark("MyBookmark1", false, true);
	builder.Writeln("This is a bookmark.");
	
```

## Slutsats

vi utforskade funktionen Move To Bookmark End i Aspose.Words för .NET. Vi lärde oss hur man navigerar till slutet av ett bokmärke och lägger till innehåll programmatiskt med hjälp av den medföljande källkoden. Den här funktionen ger flexibilitet vid manipulering av Word-dokument med Aspose.Words för .NET.

