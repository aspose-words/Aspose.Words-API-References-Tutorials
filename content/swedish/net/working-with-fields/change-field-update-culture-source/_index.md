---
title: Ändra fältuppdateringskulturkälla
linktitle: Ändra fältuppdateringskulturkälla
second_title: Aspose.Words Document Processing API
description: Ändra fältuppdatering kulturkälla, steg-för-steg-guide för att ändra kulturkälla i Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/change-field-update-culture-source/
---

den här handledningen kommer vi att guida dig genom processen att ändra fältuppdateringskulturkällan i Word-dokument med Aspose.Words för .NET. Genom att ändra kulturkällan kan du styra datumformateringen under fältuppdateringar och kopplingsoperationer. Vi kommer att förse dig med den nödvändiga C#-källkoden och steg-för-steg-instruktioner för att uppnå detta.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa en Document and DocumentBuilder
För att börja skapa en instans av klassen Document och ett DocumentBuilder-objekt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 2: Infoga innehåll med specifik plats
Ställ sedan in språket till tyska och infoga fält med datumformatering:

```csharp
builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");
```

I ovanstående kod ställer vi in teckensnittslokalen till tyska (locale ID 1031) och infogar två fält med specifik datumformatering.

## Steg 3: Ändra fältuppdateringskulturkälla
För att ändra källan för fältuppdateringskultur, använd klassen FieldOptions:

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
```

I det här exemplet ställer vi in kulturen som används under fältuppdateringen att väljas från den kultur som används av fältet.

## Steg 4: Utför Mail Merge
Utför en kopplingsoperation och ange datumvärdet för fältet "Date2":

```csharp
doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });
```

I det här kodavsnittet kör vi sammankopplingsoperationen och tillhandahåller ett DateTime-värde för fältet "Date2".

## Steg 5: Spara dokumentet
Spara det ändrade dokumentet till en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

### Exempel på källkod för att ändra fältuppdateringskulturkälla med Aspose.Words för .NET
Här är den fullständiga källkoden för att ändra fältuppdateringskulturkällan i Word-dokument med Aspose.Words för .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.LocaleId = 1031;
builder.InsertField("MERGEFIELD Date1 \\@ \"dddd, d MMMM yyyy\"");
builder.Write(" - ");
builder.InsertField("MERGEFIELD Date2 \\@ \"dddd, d MMMM yyyy\"");

doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;

doc.MailMerge.Execute(new string[] { "Date2" }, new object[] { new DateTime(2011, 1, 1) });

doc.Save(dataDir + "WorkingWithFields.ChangeFieldUpdateCultureSource.docx");
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du ändrar fältuppdateringskulturkällan i Word-dokument med Aspose.Words för .NET. Genom att följa den steg-för-steg-guiden och använda den medföljande källkoden kan du nu styra kulturen som används för datumformatering under fältuppdatering och kopplingsoperationer. Anpassa kulturkällan enligt dina krav för att säkerställa korrekt och konsekvent datum.

### FAQ's

#### F: Hur kan jag ändra fältuppdateringskulturkällan i Aspose.Words för .NET?

 S: För att ändra fältuppdateringskulturkällan i Aspose.Words för .NET kan du använda`Document.FieldOptions.CultureSource` egendom och sätt dess värde till`FieldCultureSource.FieldCode` eller`FieldCultureSource.CurrentThread` . Du kan till exempel använda`document.FieldOptions.CultureSource = FieldCultureSource.FieldCode` för att använda den kultur som definieras i fältkoden.

#### F: Hur kan jag specificera en specifik kultur för uppdatering av fält i Aspose.Words för .NET?

 S: För att ange en specifik kultur för uppdatering av fält i Aspose.Words för .NET, kan du använda`Document.FieldOptions.FieldUpdateCultureInfo` egendom och ställ in`CultureInfo` objekt som motsvarar den önskade kulturen. Du kan till exempel använda`document.FieldOptions.FieldUpdateCultureInfo = new CultureInfo("fr-FR")` för att specificera den franska (Frankrike) kulturen.

#### F: Är det möjligt att inaktivera automatisk fältuppdatering i Aspose.Words för .NET?

 S: Ja, det är möjligt att inaktivera automatisk fältuppdatering i Aspose.Words för .NET. Du kan använda`Document.FieldOptions.UpdateFields` egendom och ställ in den på`false` för att förhindra att fält uppdateras automatiskt. Detta låter dig manuellt styra uppdateringen av fält efter behov.

#### F: Hur kan jag manuellt uppdatera dokumentfält i Aspose.Words för .NET?

 S: För att manuellt uppdatera fält i ett dokument i Aspose.Words för .NET kan du använda`Field.Update` metod för varje område individuellt. Du kan till exempel använda`field.Update()` för att uppdatera det specifika fältet.