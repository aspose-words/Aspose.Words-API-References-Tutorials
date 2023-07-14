---
title: Ignorera text inuti Infoga ändringar
linktitle: Ignorera text inuti Infoga ändringar
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder funktionen "Ignorera text inuti infoga versioner" i Aspose.Words för .NET för att manipulera infogningsrevisioner i Word-dokument.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

I den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder Ignore Text Inside Insert Revisions-funktionen i Aspose.Words for .NET-biblioteket. Den här funktionen är användbar när vi vill ignorera text i infogningsrevisioner medan vi manipulerar dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skapa ett nytt dokument

 Innan vi börjar manipulera text i infogningsversioner måste vi skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt:

```csharp
Document doc = new Document();
```

## Steg 2: Infoga text med revisionsspårning

 När vi har ett dokument kan vi infoga text med revisionsspårning med hjälp av en`DocumentBuilder`objekt. Till exempel, för att infoga texten "Infogad" med revisionsspårning, kan vi använda`StartTrackRevisions`, `Writeln` och`StopTrackRevisions` metoder:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Steg 3: Infoga ogranskad text

 Förutom text med revisionsspårning kan vi även infoga oreviderad text med hjälp av`DocumentBuilder` objekt. Till exempel, för att infoga texten "Text" utan revision, kan vi använda`Write` metod:

```csharp
builder.Write("Text");
```

## Steg 4: Använd funktionen Ignorera text inuti Infoga ändringar

 För att ignorera text inuti infoga revisioner på efterföljande operationer kan vi använda a`FindReplaceOptions` objekt och ställ in`IgnoreInserted` egendom till`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Steg 5: Använda reguljära uttryck för att söka och ersätta

För att utföra sökoperationer och ersätta dokumenttexten kommer vi att använda reguljära uttryck. I vårt exempel kommer vi att söka efter alla förekomster av bokstaven "e" och ersätta dem med en asterisk "* ". Vi kommer att använda .NET`Regex` klass för detta:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Steg 6: Visa den modifierade dokumentutgången

Efter att ha tillämpat sökningen och ersätt, kan vi visa det ändrade innehållet i dokumentet med hjälp av`GetText` metod:

```csharp
Console.WriteLine(doc.GetText());
```

## Steg 7: Ändra alternativ för att inkludera infogningsrevisioner

Om vi vill inkludera texten inuti infogningsrevisionerna i utdataresultatet, kan vi ändra alternativen för att inte ignorera infogningsrevisionerna. För detta kommer vi att ställa in`IgnoreInserted` egendom till`false`:

```csharp
options.IgnoreInserted = false;
```

## Steg 8: Visa det ändrade dokumentet med infogningsrevisioner

Efter att ha ändrat alternativen kan vi utföra sökningen och ersätta igen för att få resultatet med texten inuti insättningsrevisionerna:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Exempel på källkod för Ignorera text inuti Infoga versioner med Aspose.Words för .NET

Här är den fullständiga källkoden för att demonstrera användningen av funktionen Ignorera text inuti infoga ändringar med Aspose.Words för .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Infoga text med spårningsrevisioner.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Infoga icke-reviderad text.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Slutsats

den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Ignorera text inuti infoga ändringar i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att skapa ett dokument, infoga text med spårningsrevisioner och oreviderad text, använda funktionen Ignorera text inuti Infoga revisioner, utföra sökning och ersätta operationer med reguljära uttryck och visa det ändrade dokumentet.

### FAQ's

#### F: Vad är funktionen "Ignorera text inuti infoga ändringar" i Aspose.Words för .NET?

S: Funktionen "Ignorera text inuti infogningsrevisioner" i Aspose.Words för .NET låter dig ange om texten inuti infogningsrevisioner ska ignoreras under vissa operationer, som att hitta och ersätta text. När den här funktionen är aktiverad, beaktas inte texten i bilagans versioner under drift.

#### F: Hur kan jag skapa ett nytt dokument med Aspose.Words för .NET?

 S: För att skapa ett nytt dokument med Aspose.Words för .NET kan du instansiera en`Document` objekt. Här är ett exempel på C#-kod för att skapa ett nytt dokument:

```csharp
Document doc = new Document();
```

#### F: Hur kan jag infoga text med revisionsspårning i Aspose.Words för .NET?

S: När du har ett dokument kan du infoga text med revisionsspårning med hjälp av en`DocumentBuilder` objekt. Till exempel, för att infoga texten "Infogad" med revisionsspårning, kan du använda`StartTrackRevisions`, `Writeln` , och`StopTrackRevisions` metoder:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### F: Hur kan jag infoga oreviderad text i Aspose.Words för .NET?

 S: Förutom text med revisionsspårning kan du också infoga oreviderad text med hjälp av`DocumentBuilder` objekt. Till exempel, för att infoga texten "Text" utan revidering, kan du använda`Write` metod:

```csharp
builder.Write("Text");
```

#### F: Hur kan jag ignorera text i infogningsversioner i Aspose.Words för .NET?

 S: För att ignorera text i infogningsrevisioner under efterföljande operationer, kan du använda a`FindReplaceOptions` objekt och ställ in`IgnoreInserted` egendom till`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### F: Hur kan jag söka och ersätta med reguljära uttryck i Aspose.Words för .NET?

 S: För att utföra sök- och ersättningsoperationer på texten i dokumentet med hjälp av reguljära uttryck, kan du använda .NET`Regex` klass. Till exempel, för att söka efter alla förekomster av bokstaven "e" och ersätta dem med en asterisk "* ", kan du skapa en`Regex` objekt och använd det med`Replace` metod:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### F: Hur kan jag se den modifierade utdata från dokumentet i Aspose.Words för .NET?

 S: Efter att ha tillämpat sök- och ersättningsoperationer kan du se det ändrade innehållet i dokumentet med hjälp av`GetText` metod:

```csharp
Console.WriteLine(doc.GetText());
```

#### F: Hur kan jag inkludera insättningsrevisionerna i utdataresultatet i Aspose.Words för .NET?

 S: För att inkludera texten i infogningsrevisionerna i utdataresultatet, kan du ändra alternativen för att inte ignorera infogningsrevisionerna. För detta kan du ställa in`IgnoreInserted`egendom av`FindReplaceOptions` invända mot`false`:

```csharp
options.IgnoreInserted = false;
```

#### F: Hur kan jag visa det modifierade dokumentet med insättningsversionerna i Aspose.Words för .NET?

S: Efter att ha ändrat alternativen för att inkludera infogningsrevisioner kan du utföra sökningen och ersätta igen för att få resultatet med texten inuti infogningsrevisionerna:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```