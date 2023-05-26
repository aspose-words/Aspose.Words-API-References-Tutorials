---
title: Infoga fält
linktitle: Infoga fält
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar ett fält i dina Word-dokument med Aspose.Words för .NET. Anpassa dina dokument med dynamiska fält.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-field/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Infoga ett fält" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa Document and DocumentBuilder

Vi börjar med att skapa ett nytt dokument och initiera en DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga fältet

 Vi använder`InsertField()` metod för DocumentBuilder för att infoga ett fält i dokumentet. I det här exemplet infogar vi ett sammanfogningsfält (MERGEFIELD) med fältnamnet "MyFieldName" och sammanslagningsformat.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Exempel på källkoden för att infoga ett fält med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga fältet.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

det här exemplet skapade vi ett nytt dokument, initierade en DocumentBuilder och infogade sedan ett sammanfogningsfält med fältnamnet "MyFieldName" och sammanslagningsformat. Dokumentet sparas sedan med ett angivet filnamn.

Detta avslutar vår guide om hur du använder funktionen "Infoga ett fält" med Aspose.Words för .NET.
