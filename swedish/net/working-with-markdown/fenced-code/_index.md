---
title: Inhägnad kod
linktitle: Inhägnad kod
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder den inhägnade kodfunktionen med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/fenced-code/
---

I det här exemplet kommer vi att gå igenom hur du använder den inhägnade kodfunktionen med Aspose.Words för .NET. inhägnad kod används för att representera kodblock med specifik formatering.

## Steg 1: Använda en dokumentgenerator

Först använder vi en dokumentgenerator för att lägga till innehåll i vårt dokument.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Steg 2: Lägga till en stil för inhägnad kod

 Vi kommer att lägga till en anpassad stil för den inhägnade koden med hjälp av`Styles.Add` metod för`Document` objekt. I det här exemplet skapar vi en stil som heter "FencedCode" för den inhägnade koden.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Steg 3: Lägga till inhägnad kod utan info

Nu kan vi lägga till ett inhägnat kodblock utan informationssträng med den anpassade stilen "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Steg 4: Lägg till inhägnad kod med infosträng

Vi kan också lägga till ett inhägnat kodblock med en informationssträng med en annan anpassad stil. I det här exemplet skapar vi en stil som heter "FencedCode.C#" för att representera ett block med C#-kod.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Exempel på källkod för Fenced Code med Aspose.Words för .NET

```csharp
	// Använd en dokumentbyggare för att lägga till innehåll i dokumentet.
	DocumentBuilder builder = new DocumentBuilder();

	Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
	builder.ParagraphFormat.Style = fencedCode;
	builder.Writeln("This is an fenced code");

	Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
	builder.ParagraphFormat.Style = fencedCodeWithInfo;
	builder.Writeln("This is a fenced code with info string");
            
```


