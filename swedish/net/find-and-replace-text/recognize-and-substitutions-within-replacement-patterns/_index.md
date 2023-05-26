---
title: Känn igen och ersättningar inom ersättningsmönster
linktitle: Känn igen och ersättningar inom ersättningsmönster
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du använder ersättningsmönster med igenkänningar och ersättningar i Aspose.Words för .NET för att manipulera Word-dokument.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/recognize-and-substitutions-within-replacement-patterns/
---

I den här artikeln kommer vi att utforska ovanstående C#-källkod för att förstå hur man använder funktionen Recognize And Substitutions Within Replacement Patterns i Aspose.Words för .NET-biblioteket. Den här funktionen hjälper till att känna igen komplexa sökmönster och utföra ersättningar baserat på grupper som fångats under dokumentmanipulation.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skapa ett nytt dokument

 Innan vi börjar använda matchningar och ersättningar i ersättningsmönster måste vi skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt:

```csharp
Document doc = new Document();
```

## Steg 2: Infoga text i dokumentet

 När vi har ett dokument kan vi infoga text med hjälp av a`DocumentBuilder`objekt. I vårt exempel använder vi`Write` metod för att infoga frasen "Jason ger Paul lite pengar." :

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Write("Jason gives money to Paul.");
```

## Steg 3: Igenkännanden och ersättningar i ersättningsmönster

 Nu kommer vi att använda`Range.Replace` funktion för att utföra textsökning och ersätta med ett reguljärt uttryck för att känna igen specifika mönster. I vårt exempel använder vi det reguljära uttrycket`([A-z]+) gives money to ([A-z]+)` att känna igen meningar där någon ger pengar till någon annan . Vi använder ersättningsmönstret`$2 takes money from $1` att utföra substitutionen genom att byta om rollerna. Användningen av`$1` och`$2` hänvisar till grupperna som fångas av det reguljära uttrycket:

```csharp
Regex regex = new Regex(@"([A-z]+) gives money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

doc.Range.Replace(regex, @"$2 takes money from $1", options);
```

### Exempel på källkod för Recognize And Substitutions Within Replacement Patterns med Aspose.Words for .NET

Här är det fullständiga exemplet på källkoden för att illustrera användningen av matchningar och ersättningar i ersättningsmönster med Aspose.Words för .NET:

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Jason give money to Paul.");

	Regex regex = new Regex(@"([A-z]+) give money to ([A-z]+)");

	FindReplaceOptions options = new FindReplaceOptions { UseSubstitutions = true };

	doc.Range.Replace(regex, @"$2 take money from $1", options);

```

## Slutsats

den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Recognize And Substitutions Within Replacement Patterns i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att skapa ett dokument, infoga text, utföra sökning och ersätta med reguljära uttryck och ersättningsmönster baserat på fångade grupper, och manipulera dokumentet.
