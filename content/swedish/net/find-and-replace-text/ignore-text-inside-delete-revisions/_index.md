---
title: Ignorera text inuti Ta bort ändringar
linktitle: Ignorera text inuti Ta bort ändringar
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder funktionen "Ignorera text i radera ändringar" i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen "Ignorera text i radera ändringar" i Aspose.Words för .NET-biblioteket. Den här funktionen är användbar när vi vill ignorera text i raderingsversioner vid ordbehandling med dokument.

## Översikt över Aspose.Words för .NET-biblioteket

Innan jag dyker in i koddetaljerna, låt mig kort presentera Aspose.Words för .NET-biblioteket. Det är ett kraftfullt bibliotek som gör det möjligt att skapa, ändra och konvertera Word-dokument i .NET-applikationer. Den erbjuder många avancerade funktioner för ordbehandling med dokument, inklusive revisionshantering.

## Förstå funktionen "Ignorera text i radera versioner".

Funktionen "Ignorera text i raderingsversioner" i Aspose.Words för .NET låter dig ange om text i raderingsversioner ska ignoreras under vissa operationer, som att hitta och ersätta text. När den här funktionen är aktiverad, beaktas inte raderad text i revisioner under drift.

## Steg 1: Skapa ett nytt dokument med Aspose.Words för .NET

 Innan vi börjar manipulera text i ett dokument måste vi skapa ett nytt dokument med Aspose.Words för .NET. Det kan göras genom att instansiera en`Document` objekt:

```csharp
Document doc = new Document();
```

## Steg 2: Infoga icke-reviderad text i dokumentet

 När vi väl har ett dokument kan vi infoga ogranskad text med hjälp av en`DocumentBuilder` objekt. Till exempel, för att infoga texten "Raderad text", kan vi använda`Writeln` och`Write` metoder:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## Steg 3: Ta bort ett stycke med spårningsrevisioner

För att illustrera användningen av funktionen "Ignorera text i radera ändringar" kommer vi att ta bort ett stycke från dokumentet med hjälp av revisionsspårning. Detta gör att vi kan se hur den här funktionen påverkar efterföljande operationer.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## Steg 4: Använd funktionen "Ignorera text i radera ändringar".

 Nu när vi har förberett vårt dokument genom att ta bort ett stycke kan vi aktivera funktionen "Ignorera text inuti radera ändringar" med en`FindReplaceOptions` objekt. Vi kommer att ställa in`IgnoreDeleted`egendom till`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## Steg 5: Använd reguljära uttryck för att hitta och ersätta

För att utföra sök- och ersättningsoperationer på texten i dokumentet kommer vi att använda reguljära uttryck. I vårt exempel kommer vi att söka efter alla förekomster av bokstaven "e" och ersätta dem med en asterisk "* ". .NET`Regex` klass används för detta:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Steg 6: Visar den modifierade dokumentutmatningen

 Efter att ha tillämpat sökningen och ersätt, kan vi visa det ändrade innehållet i dokumentet med hjälp av`GetText` metod:

```csharp
Console.WriteLine(doc.GetText());
```

## Steg 7: Ändra alternativen för att inkludera raderad text

 Om vi vill inkludera raderad text i utdataresultatet kan vi ändra alternativen för att inte ignorera raderad text. För detta kommer vi att ställa in`IgnoreDeleted`egendom till`false`:

```csharp
options. IgnoreDeleted = false;
```

## Steg 8: Mata ut det ändrade dokumentet med raderad text

Efter att ha ändrat alternativen kan vi utföra sökningen och ersätta igen för att få resultatet med den raderade texten inkluderad:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Exempel på källkod för Ignorera text inuti Ta bort revisioner med Aspose.Words för .NET

Här är det fullständiga källkodsexemplet för att demonstrera användningen av funktionen "Ignorera text i radera ändringar" med Aspose.Words för .NET:

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Infoga icke-reviderad text.
	builder.Writeln("Deleted");
	builder.Write("Text");

	// Ta bort första stycket med spårningsrevisioner.
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## Slutsats

den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen "Ignorera text i radera ändringar" i Aspose.Words för .NET. Den här funktionen är användbar för att ignorera text i raderingsversioner när du manipulerar dokument. Vi följde en steg-för-steg-guide för att skapa ett dokument, infoga text, ta bort ett stycke med revisionsspårning, tillämpa funktionen "Ignorera text inuti radera revisioner" och utföra sök- och ersättningsoperationer.

### FAQ's

#### F: Vad är funktionen "Ignorera text inuti radera ändringar" i Aspose.Words för .NET?

S: Funktionen "Ignorera text i raderingsversioner" i Aspose.Words för .NET låter dig ange om text i raderingsversioner ska ignoreras under vissa operationer, som att hitta och ersätta text. När den här funktionen är aktiverad, beaktas inte raderad text i revisioner under drift.

#### F: Vad är Aspose.Words för .NET?

S: Aspose.Words för .NET är ett kraftfullt bibliotek för att skapa, redigera och konvertera Word-dokument till .NET-applikationer. Den erbjuder många avancerade funktioner för ordbehandling med dokument, inklusive revisionshantering.

#### F: Hur skapar man ett nytt dokument i Aspose.Words för .NET?

 S: Innan du börjar manipulera text i ett dokument måste du skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt. Här är en exempelkod för att skapa ett nytt dokument:

```csharp
Document doc = new Document();
```

#### F: Hur infogar man oredigerad text i ett dokument med Aspose.Words för .NET?

 S: När du har ett dokument kan du infoga ogranskad text med hjälp av en`DocumentBuilder` objekt. Till exempel, för att infoga texten "Raderad text", kan du använda`Writeln` och`Write` metoder:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### F: Hur tar jag bort ett stycke med revisionsspårning i Aspose.Words för .NET?

S: För att illustrera användningen av funktionen "Ignorera text i radera ändringar" kommer vi att ta bort ett stycke från dokumentet med hjälp av revisionsspårning. Detta gör att vi kan se hur den här funktionen påverkar efterföljande operationer.

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### F: Hur aktiverar man funktionen "Ignorera text i radera ändringar" i Aspose.Words för .NET?

 S: Nu när vi har förberett vårt dokument genom att ta bort ett stycke kan vi aktivera funktionen "Ignorera text inuti radera ändringar" med en`FindReplaceOptions` objekt. Vi kommer att ställa in`IgnoreDeleted`egendom till`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### F: Hur söker och ersätter jag med reguljära uttryck i Aspose.Words för .NET?

S: För att utföra sök- och ersättningsoperationer på texten i dokumentet kommer vi att använda reguljära uttryck. I vårt exempel kommer vi att söka efter alla förekomster av bokstaven "e" och ersätta dem med en asterisk "* ". Vi kommer att använda .NET`Regex` klass för detta:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### F: Hur kan man se ändrat dokumentinnehåll i Aspose.Words för .NET?

S: Efter att ha tillämpat sök och ersätt kan vi visa det ändrade innehållet i dokumentet med hjälp av`GetText` metod:

```csharp
Console.WriteLine(doc.GetText());
```

#### F: Hur inkluderar man raderad text i utdataresultatet i Aspose.Words för .NET?

 S: Om vi vill inkludera raderad text i utdataresultatet kan vi ändra alternativen för att inte ignorera raderad text. För detta kommer vi att ställa in`IgnoreDeleted`egendom till`false`:

```csharp
options. IgnoreDeleted = false;
```

#### F: Hur visar man redigerat dokument med raderad text i Aspose.Words för .NET?

S: Efter att ha ändrat alternativen kan vi göra en ny sökning och ersätta för att få resultatet med den raderade texten inkluderad:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
