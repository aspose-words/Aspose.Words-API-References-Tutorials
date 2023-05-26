---
title: Rubrik
linktitle: Rubrik
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder heading med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/heading/
---

I det här exemplet kommer vi att visa dig hur du använder rubrikfunktionen med Aspose.Words för .NET. Rubriker används för att strukturera och prioritera innehållet i ett dokument.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Anpassa rubrikstilar

Som standard kan rubrikstilar i Word ha fet och kursiv formatering. Om vi inte vill att dessa egenskaper ska tillämpas måste vi uttryckligen ställa in dem på "false".

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Steg 3: Lägga till en nivå 1-titel

 Vi kan lägga till en nivå 1-titel genom att ange lämpligt styckeformatnamn och använda`Writeln` metod för att skriva innehållet i titeln.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

### Exempel på källkod för rubrik med Aspose.Words för .NET


```csharp
	// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
	DocumentBuilder builder = new DocumentBuilder();

	// Som standard kan rubrikstilar i Word ha fet och kursiv formatering.
	//Om vi inte vill framhävas, ställ dessa egenskaper uttryckligen till false.
	builder.Font.Bold = false;
	builder.Font.Italic = false;

	builder.ParagraphFormat.StyleName = "Heading 1";
	builder.Writeln("This is an H1 tag");
            
```

Grattis! Du har nu lärt dig hur du använder rubrikfunktionen med Aspose.Words för .NET.


