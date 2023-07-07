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

den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

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

I det här exemplet skapade vi ett nytt dokument, konstruerade ett IF-fält med kapslade MERGEFIELD-fält och infogade sedan det fältet i dokumentet på en angiven plats. Dokumentet sparas sedan med ett specifikt filnamn.

### FAQ's

#### F: Vad är en fältkonstruktör i Aspose.Words?

S: En Field Builder i Aspose.Words är ett kraftfullt verktyg för att skapa och manipulera fält i ett Word-dokument. Den erbjuder avancerade funktioner för att bygga och anpassa fält, inklusive att infoga fältkoder och hantera formateringsalternativ.

#### F: Vilka typer av fält kan infogas med hjälp av fältbyggaren?

S: Fältbyggaren i Aspose.Words låter dig infoga olika typer av fält i ett Word-dokument. Här är några exempel på vanliga fälttyper:

- MERGEFIELD: används för att slå samman data från externa källor.
- DATUM: visar aktuellt datum.
- PAGE: visar aktuellt sidnummer.
- IF: tillåter att villkora visningen av ett innehåll enligt ett villkor.
- TOC: genererar automatiskt en innehållsförteckning baserat på dokumentrubrikstilarna.

#### F: Hur anpassar man fälten som infogas med fältbyggaren?

S: Fältbyggaren erbjuder anpassningsalternativ för infogade fält. Du kan använda fältkonstruktormetoder och egenskaper för att ställa in alternativ som fältformatering, argument, växlar och standardvärden. Du kan till exempel ställa in datumformat, talformat, tusentalsavgränsare, etc.
  