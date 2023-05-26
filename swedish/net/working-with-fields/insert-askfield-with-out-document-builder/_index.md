---
title: Infoga ASKField Without Document Builder
linktitle: Infoga ASKField Without Document Builder
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du infogar ett ASK-fält i dina Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-fields/insert-askfield-with-out-document-builder/
---

Här är en steg-för-steg-guide för att förklara C#-källkoden nedan, som använder funktionen "Infoga ett ASK-fält utan DocumentBuilder" i Aspose.Words för .NET. Se till att följa varje steg noggrant för att få önskat resultat.

## Steg 1: Installation av dokumentkatalog

I den angivna koden måste du ange katalogen för dina dokument. Ersätt värdet "DIN DOKUMENTKATOLOG" med lämplig sökväg till din dokumentkatalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Skapa dokumentet och stycket

Vi börjar med att skapa ett nytt dokument och hämta första stycket.

```csharp
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
```

## Steg 3: Infoga fältet ASK

 Vi använder`AppendField()` metod för att infoga ett ASK-fält i stycket.

```csharp
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);
```

Vi konfigurerar sedan de olika egenskaperna för ASK-fältet genom att ange önskade värden.

```csharp
field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;
```

 Slutligen kallar vi`Update()` metod för att uppdatera fältet.

```csharp
field. Update();
```

### Exempel på källkoden för att infoga ett ASK-fält utan DocumentBuilder med Aspose.Words för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Skapande av dokument.
Document doc = new Document();
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];

// Infoga fältet FRÅGA.
FieldAsk field = (FieldAsk)para.AppendField(FieldType.FieldAsk, false);

field.BookmarkName = "Test 1";
field. PromptText = "Test2";
field. DefaultResponse = "Test3";
field. PromptOnceOnMailMerge = true;

field. Update();

doc.Save(dataDir + "InsertionChampASKSansDocumentBuilder.docx");
```

I det här exemplet skapade vi ett nytt dokument, infogade ett ASK-fält utan att använda DocumentBuilder, konfigurerade fältets olika egenskaper och sparade dokumentet med ett angivet filnamn.

Detta avslutar vår guide om hur du använder funktionen "Infoga ASK-fält utan DocumentBuilder" med Aspose.Words för .NET.