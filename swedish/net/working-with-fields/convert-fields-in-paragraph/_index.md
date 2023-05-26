---
title: Konvertera fält i stycke
linktitle: Konvertera fält i stycke
second_title: Aspose.Words för .NET API Referens
description: Konvertera IF-fält till vanlig text i ett stycke med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/convert-fields-in-paragraph/
---

Här är en handledning som visar hur du använder funktionen Konvertera fält till stycke med Aspose.Words för .NET. Denna kod konverterar alla IF-typfält som påträffas i det sista stycket i ett dokument till vanlig text. Följ stegen nedan för att förstå och köra den här koden.

Se till att du har installerat Aspose.Words för .NET och ställ in din utvecklingsmiljö innan du börjar.

## Steg 1: Importera referenser

För att använda Aspose.Words i ditt projekt måste du lägga till nödvändiga referenser. Se till att du har lagt till en referens till Aspose.Words-biblioteket i ditt projekt.

## Steg 2: Ladda dokumentet

Innan du kan konvertera fält måste du ladda dokumentet som innehåller fälten som ska konverteras. Var noga med att ange rätt sökväg till katalogen som innehåller dokumentet. Så här laddar du upp dokumentet:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet.
Document doc = new Document(dataDir + "Linked fields.docx");
```

Ersätt "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din dokumentkatalog.

## Steg 3: Konvertera fält till text

Nu när dokumentet är laddat kan vi fortsätta med att konvertera typfälten till vanlig text. I det här exemplet riktar vi oss endast mot fälten i dokumentets sista stycke. Här är koden som utför denna konvertering:

```csharp
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());
```

 Den här koden använder en kombination av LINQ-metoder för att filtrera bort fält i dokumentets sista stycke och konverterar dem sedan till vanlig text genom att anropa`Unlink()` metod.

## Steg 4: Spara det ändrade dokumentet

 När fälten har konverterats kan du spara det ändrade dokumentet. Använd`Save()` metod för detta. Här är ett exempel :

```csharp
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```

Var noga med att ange rätt sökväg och filnamn för säkerhetskopian.

### Källkodsexempel för Convert Fields In Paragraph med Aspose.Words för .NET

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet.
Document doc = new Document(dataDir + "Linked fields.docx");

// Konvertera IF-fält till vanlig text i dokumentets sista stycke.
doc.FirstSection.Body.LastParagraph.Range.Fields
     .Where(f => f.Type == FieldType.FieldIf)
     .ToList()
     .ForEach(f => f.Unlink());

// Spara det ändrade dokumentet.
doc.Save(dataDir + "WorkingWithFields.TestFile.docx");
```
