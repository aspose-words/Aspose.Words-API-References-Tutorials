---
title: Ändra Toc Tab Stops
linktitle: Ändra Toc Tab Stops
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ändrar innehållsförteckningsflikar i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words för .NET är ett kraftfullt bibliotek för att skapa, redigera och manipulera Word-dokument i en C#-applikation. Bland funktionerna som erbjuds av Aspose.Words finns möjligheten att ändra flikarna som används i en innehållsförteckning i ett Word-dokument. I den här guiden kommer vi att visa dig hur du använder C#-källkoden för Aspose.Words för .NET för att ändra flikar i ett dokuments innehållsförteckning.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett populärt bibliotek som gör arbetet med Word-dokument enkelt och effektivt. Den erbjuder ett brett utbud av funktioner för att skapa, redigera och manipulera Word-dokument, inklusive att ändra innehållsförteckningsflikar.

## Laddar dokumentet som innehåller innehållsförteckningen

Det första steget är att ladda Word-dokumentet som innehåller innehållsförteckningen du vill ändra. Använd klassen Document för att ladda dokumentet från källfilen. Här är ett exempel :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

det här exemplet laddar vi dokumentet "Table of contents.docx" som finns i dokumentkatalogen.

## Ändra flikar i innehållsförteckningen

När dokumentet har laddats går vi igenom varje stycke i dokumentet och kontrollerar om det är formaterat med resultatstilarna för innehållsförteckningen (TOC). Om så är fallet, ändrar vi flikarna som används för att anpassa sidnumren. Här är hur:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

I det här exemplet använder vi en loop för att gå igenom varje stycke i dokumentet. Vi kontrollerar sedan om stycket är formaterat med hjälp av Table of Contents Result (TOC) stilar. Om så är fallet kommer vi åt den första fliken som används i detta stycke och ändrar den genom att ta bort den gamla fliken och lägga till en ny flik med en modifierad position.

## Spara ändrat dokument

När du har gjort de nödvändiga ändringarna av flikarna i innehållsförteckningen kan du spara det ändrade dokumentet med hjälp av Spara-metoden för klassen Dokument. Här är ett exempel :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

I det här exemplet sparar vi det ändrade dokumentet som "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Exempel på källkod för funktionen "Redigera innehållsförteckningsflikar" med Aspose.Words för .NET

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Ladda dokumentet som innehåller innehållsförteckningen
Document doc = new Document(dataDir + "Table of contents.docx");

// Ändra flikarna i innehållsförteckningen
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Spara det ändrade dokumentet
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Slutsats

I den här guiden har vi tagit upp hur man använder Aspose.Words för .NET för att ändra flikarna i innehållsförteckningen i ett Word-dokument med hjälp av den medföljande C#-källkoden. Genom att följa de angivna stegen kan du enkelt anpassa innehållsförteckningsflikarna i dina Word-dokument i ditt C#-program. Aspose.Words erbjuder enorm flexibilitet och kraft att arbeta med stilarna och formateringen av dina dokument, vilket gör att du kan skapa attraktiva och professionella Word-dokument.