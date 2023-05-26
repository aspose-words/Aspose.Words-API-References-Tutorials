---
title: Tabell
linktitle: Tabell
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar en tabell med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/table/
---


I det här exemplet kommer vi att gå igenom hur du skapar en tabell med Aspose.Words för .NET. En tabell är en datastruktur som organiserar information i rader och kolumner.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```


## Steg 2: Lägg till celler och data

 Vi kommer att lägga till celler och data till vår tabell med hjälp av`InsertCell` metoden och`Writeln` dokumentgeneratorns metod.

```csharp
builder. InsertCell();
builder.Writeln("a");
builder. InsertCell();
builder.Writeln("b");

builder. InsertCell();
builder.Writeln("c");
builder. InsertCell();
builder.Writeln("d");
```

### Exempel på källkod för att skapa en tabell med Aspose.Words för .NET

```csharp
	// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
	DocumentBuilder builder = new DocumentBuilder();

	// Lägg till den första raden.
	builder.InsertCell();
	builder.Writeln("a");
	builder.InsertCell();
	builder.Writeln("b");

	// Lägg till den andra raden.
	builder.InsertCell();
	builder.Writeln("c");
	builder.InsertCell();
	builder.Writeln("d");
            
```

Grattis! Du har nu lärt dig hur du skapar en tabell med Aspose.Words för .NET.
