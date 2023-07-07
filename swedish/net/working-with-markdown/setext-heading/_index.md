---
title: Setext Rubrik
linktitle: Setext Rubrik
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder Setext-rubriker för att formatera dina dokument med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/setext-heading/
---

I den här handledningen går vi igenom hur du använder Setext Heading-funktionen med Aspose.Words för .NET. Setext Heading är en alternativ metod för att formatera titlar i Markdown-dokument.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Använd rubrikstilen Setext

Vi kommer att använda standardstyckestilen "Rubrik 1" för att skapa en nivå 1-rubrik i vårt dokument.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Steg 3: Återställ stilar

Vi återställer tidigare tillämpade teckensnittsstilar för att undvika oönskade kombinationer av stilar mellan stycken.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Steg 4: Anpassa Setext-rubriknivåer

Vi kan anpassa Setext-rubriknivåer genom att lägga till nya styckestilar baserat på befintliga rubrikstilar. I det här exemplet skapar vi en "SetextHeading1"-stil baserat på "Heading 1"-stilen för att representera en nivå 1-rubrik i Setext-formatet.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Steg 5: Spara dokumentet

Slutligen kan vi spara dokumentet i önskat format.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Exempel på källkod för Setext-titlar med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Återställ stilar från föregående stycke för att inte kombinera stilar mellan stycken.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Återställ stilar från föregående stycke för att inte kombinera stilar mellan stycken.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Setex-rubriknivån återställs till 2 om basstycket har en rubriknivå större än 2.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### FAQ's

#### F: Vad är en Setext Markdown-rubrik?

S: En Setext Markdown-rubrik är ett alternativt sätt att skapa rubriker i ett Markdown-dokument. Den använder understreck (= eller -) för att indikera olika nivåer av rubriker.

#### F: Hur använder man Setext Markdown-rubriker?

S: För att använda Setext Markdown-rubriker, placera understreck under titeltexten. Använd likhetstecken (=) för ett rubrik på nivå 1 och bindestreck (-) för ett rubrik på nivå 2.

#### F: Finns det några begränsningar i att använda Setext Markdown-rubriker?

S: Setext Markdown-rubriker har begränsningar när det gäller rubrikhierarki och är inte lika visuellt distinkta som vanliga Markdown-rubriker.

#### F: Kan jag anpassa utseendet på Setext Markdown-rubriker?

S: I standard Markdown är det inte möjligt att anpassa utseendet på Setext Markdown-rubriker. De har ett fördefinierat utseende baserat på de understreck som används.

#### F: Stöds Setext Markdown-rubriker av alla Markdown-redigerare?

S: Stödet för Setext Markdown-rubriker kan variera mellan Markdown-redigerare. Kontrollera din utgivares specifika dokumentation för att vara säker.