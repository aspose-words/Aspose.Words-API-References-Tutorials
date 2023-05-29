---
title: Efter rubriker Html
linktitle: Efter rubriker Html
second_title: Aspose.Words för .NET API Referens
description: Steg-för-steg-guide för att förklara C#-källkoden för HTML-funktionen By Heading i Aspose.Words för .NET
type: docs
weight: 10
url: /sv/net/split-document/by-headings-html/
---
I den här handledningen går vi igenom hur du delar upp ett Word-dokument i mindre delar med hjälp av funktionen By HTML Heading i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och generera separata HTML-dokument baserat på Rubrik.

## Steg 1: Ladda dokumentet

För att komma igång, ange katalogen för ditt dokument och ladda dokumentet i ett dokumentobjekt. Här är hur:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Steg 2: Dela upp dokumentet efter rubrik i HTML-format

Nu kommer vi att ställa in sparaalternativ för att dela upp dokumentet i mindre delar baserat på Rubrik i HTML-format. Här är hur:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Dela upp dokumentet i mindre delar, i det här fallet separera det efter titel.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Exempel på källkod för By Headings HTML med Aspose.Words för .NET

Här är den fullständiga källkoden för funktionen By HTML Heading i Aspose.Words för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Dela upp ett dokument i mindre delar, i det här fallet delat efter rubrik.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

Med denna kod kommer du att kunna dela upp ett Word-dokument i mindre delar med Aspose.Words för .NET, baserat på rubriker. Du kan sedan generera separata HTML-dokument för varje del.

