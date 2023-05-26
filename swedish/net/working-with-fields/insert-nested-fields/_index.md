---
title: Infoga kapslade fält
linktitle: Infoga kapslade fält
second_title: Aspose.Words för .NET API Referens
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

 Vi använder DocumentBuilder's`InsertField()` metod för att infoga ett kapslat fält i sidfoten.

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