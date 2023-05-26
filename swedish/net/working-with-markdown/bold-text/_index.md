---
title: Fettext
linktitle: Fettext
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du gör fet text med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/bold-text/
---

I det här exemplet kommer vi att berätta för dig hur du gör fet text med Aspose.Words för .NET. Fet text gör den mer synlig och ger den mer framträdande plats.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Fet text

 Vi kan feta texten genom att ställa in dokumentbyggarens`Font.Bold` egendom till`true`.

```csharp
builder.Font.Bold = true;
```

## Steg 3: Lägg till innehåll i dokumentet

 Nu kan vi lägga till innehåll i dokumentet med hjälp av dokumentbyggarmetoderna, som t.ex`Writeln`, som lägger till en textrad.

```csharp
builder.Writeln("This text will be bold");
```

## Exempel på källkod för fet text med Aspose.Words för .NET


```csharp
	// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
	DocumentBuilder builder = new DocumentBuilder();

	// Gör texten fet.
	builder.Font.Bold = true;
	builder.Writeln("This text will be Bold");  
```

Grattis! Du har nu lärt dig hur man fet text med Aspose.Words för .NET.


