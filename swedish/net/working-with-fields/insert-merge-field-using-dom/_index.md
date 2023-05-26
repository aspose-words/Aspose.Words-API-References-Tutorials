---
title: Infoga sammanslagningsfält med DOM
linktitle: Infoga sammanslagningsfält med DOM
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar anpassade sammanslagningsfält i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-merge-field-using-dom/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan som använder funktionen "Insert Field Merge Field" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

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

## Steg 3: Flytta markören till stycket

 Vi använder`MoveTo()` metoden i DocumentBuilder för att flytta markören till stycket där vi vill infoga fältsammanfogningsfältet.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Steg 4: Infoga fältsammanfogningsfältet

 Vi använder DocumentBuilder's`InsertField()` metod för att infoga ett sammanslagningsfält för fält i stycket.

```csharp
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);
```

Vi konfigurerar sedan egenskaperna för fältsammanslagning genom att ange lämpliga alternativ, såsom fältnamn, text före och efter fältet och vertikala formateringsalternativ.

```csharp
field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;
```

 Slutligen kallar vi`Update()` metod för att uppdatera fältet.

```csharp
field. Update();
```

### Exempel på källkod för att infoga ett sammanslagningsfält för fält med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Flytta markören till stycket.
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);

// Infoga sammanslagningsfält för fält.
FieldMergeField field = (FieldMergeField)builder.InsertField(FieldType.FieldMergeField, false);

field.FieldName = "Test1";
field.TextBefore = "Test2";
field. TextAfter = "Test3";
field. IsMapped = true;
field. IsVerticalFormatting = true;

// Uppdatera fältet.
field. Update();

doc.Save(dataDir + "InsertionChampMergeChamp.docx");
```

I det här exemplet skapade vi ett nytt dokument, flyttade markören till önskat stycke och infogade sedan ett sammanslagningsfält för fält i dokumentet.