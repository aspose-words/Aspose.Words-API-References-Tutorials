---
title: Indragen kod
linktitle: Indragen kod
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder indragen kod med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/indented-code/
---

I det här exemplet kommer vi att förklara hur man använder den indragna kodfunktionen med Aspose.Words för .NET. Indragen kod används för att visuellt representera kodblock med specifik formatering.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Lägg till stil för indragen kod

 Vi kommer att lägga till en anpassad stil för den indragna koden med hjälp av`Styles.Add` metod för`Document` objekt. I det här exemplet skapar vi en stil som heter "IndentedCode" för indragen kod.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Steg 3: Lägg till indragen kod

Nu kan vi lägga till ett indraget kodblock med den anpassade stilen "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Exempel på källkod för indragen kod med Aspose.Words för .NET

```csharp
	// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
	DocumentBuilder builder = new DocumentBuilder();

	Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
	builder.ParagraphFormat.Style = indentedCode;
	builder.Writeln("This is an indented code");
            
```

Grattis! Du har nu lärt dig hur du använder den indragna kodfunktionen med Aspose.Words för .NET.

