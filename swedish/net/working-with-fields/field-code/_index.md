---
title: Fältkod
linktitle: Fältkod
second_title: Aspose.Words för .NET API Referens
description: Steg för steg guide för att få fältkod och fältresultat i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/field-code/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Hämta fältkod" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet

Det första steget är att ladda upp dokumentet där du vill hämta fältkoderna.

```csharp
Document doc = new Document(dataDir + "Hyperlinks.docx");
```

Se till att ersätta "Hyperlinks.docx" med namnet på din egen fil.

## Steg 3: Bläddra i dokumentfält

 Vi använder a`foreach` loop till loop genom alla fält som finns i dokumentet.

```csharp
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;
}
```

 Vid varje iteration av slingan får vi fältkoden med hjälp av`GetFieldCode()` metod. Vi lagrar även resultatet av fältet i en variabel.

### Källkodsexempel för Get Field Code med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet.
Document doc = new Document(dataDir + "Hyperlinks.docx");

// Gå igenom dokumentfälten.
foreach(Field field in doc.Range.Fields)
{
     string fieldCode = field.GetFieldCode();
     string fieldResult = field.Result;

     // Gör något med fältets kod och resultat.
}
```

det här exemplet laddade vi ett dokument och bläddrade sedan igenom alla fält som fanns i dokumentet. Vid varje iteration fick vi koden och resultatet av fältet. Du kan lägga till din egen logik för att bearbeta koden och resultatfälten efter behov.

Detta avslutar vår guide om hur du använder funktionen "Hämta fältkod" med Aspose.Words för .NET.