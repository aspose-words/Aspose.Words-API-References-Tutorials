---
title: Meta-tecken i sökmönster
linktitle: Meta-tecken i sökmönster
second_title: Aspose.Words Document Processing API
description: Lär dig hur du använder metatecken i sökmönstret med Aspose.Words för .NET för att manipulera Word-dokument.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/meta-characters-in-search-pattern/
---
I den här artikeln kommer vi att utforska ovanstående C#-källkod för att förstå hur man använder Meta Characters In Search Pattern-funktionen i Aspose.Words för .NET-biblioteket. Den här funktionen låter dig använda speciella metatecken för att utföra avancerade sökningar och ersättningar i Word-dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skapa ett nytt dokument

 Innan vi börjar använda metatecken i sökmönstret måste vi skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## Steg 2: Infoga text i dokumentet

 När vi har ett dokument kan vi infoga text med hjälp av a`DocumentBuilder` objekt. I vårt exempel använder vi`Writeln` och`Write` metoder för att infoga två rader text:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## Steg 3: Hitta och ersätt text med metatecken

 Nu kommer vi att använda`Range.Replace` funktion för att söka och ersätta text med hjälp av ett sökmönster som innehåller speciella metatecken. I vårt exempel ersätter vi frasen "Detta är rad 1&pDetta är rad 2" med "Denna rad är ersatt" med hjälp av`&p` metatecken för att representera en styckebrytning:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## Steg 4: Infoga en sidbrytning i dokumentet

 För att illustrera användningen av en annan metatecken kommer vi att infoga en sidbrytning i dokumentet med hjälp av`InsertBreak` metod med`BreakType.PageBreak` parametrar. Vi flyttar först markören från`DocumentBuilder` till slutet av dokumentet infogar vi sidbrytningen och en ny textrad:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## Steg 5: Hitta och ersätt med en annan metatecken

 Nu gör vi en ny sökning och ersätter med hjälp av`&m` metatecken för att representera en sidbrytning. Vi ersätter frasen "Detta är rad 1&mDetta är rad 2" med "Sidbrytningen är ersatt med ny text." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## Steg 6: Spara det redigerade dokumentet

Slutligen sparar vi det ändrade dokumentet i en specificerad katalog med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Exempel på källkod för Meta Characters In Search Pattern med Aspose.Words för .NET

Här är den fullständiga källkoden för att demonstrera användningen av metatecken i sökmönstret med Aspose.Words för .NET:

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder metatecken i sökmönstret för Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att skapa ett dokument, infoga text, utföra sökning och ersätta med speciella metatecken, infoga sidbrytningar och spara det redigerade dokumentet.

### FAQ's

#### F: Vad är funktionen Meta Characters In Search Pattern i Aspose.Words för .NET?

S: Funktionen Meta Characters In Search Pattern i Aspose.Words för .NET låter dig använda speciella meta-tecken för att utföra avancerade sökningar och ersättningar i Word-dokument. Dessa metatecken låter dig representera styckebrytningar, avsnittsbrytningar, sidbrytningar och andra specialelement i ditt sökmönster.

#### F: Hur skapar man ett nytt dokument i Aspose.Words för .NET?

 S: Innan du använder metatecken i sökmallen måste du skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt. Här är en exempelkod för att skapa ett nytt dokument:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### F: Hur infogar man text i ett dokument med Aspose.Words för .NET?

 S: När du har ett dokument kan du infoga text med hjälp av en`DocumentBuilder` objekt. I vårt exempel använder vi`Writeln` och`Write` metoder för att infoga två rader text:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### F: Hur söker och ersätter man text med metatecken i ett dokument med Aspose.Words för .NET?

 S: För att söka och ersätta text med metatecken kan du använda`Range.Replace` metod. I vårt exempel ersätter vi frasen "Detta är rad 1&pDetta är rad 2" med "Denna rad är ersatt" med hjälp av`&p` metatecken för att representera en styckebrytning:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### F: Hur infogar man en sidbrytning i ett dokument med Aspose.Words för .NET?

S: För att illustrera användningen av en annan metatecken kommer vi att infoga en sidbrytning i dokumentet med hjälp av`InsertBreak` metod med`BreakType.PageBreak` parametrar. Vi flyttar först markören från`DocumentBuilder` till slutet av dokumentet infogar vi sidbrytningen och en ny textrad:

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### F: Hur söker och ersätter man med en annan metatecken i ett dokument med Aspose.Words för .NET?

 S: Vi kommer nu att utföra en ny sökning och ersätta med hjälp av`&m` metatecken för att representera en sidbrytning. Vi ersätter frasen "Detta är rad 1&mDetta är rad 2" med "Sidbrytningen är ersatt med ny text." :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### F: Hur sparar jag ett redigerat dokument i Aspose.Words för .NET?

 S: När du har gjort ändringar i dokumentet kan du spara det i en angiven katalog med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```