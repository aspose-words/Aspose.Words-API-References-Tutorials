---
title: Hämta fältnamn för sammankoppling av brev
linktitle: Hämta fältnamn för sammankoppling av brev
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du får kopplingsfältnamn i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/get-mail-merge-field-names/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Get Merge Field Names" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet

Det första steget är att ladda dokumentet där du vill hämta sammanslagningsfältnamnen.

```csharp
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");
```

Se till att ersätta "DIN DOKUMENTFIL" med namnet på din egen fil.

## Steg 3: Hämta sammanslagningsfältnamn

 Vi använder`GetFieldNames()` metod för att få en array som innehåller namnen på de sammanslagningsfält som finns i dokumentet.

```csharp
string[] fieldNames = doc.MailMerge.GetFieldNames();
```

 De`fieldNames` variabeln innehåller nu namnen på sammanslagningsfälten.

### Källkodsexempel för Get Merge-fältnamn med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet.
Document doc = new Document(dataDir + "YOUR DOCUMENT FILE");

// Hämta sammanslagna fältnamn.
string[] fieldNames = doc.MailMerge.GetFieldNames();

// Visa antalet sammanslagningsfält.
Console.WriteLine("\nDocument contains " + fieldNames.Length + " merge fields.");
```

 I det här exemplet laddade vi ett dokument, fick sammanslagningsfältsnamnen med hjälp av`GetFieldNames()` metod och visade antalet sammanslagningsfält som finns i dokumentet.

Detta avslutar vår guide om hur du använder funktionen "Get Merge Field Names" med Aspose.Words för .NET.