---
title: Ändra Toc-flikstopp i Word-dokument
linktitle: Ändra Toc-flikstopp i Word-dokument
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ändrar innehållsförteckningsflikar i ett Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words för .NET är ett kraftfullt bibliotek för att skapa, redigera och manipulera Word-dokument i en C#-applikation. Bland funktionerna som erbjuds av Aspose.Words finns möjligheten att ändra flikarna som används i en innehållsförteckning i ett Word-dokument. I den här guiden kommer vi att visa dig hur du använder C#-källkoden för Aspose.Words för .NET för att ändra flikar i ett dokuments innehållsförteckning.

## Förstå Aspose.Words-biblioteket

Innan du dyker in i koden är det viktigt att förstå Aspose.Words-biblioteket för .NET. Aspose.Words är ett populärt bibliotek som gör ordbehandling med Word-dokument enkelt och effektivt. Den erbjuder ett brett utbud av funktioner för att skapa, redigera och manipulera Word-dokument, inklusive att ändra innehållsförteckningsflikar.

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

### Vanliga frågor om ändring av tabbstopp i Word-dokument

#### F: Vad är syftet med "Change Toc Tab Stops in Word Document"-funktionen i Aspose.Words för .NET?

S: Funktionen "Change Toc Tab Stops In Word Document" i Aspose.Words för .NET låter dig ändra tabbstoppen som används i innehållsförteckningen i ett Word-dokument. Det gör att du kan anpassa justeringen och placeringen av sidnumren och motsvarande rubriker i innehållsförteckningen.

#### F: Vad är Aspose.Words för .NET?

S: Aspose.Words för .NET är ett kraftfullt bibliotek designat för ordbehandling med Word-dokument i .NET-applikationer. Den tillhandahåller omfattande funktioner för att skapa, redigera, manipulera och konvertera Word-dokument programmatiskt med C# eller andra .NET-språk.

#### F: Hur laddar jag ett Word-dokument som innehåller en innehållsförteckning med Aspose.Words för .NET?

 S: För att ladda ett Word-dokument som innehåller en innehållsförteckning med Aspose.Words för .NET, kan du använda`Document` klass och dess konstruktör. Genom att ange filsökvägen till dokumentet kan du ladda det i en`Document` objekt. Här är ett exempel:

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

Detta kodavsnitt laddar dokumentet "Table of contents.docx" som finns i den angivna katalogen.

#### F: Hur kan jag ändra flikarna som används i innehållsförteckningen med Aspose.Words för .NET?

S: När dokumentet har laddats kan du iterera genom varje stycke i dokumentet och kontrollera om det är formaterat med resultatstilarna för innehållsförteckningen (TOC). Om ett stycke är formaterat som ett innehållsförteckningsformat kan du ändra flikarna som används för att justera sidnumren. I Aspose.Words för .NET kan du komma åt`ParagraphFormat` egenskapen för varje stycke för att hämta och ändra tabbstoppen. Här är ett exempel:

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

I den här koden itererar loopen genom varje stycke i dokumentet. Om ett stycke har en innehållsförteckningsstil, kommer det åt det första tabbstoppet som används i det stycket, tar bort det och lägger till ett nytt tabbstopp med en modifierad position.

#### F: Kan jag ändra flikarna för flera nivåer i innehållsförteckningen med Aspose.Words för .NET?

S: Ja, du kan ändra flikarna för flera nivåer i innehållsförteckningen med Aspose.Words för .NET. Genom att iterera genom varje stycke och kontrollera innehållsförteckningen kan du ändra flikarna för varje nivå individuellt. Du kan komma åt önskad nivå i innehållsförteckningen och justera tabbstoppen därefter.

#### F: Hur sparar jag det ändrade dokumentet efter att ha ändrat flikarna i innehållsförteckningen med Aspose.Words för .NET?

 S: Efter att ha gjort nödvändiga ändringar av flikarna i innehållsförteckningen kan du spara det ändrade dokumentet med hjälp av`Save` metod för`Document` klass. Ange önskad filsökväg och namn för utdatadokumentet som en parameter till`Save` metod. Här är ett exempel:

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

Denna kod sparar det ändrade dokumentet som "WorkingWithTableOfContent.ChangeTocTabStops.docx".

#### F: Kan jag anpassa andra aspekter av innehållsförteckningen med Aspose.Words för .NET?

S: Ja, med Aspose.Words för .NET kan du anpassa olika aspekter av innehållsförteckningen. Förutom att ändra flikarna kan du ändra teckensnittsstilar, storlek, justering och andra formateringsegenskaper för innehållsförteckningsposter och sidnummer. Dessutom kan du justera indrag, avstånd och formatering av motsvarande rubriker.

#### F:. Kan jag ändra flikinriktningen och ledartecken för innehållsförteckningen med Aspose.Words för .NET?

S: Ja, du kan ändra tabbjustering och ledartecken för innehållsförteckningen med Aspose.Words för .NET. Genom att komma åt tabbstoppen och justera deras justering och ledaregenskaper kan du styra justeringen och det visuella utseendet på sidnumren och motsvarande rubriker i innehållsförteckningen.

#### F: Har Aspose.Words för .NET stöd för att ändra andra stilar och formatering i Word-dokument?

S: Ja, Aspose.Words för .NET ger omfattande stöd för att ändra olika stilar och formatering i Word-dokument. Det låter dig ändra stilar för olika element som stycken, rubriker, tabeller, listor och mer. Du kan ändra teckensnitt, färger, justering, indrag, avstånd och andra formateringsaspekter enligt dina krav.

#### F: Kan jag ändra flikarna i innehållsförteckningen i ett befintligt Word-dokument med Aspose.Words för .NET?

S: Ja, du kan ändra flikarna i innehållsförteckningen i ett befintligt Word-dokument med Aspose.Words för .NET. Genom att ladda dokumentet, iterera genom styckena och göra nödvändiga ändringar i flikstoppen kan du uppdatera flikarna i innehållsförteckningen. Spara slutligen dokumentet för att tillämpa ändringarna.