---
title: Infoga formulärfält
linktitle: Infoga formulärfält
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar dropdown-formulärfält i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-formfields/insert-form-fields/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du infogar formulärfält, särskilt ett rullgardinsfält, i ett Word-dokument med Aspose.Words för .NET. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera Document- och DocumentBuilder-objekten

 Initiera först`Document` och`DocumentBuilder` föremål:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga ett rullgardinsformulärfält

 Ange sedan alternativen för rullgardinsmenyn och infoga det i dokumentet med hjälp av`InsertComboBox` metod för`DocumentBuilder`objekt. I det här exemplet infogar vi ett rullgardinsfält med namnet "DropDown" med tre alternativ: "En", "Två" och "Tre":

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## Steg 3: Spara dokumentet

Spara slutligen dokumentet:

```csharp
doc.Save("OutputDocument.docx");
```

Det är allt! Du har framgångsrikt infogat ett rullgardinsfält i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för Infoga formulärfält med Aspose.Words för .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.