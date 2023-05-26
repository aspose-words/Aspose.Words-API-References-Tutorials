---
title: Ersätt hyperlänkar
linktitle: Ersätt hyperlänkar
second_title: Aspose.Words för .NET API Referens
description: Ersätt hyperlänkar i Word-dokument med Aspose.Words för .NET. Steg-för-steg-instruktioner för att ersätta hyperlänkar.
type: docs
weight: 10
url: /sv/net/working-with-fields/replace-hyperlinks/
---

Här är en steg-för-steg-guide för att förklara följande C#-källkod för att ersätta hyperlänkar med Aspose.Words för .NET-funktionalitet. Se till att du har inkluderat Aspose.Words-biblioteket i ditt projekt innan du använder den här koden.

## Steg 1: Ange sökväg till dokumentkatalogen

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

 Var noga med att ange rätt sökväg till din dokumentkatalog som innehåller`Hyperlinks.docx` fil.

## Steg 2: Ladda dokumentet som innehåller hyperlänkarna

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

 Här skapar vi en instans av`Document` klass från den angivna filen.

## Steg 3: Bläddra i fälten för att hitta hyperlänkar

```csharp
foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Vissa hyperlänkar kan vara lokala (länkar till bokmärken inuti dokumentet), vi ignorerar dem.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}
```

 Denna loop går igenom alla fält i dokumentet och letar efter typfält`FieldType.FieldHyperlink` . När ett fält av den här typen har hittats kontrollerar vi om det är en lokal länk genom att markera`SubAddress` fast egendom. Om inte, ersätter vi länkadressen med`"http://www.aspose.com"`och resultatet med`"Aspose - The .NET & Java Component Editor"`.

## Steg 4: Spara det ändrade dokumentet

```csharp
doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Slutligen sparar vi det modifierade dokumentet med de ersatta hyperlänkarna till en specificerad fil.

### Exempel på källkod för att ersätta hyperlänkar med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document(dataDir + "Hyperlinks.docx");

foreach(Field field in doc.Range.Fields)
{
     if (field.Type == FieldType.FieldHyperlink)
     {
         FieldHyperlink hyperlink = (FieldHyperlink)field;

         // Vissa hyperlänkar kan vara lokala (länkar till bokmärken inuti dokumentet), vi ignorerar dem.
         if (hyperlink.SubAddress != null)
             keep on going;

         hyperlink.Address = "http://www.aspose.com";
         hyperlink.Result = "Aspose - The .NET & Java component editor";
     }
}

doc.Save(dataDir + "WorkingWithFields.ReplaceHyperlinks.docx");
```

Detta är exempel på källkod för att ersätta hyperlänkar i ett dokument med Aspose.Words för .NET.