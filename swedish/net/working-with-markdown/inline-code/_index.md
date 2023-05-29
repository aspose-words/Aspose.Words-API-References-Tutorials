---
title: Inline kod
linktitle: Inline kod
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar kod med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/inline-code/
---

I det här exemplet kommer vi att gå igenom hur du använder inline-kodfunktionen med Aspose.Words för .NET. Inline-kod används för att visuellt representera kodbitar inuti ett stycke.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Lägg till stil för inline-kod

 Vi kommer att lägga till en anpassad stil för inline-koden med hjälp av`Styles.Add` metod för`Document` objekt. I det här exemplet skapar vi en stil som heter "InlineCode" för inline-kod med en standardbacktick.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Steg 3: Lägg till inline-kod

Nu kan vi lägga till inline-kod med den anpassade stilen "InlineCode". I det här exemplet lägger vi till två textstycken med olika antal backticks.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Exempel på källkod för Inline Code med Aspose.Words för .NET

```csharp
// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
DocumentBuilder builder = new DocumentBuilder();

//Antal backticks saknas, en backtick kommer att användas som standard.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Det blir 3 backticks.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Grattis! Du har nu lärt dig hur du använder inline-kodfunktionalitet med Aspose.Words för .NET.

