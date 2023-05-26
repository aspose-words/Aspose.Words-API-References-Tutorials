---
title: Ersätt text som innehåller metatecken
linktitle: Ersätt text som innehåller metatecken
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ersätter text som innehåller metatecken i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/replace-text-containing-meta-characters/
---

I den här artikeln kommer vi att utforska ovanstående C#-källkod för att förstå hur man använder funktionen Ersätt text som innehåller metatecken i Aspose.Words för .NET-biblioteket. Den här funktionen låter dig ersätta delar av texten i ett dokument som innehåller specifika meta-tecken.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skapa ett nytt dokument

 Innan vi börjar använda textersättning för metatecken måste vi skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Steg 2: Infoga text i dokumentet

 När vi har ett dokument kan vi infoga text med hjälp av a`DocumentBuilder` objekt. I vårt exempel använder vi`Writeln`metod för att infoga flera stycken av text i olika avsnitt:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## Steg 3: Konfigurera Sök och ersätt alternativ

 Nu kommer vi att konfigurera hitta och ersätta alternativ med hjälp av en`FindReplaceOptions` objekt. I vårt exempel ställer vi in justeringen av de ersatta styckena till "Centrerad":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment

.Center;
```

## Steg 4: Ersätt text som innehåller metatecken

 Vi använder`Range.Replace` metod för att ersätta text som innehåller metatecken. I vårt exempel ersätter vi varje förekomst av ordet "avsnitt" följt av en styckebrytning med samma ord följt av flera bindestreck och en ny styckebrytning:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## Steg 5: Byt ut en anpassad texttagg

 Vi använder också`Range.Replace` metod för att ersätta en anpassad "{insert-section}" texttagg med avsnittsbrytning. I vårt exempel ersätter vi "{insert-section}" med "&b" för att infoga en avsnittsbrytning:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## Steg 6: Spara det redigerade dokumentet

 Slutligen sparar vi det ändrade dokumentet i en specificerad katalog med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Exempel på källkod för Ersätt text som innehåller metatecken med Aspose.Words för .NET

Här är det fullständiga exemplet på källkoden för att demonstrera användningen av textersättning som innehåller metatecken med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// Dubbla varje styckebrytning efter ordet "avsnitt", lägg till typ av understrykning och gör det centrerat.
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	// Infoga avsnittsbrytning istället för anpassad texttagg.
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Ersätt text som innehåller metatecken i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att skapa ett dokument, infoga text, ersätta text som innehåller metatecken och spara det ändrade dokumentet.

