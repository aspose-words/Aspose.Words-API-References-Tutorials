---
title: Jämförelse Granularitet
linktitle: Jämförelse Granularitet
second_title: Aspose.Words Document Processing API
description: Lär dig Jämför granularitetsfunktionen i Aspose.Words för .NET som gör att dokument kan jämföras tecken för tecken, och rapporterar gjorda ändringar.
type: docs
weight: 10
url: /sv/net/compare-documents/comparison-granularity/
---
Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen Compare Granularity i Aspose.Words för .NET.

## Steg 1: Introduktion

Funktionen Compare Granularity i Aspose.Words för .NET låter dig jämföra dokument på teckennivå. Detta innebär att varje karaktär kommer att jämföras och ändringar kommer att rapporteras därefter.

## Steg 2: Sätta upp miljön

Innan du börjar måste du ställa in din utvecklingsmiljö för att fungera med Aspose.Words för .NET. Se till att du har Aspose.Words-biblioteket installerat och har ett lämpligt C#-projekt att bädda in koden i.

## Steg 3: Lägg till nödvändiga sammansättningar

För att använda funktionen Compare Granularity i Aspose.Words för .NET måste du lägga till de nödvändiga sammansättningarna till ditt projekt. Se till att du har rätt referenser till Aspose.Words i ditt projekt.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Steg 4: Skapa dokument

I det här steget kommer vi att skapa två dokument med klassen DocumentBuilder. Dessa dokument kommer att användas för jämförelsen.

```csharp
// Skapa dokument A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Skapa dokument B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Steg 5: Konfigurera jämförelsealternativ

I det här steget kommer vi att konfigurera jämförelsealternativen för att specificera jämförelsegranulariteten. Här kommer vi att använda granularitet på teckennivå.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Steg 6: Dokumentjämförelse

Låt oss nu jämföra dokumenten med hjälp av metoden Compare för klassen Document. Ändringar sparas i dokument A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 De`Compare`metoden jämför dokument A med dokument B och sparar ändringarna i dokument A. Du kan ange författarens namn och datum för jämförelsen som referens.

## Slutsats

I den här artikeln utforskade vi funktionen Compare Granularity i Aspose.Words för .NET. Den här funktionen låter dig jämföra dokument på teckennivå och rapportera ändringar. Du kan använda denna kunskap för att utföra detaljerade dokumentjämförelser i dina projekt.

### Exempel på källkod för Comparison Granularity med Aspose.Words för .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```
