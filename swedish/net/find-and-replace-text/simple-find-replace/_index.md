---
title: Enkelt hitta ersätt
linktitle: Enkelt hitta ersätt
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du utför en enkel sökersättning i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/find-and-replace-text/simple-find-replace/
---

den här artikeln kommer vi att utforska C#-källkoden ovan för att förstå hur man använder funktionen Simple Find Replace i Aspose.Words for .NET-biblioteket. Den här funktionen låter dig utföra enkel textersättning genom att söka efter en specifik teckensträng och ersätta den med en annan teckensträng i ett Word-dokument.

## Förutsättningar

- Grundläggande kunskaper i C#-språket.
- .NET-utvecklingsmiljö med Aspose.Words-biblioteket installerat.

## Steg 1: Skapa ett nytt dokument

 Innan vi börjar använda enkel sök och ersätt måste vi skapa ett nytt dokument med Aspose.Words för .NET. Detta kan göras genom att instansiera en`Document` objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## Steg 2: Infoga text i dokumentet

 När vi har ett dokument kan vi infoga text med hjälp av a`DocumentBuilder` objekt. I vårt exempel använder vi`Writeln` metod för att infoga frasen "Hej_CustomerName_,":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## Steg 3: Enkel textersättning

 Vi använder`Range.Replace` metod för att utföra enkel textersättning. I vårt exempel ersätter vi alla förekomster av strängen "_ClientName_ " med "James Bond" med hjälp av`FindReplaceOptions` alternativet med`FindReplaceDirection.Forward` sökriktning:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Steg 4: Spara det redigerade dokumentet

 Slutligen sparar vi det ändrade dokumentet i en specificerad katalog med hjälp av`Save` metod:

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Exempel på källkod för Simple Find Replace med Aspose.Words för .NET

Här är det fullständiga exemplet på källkoden för att demonstrera användningen av enkel sökning och ersätt med Aspose.Words för .NET:

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	// Spara det ändrade dokumentet
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## Slutsats

den här artikeln utforskade vi C#-källkoden för att förstå hur man använder funktionen Simple Find Replace i Aspose.Words för .NET. Vi följde en steg-för-steg-guide för att skapa ett dokument, infoga text, utföra enkel textersättning och spara det redigerade dokumentet.
