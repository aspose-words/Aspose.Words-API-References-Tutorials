---
title: Ersätt med Regex
linktitle: Ersätt med Regex
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du utför reguljära uttrycksbaserad textersättning i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/replace-with-regex/
---

I den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen Ersätt med Regex i Aspose.Words för .NET-biblioteket. Den här funktionen låter dig utföra textersättning baserat på specifika mönster som definieras av ett reguljärt uttryck.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skapa ett nytt dokument

 Innan vi börjar använda ersättning för reguljära uttryck måste vi skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt:

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

## Steg 3: Konfigurera Sök och ersätt alternativ

 Nu kommer vi att konfigurera hitta och ersätta alternativ med hjälp av en`FindReplaceOptions` objekt. I vårt exempel använder vi standardalternativen:

```csharp
FindReplaceOptions options = new FindReplaceOptions();
```

## Steg 4: Ersätt med reguljärt uttryck

 Vi använder`Range.Replace` metod för att utföra textersättning med ett reguljärt uttryck. I vårt exempel använder vi det reguljära uttrycket "[s|m]ad" to find the words "sad" and "mad" and replace them with the word "bad":

```csharp
doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);
```

## Steg 5: Spara det ändrade dokumentet

 Slutligen sparar vi det ändrade dokumentet i en specificerad katalog med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
```

### Exempel på källkod för Ersätt med Regex med Aspose.Words för .NET

Här är den fullständiga källkoden för att demonstrera användningen av reguljära uttrycksersättning med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	FindReplaceOptions options = new FindReplaceOptions();

	doc.Range.Replace(new Regex("[s|m]ad"), "bad", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceWithRegex.docx");
  
```

## Slutsats

I den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Ersätt med Regex i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att skapa ett dokument, infoga text, utföra ersättningen med ett reguljärt uttryck och spara det ändrade dokumentet.
