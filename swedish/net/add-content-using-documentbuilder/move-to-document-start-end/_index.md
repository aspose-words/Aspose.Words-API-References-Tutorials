---
title: Flytta till dokumentets startslut
linktitle: Flytta till dokumentets startslut
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder Aspose.Words för .NET för att flytta till dokumentets start och slut i Word-dokument med denna steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/add-content-using-documentbuilder/move-to-document-start-end/
---

det här exemplet kommer vi att utforska funktionen Flytta till dokument start/slut i Aspose.Words för .NET. Aspose.Words är ett kraftfullt dokumentmanipuleringsbibliotek som låter utvecklare skapa, modifiera och konvertera Word-dokument programmatiskt. Funktionen Flytta till dokument start/slut gör att vi kan navigera till början eller slutet av ett dokument med klassen DocumentBuilder.

## Förklara källkoden steg för steg

Låt oss gå igenom källkoden steg för steg för att förstå hur man använder funktionen Move To Document Start/End med Aspose.Words för .NET.


## Steg 1: Initiera dokument- och dokumentbyggaren

Initiera sedan Document- och DocumentBuilder-objekten:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Flytta till dokumentstart

För att flytta markörens position till början av dokumentet, använd metoden MoveToDocumentStart i klassen DocumentBuilder:

```csharp
builder.MoveToDocumentStart();
```

## Steg 3: Flytta till dokumentslutet

För att flytta markörens position till slutet av dokumentet, använd metoden MoveToDocumentEnd i klassen DocumentBuilder:

```csharp
builder.MoveToDocumentEnd();
```

## Steg 4: Mata ut markörens position

Du kan mata ut markörpositionen med Console.WriteLine eller någon annan önskad metod. Till exempel:

```csharp
Console.WriteLine("\nThis is the beginning of the document.");
Console.WriteLine("\nThis is the end of the document.");
```

### Exempel på källkod för Move To Document Start/End med Aspose.Words för .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Flytta markörpositionen till början av ditt dokument.
builder.MoveToDocumentStart();
Console.WriteLine("\nThis is the beginning of the document.");

// Flytta markörens position till slutet av dokumentet.
builder.MoveToDocumentEnd();
Console.WriteLine("\nThis is the end of the document.");
```

## Slutsats

I det här exemplet har vi utforskat funktionen Flytta till dokument start/slut i Aspose.Words för .NET. Vi lärde oss hur man navigerar till början och slutet av ett dokument med klassen DocumentBuilder. Den här funktionen är användbar när du programmerar ordbehandling med Word-dokument och behöver manipulera eller infoga innehåll på specifika positioner i dokumentet.