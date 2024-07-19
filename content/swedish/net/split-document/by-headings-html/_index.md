---
title: Dela Word-dokument efter rubriker Html
linktitle: Efter rubriker Html
second_title: Aspose.Words Document Processing API
description: Steg-för-steg-guide för att förklara C#-källkoden för det delade Word-dokumentet By Heading HTML-funktionen i Aspose.Words för .NET
type: docs
weight: 10
url: /sv/net/split-document/by-headings-html/
---
I den här handledningen går vi igenom hur du delar upp ett Word-dokument i mindre delar med hjälp av funktionen By HTML Heading i Aspose.Words för .NET. Följ stegen nedan för att förstå källkoden och generera separata HTML-dokument baserat på Rubrik.

## Steg 1: Ladda dokumentet

För att komma igång, ange katalogen för ditt dokument och ladda dokumentet i ett dokumentobjekt. Här är hur:

```csharp
//Sökväg till dokumentkatalogen.
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

## Slutsats

 I den här handledningen lärde vi oss hur man delar upp ett Word-dokument i mindre delar med hjälp av funktionen By HTML Heading i Aspose.Words för .NET. Genom att specificera`DocumentSplitCriteria` som`HeadingParagraph` i`HtmlSaveOptions`, kunde vi generera separata HTML-dokument baserat på rubrikerna i originaldokumentet.

Att dela upp ett dokument efter rubriker kan vara användbart för att organisera och hantera innehåll, särskilt i stora dokument med flera sektioner. Aspose.Words för .NET tillhandahåller en pålitlig och effektiv lösning för att hantera dokumentdelning och generera utdata i olika format.

Utforska gärna ytterligare funktioner och alternativ som tillhandahålls av Aspose.Words för .NET för att ytterligare förbättra dina dokumentbehandlingsmöjligheter och effektivisera ditt arbetsflöde.

### Vanliga frågor

#### Hur kan jag dela upp ett Word-dokument i mindre delar baserat på rubriker med Aspose.Words för .NET?

 För att dela upp ett Word-dokument baserat på rubriker kan du använda funktionen By HTML Heading i Aspose.Words för .NET. Följ den medföljande källkoden och ställ in`DocumentSplitCriteria` till`HeadingParagraph` i`HtmlSaveOptions` objekt. Detta kommer att dela upp dokumentet i mindre delar vid varje rubrik.

#### Vilka format kan jag dela upp Word-dokumentet i?

 Den medföljande källkoden visar att Word-dokumentet delas upp i mindre delar i HTML-format. Men Aspose.Words för .NET stöder olika utdataformat, inklusive DOCX, PDF, EPUB och mer. Du kan ändra koden och ange önskat utdataformat i`HtmlSaveOptions` invända i enlighet därmed.

#### Kan jag välja ett annat kriterium för att dela upp dokumentet?

Ja, du kan välja andra kriterier för att dela upp dokumentet baserat på dina krav. Aspose.Words för .NET tillhandahåller flera kriteriealternativ, som t.ex`HeadingParagraph`, `Page`, `Section` , och mer. Ändra`DocumentSplitCriteria` egendom i`HtmlSaveOptions` objekt för att välja lämpliga kriterier för delning.

#### Hur kan jag anpassa HTML-utdata för de delade delarna?

 Aspose.Words för .NET låter dig anpassa HTML-utdata för de delade delarna genom att ange ytterligare alternativ i`HtmlSaveOptions` objekt. Du kan styra olika aspekter som CSS-stilar, bilder, typsnitt och mer. Se Aspose.Words-dokumentationen för mer information om anpassning av HTML-utdata.

#### Kan jag dela upp dokumentet baserat på flera kriterier?

 Ja, du kan dela upp dokumentet baserat på flera kriterier genom att kombinera kriteriealternativen därefter. Du kan till exempel dela upp dokumentet efter både rubrik och sida genom att ställa in`DocumentSplitCriteria`egendom till`HeadingParagraph | Page`. Detta kommer att dela upp dokumentet vid varje rubrik och varje sida, vilket skapar mindre delar baserat på båda kriterierna.