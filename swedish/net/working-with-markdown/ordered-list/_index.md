---
title: Beställd lista
linktitle: Beställd lista
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar en ordnad lista med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/ordered-list/
---

I det här exemplet kommer vi att förklara hur man använder den ordnade listfunktionen med Aspose.Words för .NET. Ordnad lista låter dig organisera objekt sekventiellt med siffror.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att skapa ett nytt dokument.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Tillämpa det beställda listformatet

Vi kommer att tillämpa det beställda listformatet med hjälp av dokumentbyggarens`ApplyBulletDefault` metod. Vi kan också anpassa numreringsformatet genom att gå till listnivåerna och ställa in det format vi vill ha.

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## Steg 3: Lägga till objekt i listan

 Vi kan lägga till objekt till listan med hjälp av dokumentgeneratorns`Writeln` metod.

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## Steg 4: Gör indrag i listan

 Vi kan dra in listan med hjälp av dokumentgeneratorns`ListIndent` metod.

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## Steg 5: Spara dokumentet

Slutligen kan vi spara dokumentet i önskat format.

### Exempel på källkod för beställd lista med Aspose.Words för .NET

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.ListFormat.ApplyBulletDefault();
	builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
	builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

	builder.Writeln("Item 1");
	builder.Writeln("Item 2");

	builder.ListFormat.ListIndent();

	builder.Writeln("Item 2a");
	builder.Writeln("Item 2b");
            
```

Grattis! Du har nu lärt dig hur du använder den beställda listfunktionen med Aspose.Words för .NET.

