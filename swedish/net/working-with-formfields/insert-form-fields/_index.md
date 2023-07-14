---
title: Infoga formulärfält
linktitle: Infoga formulärfält
second_title: Aspose.Words Document Processing API
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

 Ange sedan alternativen för rullgardinsmenyn och infoga det i dokumentet med hjälp av`InsertComboBox` metod för`DocumentBuilder` objekt. I det här exemplet infogar vi ett rullgardinsfält med namnet "DropDown" med tre alternativ: "En", "Två" och "Tre":

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

### FAQ's

#### F: Hur kan jag infoga ett formulärfält för texttyp i Aspose.Words?

 S: För att infoga ett formulärfält för texttyp i Aspose.Words kan du använda`FormField` klass och ställ in dess`Type` egendom till`FormFieldType.Text`. Du kan också anpassa andra egenskaper som namn, etikett och alternativ.

#### F: Är det möjligt att skapa ett formulärfält för kryssruta i ett dokument?

 S: Ja, det är möjligt att skapa ett formulärfält för kryssruta i ett Aspose.Words-dokument. Du kan använda`FormField` klass och ställ in dess`Type` egendom till`FormFieldType.CheckBox` för att skapa en kryssruta. Du kan sedan anpassa egenskaperna för kryssrutan efter behov.

#### F: Hur kan jag lägga till ett formulärfält i rullgardinsmenyn i ett dokument?

 S: För att lägga till ett formulärfält i rullgardinsmenyn i ett Aspose.Words-dokument, använd`FormField` klass och ställ in dess`Type` egendom till`FormFieldType.DropDown` . Du kan sedan ställa in rullgardinsmenyn med hjälp av`DropDownItems` fast egendom.

#### F: Kan jag ange ett standardvärde för ett formulärfält i Aspose.Words?

S: Ja, du kan ställa in ett standardvärde för ett formulärfält i Aspose.Words. Använd`FormField.Result` egenskap för att ange startvärdet för formulärfältet.

#### F: Hur kan jag hämta data som skrivits in i formulärfält i Aspose.Words?

 S: För att hämta data som skrivits in i formulärfält i Aspose.Words kan du använda`FormField.Result` egenskap som innehåller värdet som angetts av användaren. Du kan komma åt den här egenskapen för varje formulärfält i ditt dokument.