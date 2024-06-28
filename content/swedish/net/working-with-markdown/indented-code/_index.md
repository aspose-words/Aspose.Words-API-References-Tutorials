---
title: Indragen kod
linktitle: Indragen kod
second_title: Aspose.Words Document Processing API
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

## Steg 2: Lägg till stil för angiven kod

Vi kommer att lägga till en anpassad stil för den indragna koden med hjälp av`Styles.Add` metod för`Document` objekt. I det här exemplet skapar vi en stil som heter "IndentedCode" för indragen kod.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Steg 3: Lägg till angiven kod

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


### FAQ's

#### F: Vad är specificerad kod i Markdown?

S: Indragen kod i Markdown är en formateringsmetod som används för att visa kod i ett Markdown-dokument. Den består av att indraga varje kodrad med mellanslag eller tabbar.

#### F: Hur använder man indragen kod i Markdown?

S: För att använda indragen kod i Markdown, dra in varje kodrad med mellanslag eller tabb.

#### F: Vilka är fördelarna med indragen kod i Markdown?

S: Indragen kod i Markdown förbättrar kodens läsbarhet och gör det lättare för läsarna att förstå.

#### F: Vad är skillnaden mellan indragen kod och kodblock i Markdown?

S: Indragen kod används för små kodavsnitt som infogas i text, medan kodblock används för att visa större kodbitar i separat formatering.

#### F: Stöds indragen kod i Markdown av alla Markdown-redigerare?

S: Stöd för indragen kod i Markdown kan variera mellan Markdown-redigerare. Kontrollera din utgivares specifika dokumentation för att vara säker.