---
title: Ersätt med sträng
linktitle: Ersätt med sträng
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ersätter text med en sträng i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/replace-with-string/
---

I den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen Ersätt med sträng i Aspose.Words för .NET-biblioteket. Den här funktionen låter dig utföra textersättning baserat på en specifik teckensträng i ett Word-dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skapa ett nytt dokument

Innan vi börjar använda strängersättning måste vi skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Steg 2: Infoga text i dokumentet

 När vi har ett dokument kan vi infoga text med hjälp av a`DocumentBuilder` objekt. I vårt exempel använder vi`Writeln` metod för att infoga frasen "sad crazy bad":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## Steg 3: Ersätt med en sträng

 Vi använder`Range.Replace` metod för att ersätta text med en sträng. I vårt exempel ersätter vi alla förekomster av ordet "tråkigt" med "dåligt" med hjälp av`FindReplaceOptions` alternativet med`FindReplaceDirection.Forward` sökriktning:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Steg 4: Spara det redigerade dokumentet

 Slutligen sparar vi det ändrade dokumentet i en specificerad katalog med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Exempel på källkod för Ersätt med sträng med Aspose.Words för .NET

Här är den fullständiga källkoden för att illustrera användningen av att ersätta med en teckensträng med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Ersätt med sträng i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att skapa ett dokument, infoga text, ersätta med en sträng och spara det ändrade dokumentet.
