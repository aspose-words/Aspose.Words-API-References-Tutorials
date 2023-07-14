---
title: Infoga kapslade fält
linktitle: Infoga kapslade fält
second_title: Aspose.Words Document Processing API
description: Lär dig hur du enkelt infogar kapslade fält i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-nested-fields/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Infoga kapslade fält" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa Document and DocumentBuilder

Vi börjar med att skapa ett nytt dokument och initiera en DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga sidbrytningar

Vi använder en loop för att infoga flera sidbrytningar i dokumentet.

```csharp
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);
```

## Steg 4: Flytta till sidfot

 Vi använder`MoveToHeaderFooter()` metoden i DocumentBuilder för att flytta markören till huvudsidfoten.

```csharp
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

## Steg 5: Infoga det kapslade fältet

 Vi använder DocumentBuilder's`InsertField()`metod för att infoga ett kapslat fält i sidfoten.

```csharp
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");
```

 Slutligen kallar vi`Update()` metod för att uppdatera fältet.

```csharp
field. Update();
```

### Exempel på källkod för att infoga kapslade fält med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga sidbrytningar.
for (int i = 0; i < 5; i++)
     builder. InsertBreak(BreakType.PageBreak);

// Flytta till sidfoten.
builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// Infoga kapslat fält.
Field field = builder. InsertField(@"IF ");
builder.MoveTo(field.Separator);
builder. InsertField("PAGE");
builder. Write(" <> ");
builder.InsertField("NUMPAGES");
builder.Write(" \"See next page\" \"Last page\" ");

// Uppdatera fältet.
field. Update();

doc.Save(dataDir + "InsertNestedFields.docx");
```

I det här exemplet skapade vi ett nytt dokument, infogade sidbrytningar, flyttade markören till sidfoten och infogade sedan ett kapslat fält i sidfoten.

### FAQ's

#### F: Hur kan jag infoga kapslade fält i ett Word-dokument med Aspose.Words för .NET?

S: För att infoga kapslade fält i ett Word-dokument med Aspose.Words för .NET, kan du följa dessa steg:

1. Hämta stycket där du vill infoga de kapslade fälten.
2.  Skapa en`FieldStart` objekt för det överordnade fältet.
3.  Lägg till underordnade fält med hjälp av`FieldStart.NextSibling` metod som passerar motsvarande`FieldStart` objekt som parametrar.

#### F: Vilka är fördelarna med att använda kapslade fält i ett Word-dokument med Aspose.Words för .NET?

S: Att använda kapslade fält ger flera fördelar i ett Word-dokument med Aspose.Words för .NET. Detta ger större flexibilitet när det gäller att skapa dynamiska dokumentmallar genom att tillåta infogning av variabelvärden och beräkningar i kapslade fält. Kapslade fält kan också underlätta automatisk generering av innehåll, som att generera innehållsförteckningar, sidnummer, etc.

#### F: Kan jag ha kapslade fält på flera nivåer i ett Word-dokument med Aspose.Words för .NET?

 S: Ja, det är möjligt att ha kapslade fält på flera nivåer i ett Word-dokument med Aspose.Words för .NET. Du kan skapa komplexa hierarkier av kapslade fält genom att använda`FieldStart.NextSibling` metod för att lägga till underordnade fält till befintliga överordnade fält.

#### F: Hur kan jag anpassa egenskaperna för kapslade fält i ett Word-dokument med Aspose.Words för .NET?

 S: För att anpassa egenskaperna för kapslade fält i ett Word-dokument med Aspose.Words för .NET kan du komma åt motsvarande`FieldStart`objekt och ändra deras egenskaper efter behov. Du kan ställa in formateringsalternativ, värden, beräkningar etc. för kapslade fält för att uppnå önskat resultat.

#### F: Påverkar det att infoga kapslade fält Word-dokumentets prestanda med Aspose.Words för .NET?

S: Att infoga kapslade fält kan påverka Word-dokumentets prestanda med Aspose.Words för .NET, särskilt om dokumentet innehåller ett stort antal kapslade fält eller komplexa hierarkier. Det rekommenderas att optimera koden för att undvika onödiga eller upprepade operationer på kapslade fält för att förbättra prestandan.