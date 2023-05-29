---
title: Läs Markdown Document
linktitle: Läs Markdown Document
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du läser markdown-dokument med Aspose.Words för .NET Steg-för-steg-guide.
type: docs
weight: 10
url: /sv/net/working-with-markdown/read-markdown-document/
---

I det här exemplet kommer vi att gå igenom hur du läser ett Markdown-dokument med Aspose.Words för .NET Markdown är ett lättviktigt uppmärkningsspråk som används för att formatera vanlig text.

## Steg 1: Läser Markdown-dokumentet

 Först använder vi`Document` klass för att läsa Markdown-dokumentet. Vi måste ange sökvägen till Markdown-filen som ska läsas.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");
```

## Steg 2: Ta bort rubrikformatering

Vi kan ta bort formateringen från rubriken i dokumentets sista stycke. I det här exemplet tilldelar vi stycket stilen "Citat".

```csharp
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];
```

## Steg 3: Spara dokumentet

Slutligen kan vi spara dokumentet i önskat format.

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

### Exempel på källkod för att läsa ett Markdown-dokument med Aspose.Words för .NET


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Quotes.md");

// Låt oss ta bort rubrikformatering från ett citat i det allra sista stycket.
Paragraph paragraph = doc.FirstSection.Body.LastParagraph;
paragraph.ParagraphFormat.Style = doc.Styles["Quote"];

doc.Save(dataDir + "WorkingWithMarkdown.ReadMarkdownDocument.md");
```

Grattis! Du har nu lärt dig hur du läser ett Markdown-dokument med Aspose.Words för .NET.

