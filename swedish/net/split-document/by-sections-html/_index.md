---
title: Efter avsnitt Html
linktitle: Efter avsnitt Html
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du delar upp ett Word-dokument i sektioner HTML med Aspose.Words för .NET med komplett kodexempel.
type: docs
weight: 10
url: /sv/net/split-document/by-sections-html/
---

det här exemplet kommer vi att visa dig hur du delar upp ett Word-dokument i separata sektioner i HTML-format med hjälp av funktionen By HTML Sections i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och generera separata HTML-dokument för varje avsnitt.

## Steg 1: Ladda dokumentet

För att komma igång, ange katalogen för ditt dokument och ladda dokumentet i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Steg 2: Dela upp dokumentet i avsnitt i HTML-format

Nu kommer vi att ställa in sparalternativen för att dela upp dokumentet i sektioner i HTML-format. Så här gör du:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Exempel på källkod för By Sections HTML med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen By HTML Sections i Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

Med denna kod kommer du att kunna dela upp ett Word-dokument i separata avsnitt i HTML-format med Aspose.Words för .NET.

Nu kan du skapa separata HTML-dokument för varje sektion av det ursprungliga dokumentet.



