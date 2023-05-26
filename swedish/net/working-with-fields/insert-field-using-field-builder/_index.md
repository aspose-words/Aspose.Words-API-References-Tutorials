---
title: Infoga fält med Field Builder
linktitle: Infoga fält med Field Builder
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar anpassade fält i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-field-using-field-builder/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Infoga ett fält med FieldBuilder" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet

Vi börjar med att skapa ett nytt dokument.

```csharp
Document doc = new Document();
```

## Steg 3: Bygg IF-fältet med FieldBuilder

Vi använder klassen FieldBuilder för att konstruera ett IF-fält med två kapslade MERGEFIELD-fält. I det här exemplet visar IF-fältet för- och efternamn baserat på ett villkor.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Steg 4: Infoga IF-fältet i dokumentet

 Vi använder`BuildAndInsert()` metod för att bygga och infoga IF-fältet på en specifik plats i dokumentet.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Exempel på källkod för att infoga ett fält med FieldBuilder med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument.
Document doc = new Document();

// Konstruktion av IF-fältet med FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Infoga OM-fältet i dokumentet.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

det här exemplet skapade vi ett nytt dokument, konstruerade ett IF-fält med kapslade MERGEFIELD-fält och infogade sedan det fältet i dokumentet på en angiven plats. Dokumentet sparas sedan med ett specifikt filnamn.
