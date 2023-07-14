---
title: Ordbyt ut text som innehåller metatecken
linktitle: Ordbyt ut text som innehåller metatecken
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ord ersätter text som innehåller metatecken i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/replace-text-containing-meta-characters/
---
I den här artikeln kommer vi att utforska ovanstående C#-källkod för att förstå hur man använder funktionen Word Replace Text Containing Meta Characters i Aspose.Words for .NET-biblioteket. Den här funktionen låter dig ersätta delar av texten i ett dokument som innehåller specifika meta-tecken.

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

 När vi har ett dokument kan vi infoga text med hjälp av a`DocumentBuilder` objekt. I vårt exempel använder vi`Writeln` metod för att infoga flera stycken av text i olika avsnitt:

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
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## Steg 4: Ersätt text som innehåller metatecken

 Vi använder`Range.Replace`metod för att ersätta text som innehåller metatecken. I vårt exempel ersätter vi varje förekomst av ordet "avsnitt" följt av en styckebrytning med samma ord följt av flera bindestreck och en ny styckebrytning:

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

den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Ersätt text som innehåller metatecken i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att skapa ett dokument, infoga text, ersätta text som innehåller metatecken och spara det ändrade dokumentet.

### FAQ's

#### F: Vad är funktionen Ersätt text som innehåller metatecken i Aspose.Words för .NET?

S: Funktionen Ersätt text som innehåller metatecken i Aspose.Words för .NET låter dig ersätta delar av text i ett dokument som innehåller specifika metatecken. Du kan använda den här funktionen för att utföra avancerade ersättningar i ditt dokument med hänsyn till metatecken.

#### F: Hur skapar man ett nytt dokument i Aspose.Words för .NET?

 S: Innan du använder funktionen Ersätt text som innehåller metatecken måste du skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt. Här är en exempelkod för att skapa ett nytt dokument:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### F: Hur infogar man text i ett dokument med Aspose.Words för .NET?

 S: När du har ett dokument kan du infoga text med hjälp av en`DocumentBuilder` objekt. I vårt exempel använder vi`Writeln` metod för att infoga flera stycken av text i olika avsnitt:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### F: Hur konfigurerar man sök- och ersättningsalternativ i Aspose.Words för .NET?

 S: Nu kommer vi att konfigurera hitta och ersätta alternativ med hjälp av a`FindReplaceOptions` objekt. I vårt exempel ställer vi in justeringen av de ersatta styckena till "Centrerad":

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### F: Hur ersätter man text som innehåller metatecken i ett dokument med Aspose.Words för .NET?

 A: Vi använder`Range.Replace` metod för att utföra ersättning av text som innehåller meta-tecken. I vårt exempel ersätter vi varje förekomst av ordet "avsnitt" följt av en styckebrytning med samma ord följt av flera bindestreck och en ny styckebrytning:

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### F: Hur ersätter man en anpassad texttagg som innehåller meta-tecken i ett dokument med Aspose.Words för .NET?

 S: Vi använder också`Range.Replace` metod för att ersätta en anpassad "{insert-section}" texttagg med avsnittsbrytning. I vårt exempel ersätter vi "{insert-section}" med "&b" för att infoga en avsnittsbrytning:

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### F: Hur sparar jag ett redigerat dokument i Aspose.Words för .NET?

 S: När du har gjort ändringar i dokumentet kan du spara det i en angiven katalog med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```