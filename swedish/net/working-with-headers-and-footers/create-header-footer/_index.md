---
title: Skapa sidhuvud
linktitle: Skapa sidhuvud
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du skapar sidhuvuden och sidfötter i dina Word-dokument med Aspose.Words för .NET. Anpassa sidhuvuden och sidfötter för varje sida.
type: docs
weight: 10
url: /sv/net/working-with-headers-and-footers/create-header-footer/
---

Här är en steg-för-steg-guide för att förklara följande C#-källkod för att skapa sidhuvuden och sidfötter med Aspose.Words för .NET-funktionalitet. Se till att du har inkluderat Aspose.Words-biblioteket i ditt projekt innan du använder den här koden.

## Steg 1: Ange sökväg till dokumentkatalogen

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Var noga med att ange rätt sökväg till din dokumentkatalog där det redigerade dokumentet kommer att sparas.

## Steg 2: Skapa ett dokument och en dokumentgenerator

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Här skapar vi en instans av`Document` klass och en instans av`DocumentBuilder` klass som gör att vi kan manipulera dokumentet och lägga till element.

## Steg 3: Ställ in sidparametrar och första rubrik

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Ange om vi vill att sidhuvuden/sidfötter på den första sidan ska skilja sig från de andra sidorna.
// Du kan också använda egenskapen PageSetup.OddAndEvenPagesHeaderFooter för att ange
// olika sidhuvuden/sidfötter för udda och jämna sidor.
pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;

builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words - Creating Headers/Footers - Title Page.");

pageSetup.HeaderDistance = 20;
builder. MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
```

Vi ställer in sidparametrarna, inklusive rubrikens avstånd, och flyttar sedan till huvudhuvudet (`HeaderPrimary`). Vi använder dokumentgeneratorn för att lägga till text och formatera rubriken.

## Steg 4: Infoga en bild och text i huvudhuvudet

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

Vi använder dokumentgeneratorn för att infoga en bild i det övre vänstra hörnet av huvudhuvudet, sedan lägger vi till lite högerjusterad text.

## Steg 5: Infoga en tabell i sidfoten

```csharp
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

builder.Write("Page ");
builder.InsertField("PAGE", "");
builder.Write(" of ");
builder.InsertField("NUMPAGES", "");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.EndRow();
builder.EndTable();

builder.MoveToDocumentEnd();
```

## Steg 6: Lägg till en ny sida och ställ in sidhuvuden/sidfötter

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
//Det här avsnittet behöver inte en annan sidhuvud/sidfot för den första sidan, vi behöver bara en titelsida i dokumentet,
// och sidhuvudet/sidfoten för den här sidan har redan definierats i föregående avsnitt.
pageSetup.DifferentFirstPageHeaderFooter = false;

// Det här avsnittet visar sidhuvuden/sidfötter för föregående avsnitt som standard, anrop currentSection.HeadersFooters.LinkToPrevious(false) för att bryta denna länk,
// sidbredden är annorlunda för det nya avsnittet, så vi måste ställa in olika cellbredder för en sidfotstabell.
currentSection.HeadersFooters.LinkToPrevious(false);

// Om vi vill använda de redan befintliga sidhuvuden/sidfötter för detta avsnitt,
// men med några mindre ändringar kan det vara vettigt att kopiera sidhuvuden/sidfötter
// från föregående avsnitt och tillämpa de nödvändiga ändringarna där vi vill ha dem.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Spara dokumentet
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 Vi lägger till en sidbrytning och en sektionsbrytning för att skapa en ny sida där de primära sidhuvuden/sidfötter kommer att synas. Vi ställer in parametrarna för den nya sektionen, sedan använder vi`CopyHeadersFootersFromPreviousSection`metod för att kopiera sidhuvuden/sidfötter från föregående avsnitt. Slutligen ställer vi in lämpliga cellbredder för huvudsidfotstabellen och sparar dokumentet.

### Exempel på källkod för att skapa sidhuvuden och sidfötter med Aspose.Words för .NET

```csharp
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	Section currentSection = builder.CurrentSection;
	PageSetup pageSetup = currentSection.PageSetup;
	// Ange om vi vill att sidhuvuden/sidfötter på första sidan ska skilja sig från andra sidor.
	// Du kan också använda egenskapen PageSetup.OddAndEvenPagesHeaderFooter för att ange
	// olika sidhuvuden/sidfötter för udda och jämna sidor.
	pageSetup.DifferentFirstPageHeaderFooter = true;
	pageSetup.HeaderDistance = 20;

	builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.Font.Size = 14;

	builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");

	pageSetup.HeaderDistance = 20;
	builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

	// Infoga en positionerad bild i det övre/vänstra hörnet av rubriken.
	// Avståndet från sidans övre/vänsterkant är satt till 10 punkter.
	builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
		RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

	builder.Write("Aspose.Words Header/Footer Creation Primer.");

	builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

	// Vi använder en tabell med två celler för att göra en del av texten på raden (med sidnumrering).
	// Att justeras till vänster och den andra delen av texten (med upphovsrätt) ska justeras till höger.
	builder.StartTable();

	builder.CellFormat.ClearFormatting();

	builder.InsertCell();

	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

	// Den använder PAGE- och NUMPAGES-fälten för att automatiskt beräkna det aktuella sidnumret och många sidor.
	builder.Write("Page ");
	builder.InsertField("PAGE", "");
	builder.Write(" of ");
	builder.InsertField("NUMPAGES", "");

	builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Left;

	builder.InsertCell();

	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

	builder.Write("(C) 2001 Aspose Pty Ltd. All rights reserved.");

	builder.CurrentParagraph.ParagraphFormat.Alignment = ParagraphAlignment.Right;

	builder.EndRow();
	builder.EndTable();

	builder.MoveToDocumentEnd();

	// Gör en sidbrytning för att skapa en andra sida där de primära sidhuvuden/sidfötterna kommer att synas.
	builder.InsertBreak(BreakType.PageBreak);
	builder.InsertBreak(BreakType.SectionBreakNewPage);

	currentSection = builder.CurrentSection;
	pageSetup = currentSection.PageSetup;
	pageSetup.Orientation = Orientation.Landscape;
	//Det här avsnittet behöver inte en annan sidhuvud/sidfot på första sidan vi behöver bara en titelsida i dokumentet,
	// och sidhuvudet/sidfoten för den här sidan har redan definierats i föregående avsnitt.
	pageSetup.DifferentFirstPageHeaderFooter = false;

	// Det här avsnittet visar sidhuvuden/sidfötter från föregående avsnitt
	// anrop som standard currentSection.HeadersFooters.LinkToPrevious(false) för att avbryta denna sidbredd
	// är annorlunda för det nya avsnittet, och därför måste vi ställa in olika cellbredder för en sidfotstabell.
	currentSection.HeadersFooters.LinkToPrevious(false);

	// Om vi vill använda den redan befintliga sidhuvud/sidfotsuppsättningen för detta avsnitt.
	// Men med några mindre ändringar kan det vara lämpligt att kopiera sidhuvuden/sidfötter
	// från föregående avsnitt och tillämpa nödvändiga ändringar där vi vill ha dem.
	CopyHeadersFootersFromPreviousSection(currentSection);

	HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

	Row row = primaryFooter.Tables[0].FirstRow;
	row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
	row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

	doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```
