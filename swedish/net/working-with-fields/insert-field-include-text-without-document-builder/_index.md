---
title: Infoga FieldIncludeText utan dokumentbyggare
linktitle: Infoga FieldIncludeText utan dokumentbyggare
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar ett FieldIncludeText-fält i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-field-include-text-without-document-builder/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Infoga ett FieldIncludeText-fält" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet och stycket

Vi börjar med att skapa ett nytt dokument och initialisera ett stycke.

```csharp
Document doc = new Document();
Paragraph para = new Paragraph(doc);
```

## Steg 3: Infoga fältet FieldIncludeText

 Vi använder`AppendField()` metod för att infoga ett FieldIncludeText-fält i stycket.

```csharp
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);
```

Vi konfigurerar sedan egenskaperna för FieldIncludeText-fältet genom att ange namnet på bokmärket och namnet på källfilen.

```csharp
fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";
```

Därefter lägger vi till stycket i dokumentets brödtext.

```csharp
doc.FirstSection.Body.AppendChild(para);
```

 Slutligen kallar vi`Update()` metod för att uppdatera fältet.

```csharp
fieldIncludeText.Update();
```

### Exempel på källkoden för att infoga ett FieldIncludeText-fält med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapa dokumentet och stycket.
Document doc = new Document();
Paragraph para = new Paragraph(doc);

// Infoga fältet FieldIncludeText.
FieldIncludeText fieldIncludeText = (FieldIncludeText)para.AppendField(FieldType.FieldIncludeText, false);

fieldIncludeText.BookmarkName = "bookmark";
fieldIncludeText.SourceFullName = MyDir + "IncludeText.docx";

doc.FirstSection.Body.AppendChild(para);

fieldIncludeText.Update();

doc.Save(dataDir + "InsertionFieldFieldIncludeTextWithoutDocumentBuilder.docx");
```

I det här exemplet skapade vi ett nytt dokument, initierade ett stycke, infogade en FieldIncludeTexten som anger bokmärkesnamnet och källfilens namn och sparade dokumentet med ett specificerat filnamn.

Detta avslutar vår guide om hur du använder funktionen "Insert a FieldIncludeText" med Aspose.Words för .NET.