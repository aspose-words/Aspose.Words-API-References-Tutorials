---
title: Formulärfält Hämta formulärfältsamling
linktitle: Formulärfält Hämta formulärfältsamling
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du hämtar och manipulerar insamling av formulärfält i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-formfields/form-fields-get-form-fields-collection/
---

denna steg-för-steg handledning kommer vi att guida dig om hur du använder Aspose.Words för .NET för att hämta samlingen av formulärfält från ett Word-dokument. Vi kommer att förklara den medföljande C#-källkoden och visa dig hur du implementerar den i dina egna projekt.

För att komma igång, se till att du har Aspose.Words för .NET installerat och konfigurerat i din utvecklingsmiljö. Om du inte har gjort det, ladda ner och installera biblioteket från den officiella webbplatsen.

## Steg 1: Initiera dokumentobjektet

 Initiera först`Document` objekt genom att ange sökvägen till ditt källdokument som innehåller formulärfält:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");
```

## Steg 2: Hämta formulärfältsamlingen

 Gå sedan till`FormFields` egendom av`Range` objekt i dokumentet för att hämta samlingen av formulärfält:

```csharp
FormFieldCollection formFields = doc.Range.FormFields;
```

 Nu har du samlingen av formulärfält från Word-dokumentet lagrad i`formFields` variabel.

## Steg 3: Få åtkomst till och manipulera formulärfälten

Du kan iterera genom insamlingen av formulärfält och utföra olika operationer på varje formulärfält, som att hämta eller ställa in värden, ändra formatering eller extrahera information.

```csharp
foreach (FormField formField in formFields)
{
    // Få åtkomst till och manipulera varje formulärfält
    // ...
}
```

## Steg 4: Spara dokumentet

Spara slutligen det ändrade dokumentet om det behövs:

```csharp
doc.Save(dataDir + "ModifiedFormFields.docx");
```

Det är allt! Du har framgångsrikt hämtat samlingen av formulärfält från ett Word-dokument med Aspose.Words för .NET.

### Exempel på källkod för formulärfält Hämta formulärfältsamling med Aspose.Words för .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Form fields.docx");

FormFieldCollection formFields = doc.Range.FormFields;

// Få åtkomst till och manipulera formulärfälten efter behov
// ...

doc.Save(dataDir + "ModifiedFormFields.docx");
```

Använd gärna den här koden i dina egna projekt och modifiera den efter dina specifika krav.