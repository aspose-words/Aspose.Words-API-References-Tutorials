---
title: Formulärfält får efter namn
linktitle: Formulärfält får efter namn
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du hämtar och ändrar formulärfält efter namn i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-formfields/form-fields-get-by-name/
---

I denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att hämta formulärfält efter namn från ett Word-dokument. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt genom att ange sökvägen till ditt källdokument som innehåller formulärfält:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");
```

## Steg 2: Hämta formulärfält

 Gå sedan till`FormFields` egendom av`Range` objekt i dokumentet för att hämta alla formulärfält:

```csharp
FormFieldCollection documentFormFields = doc.Range.FormFields;
```

Du kan hämta formulärfält antingen med index eller namn. I det här exemplet hämtar vi ett formulärfält med båda metoderna:

```csharp
FormField formField1 = documentFormFields[3]; // Hämtar efter index
FormField formField2 = documentFormFields["Text2"]; // Hämtar med namn
```

## Steg 3: Ändra formulärfältegenskaper

 När du har hämtat formulärfälten kan du ändra deras egenskaper efter behov. I det här exemplet ändrar vi teckensnittsstorleken på`formField1` till 20 och teckensnittsfärgen på`formField2` till rött:

```csharp
formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;
```

## Steg 4: Spara dokumentet

Spara slutligen det ändrade dokumentet:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Det är allt! Du har framgångsrikt hämtat formulärfält efter namn och ändrat deras egenskaper i ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för formulärfält Get By Name med Aspose.Words för .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection documentFormFields = doc.Range.FormFields;

FormField formField1 = documentFormFields[3];
FormField formField2 = documentFormFields["Text2"];

formField1.Font.Size = 20;
formField2.Font.Color = Color.Red;

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.
