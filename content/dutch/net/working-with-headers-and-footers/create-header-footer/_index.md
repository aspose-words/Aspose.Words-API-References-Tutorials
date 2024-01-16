---
title: Koptekst-voettekst maken
linktitle: Koptekst-voettekst maken
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u kop- en voetteksten in uw Word-documenten kunt maken met Aspose.Words voor .NET. Pas kop- en voetteksten voor elke pagina aan.
type: docs
weight: 10
url: /nl/net/working-with-headers-and-footers/create-header-footer/
---

Hier is een stapsgewijze handleiding waarin de volgende C#-broncode wordt uitgelegd voor het maken van kop- en voetteksten met behulp van Aspose.Words voor .NET-functionaliteit. Zorg ervoor dat u de Aspose.Words-bibliotheek in uw project hebt opgenomen voordat u deze code gebruikt.

## Stap 1: Stel het documentmappad in

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Zorg ervoor dat u het juiste pad opgeeft naar uw documentenmap waar het bewerkte document zal worden opgeslagen.

## Stap 2: Maak een document en een documentgenerator

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Hier maken we een exemplaar van de`Document` klasse en een exemplaar van de`DocumentBuilder` class waarmee we het document kunnen manipuleren en elementen kunnen toevoegen.

## Stap 3: Stel paginaparameters en eerste koptekst in

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

// Geef op of we willen dat de kop-/voetteksten van de eerste pagina verschillen van de andere pagina's.
// U kunt ook de eigenschap PageSetup.OddAndEvenPagesHeaderFooter gebruiken om op te geven
// verschillende kop-/voetteksten voor oneven en even pagina's.
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

We stellen de paginaparameters in, inclusief de koptekstafstand, en gaan vervolgens naar de hoofdkop (`HeaderPrimary`). We gebruiken de documentgenerator om tekst toe te voegen en de koptekst op te maken.

## Stap 4: Voeg een afbeelding en tekst in de hoofdkop in

```csharp
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
     RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words - Building headers/footers.");

builder. MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
```

We gebruiken de documentgenerator om een afbeelding in de linkerbovenhoek van de hoofdkop in te voegen, en vervolgens voegen we wat rechts uitgelijnde tekst toe.

## Stap 5: Voeg een tabel in de hoofdvoettekst in

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

## Stap 6: Voeg een nieuwe pagina toe en stel kop-/voetteksten in

```csharp
builder. InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder. CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Deze sectie heeft geen andere kop-/voettekst nodig voor de eerste pagina. We hebben slechts één titelpagina nodig in het document.
//en de kop-/voettekst voor deze pagina is al gedefinieerd in de vorige sectie.
pageSetup.DifferentFirstPageHeaderFooter = false;

// In deze sectie worden standaard de kop-/voetteksten van de vorige sectie weergegeven. Roep currentSection.HeadersFooters.LinkToPrevious(false) aan om deze link te verbreken,
// de paginabreedte is anders voor de nieuwe sectie, dus we moeten verschillende celbreedtes instellen voor een voetteksttabel.
currentSection.HeadersFooters.LinkToPrevious(false);

// Als we de reeds bestaande kop-/voetteksten voor deze sectie willen gebruiken,
//maar met een paar kleine wijzigingen kan het zinvol zijn om de kop- en voetteksten te kopiëren
// uit de vorige sectie en pas de nodige wijzigingen toe waar we ze willen hebben.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

// Bewaar het document
doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

 We voegen een pagina-einde en een sectie-einde toe om een nieuwe pagina te maken waarop de primaire kop-/voetteksten zichtbaar zijn. We stellen de parameters voor de nieuwe sectie in en gebruiken vervolgens de`CopyHeadersFootersFromPreviousSection` methode om de kop-/voetteksten uit de vorige sectie te kopiëren. Ten slotte stellen we de juiste celbreedtes in voor de hoofdvoetteksttabel en slaan we het document op.

### Voorbeeldbroncode om kop- en voetteksten te maken met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;
// Geef op of we willen dat de kop- en voetteksten van de eerste pagina verschillen van andere pagina's.
// U kunt ook de eigenschap PageSetup.OddAndEvenPagesHeaderFooter gebruiken om op te geven
// verschillende kop-/voetteksten voor oneven en even pagina's.
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

// Voeg een gepositioneerde afbeelding in de linkerbovenhoek van de koptekst in.
// De afstand vanaf de boven-/linkerrand van de pagina is ingesteld op 10 punten.
builder.InsertImage(ImagesDir + "Graphics Interchange Format.gif", RelativeHorizontalPosition.Page, 10,
	RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;

builder.Write("Aspose.Words Header/Footer Creation Primer.");

builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

// We gebruiken een tabel met twee cellen om één deel van de tekst op de regel te zetten (met paginanummering).
// Moet links uitgelijnd worden, en het overige deel van de tekst (met copyright) moet rechts uitgelijnd worden.
builder.StartTable();

builder.CellFormat.ClearFormatting();

builder.InsertCell();

builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Het gebruikt de velden PAGE en NUMPAGES om automatisch het huidige paginanummer en vele pagina's te berekenen.
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

// Maak een pagina-einde om een tweede pagina te maken waarop de primaire kop-/voetteksten te zien zijn.
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
// Deze sectie heeft geen andere kop-/voettekst op de eerste pagina nodig. We hebben slechts één titelpagina in het document nodig.
//en de kop-/voettekst voor deze pagina is al gedefinieerd in de vorige sectie.
pageSetup.DifferentFirstPageHeaderFooter = false;

// In deze sectie worden kop- en voetteksten uit de vorige sectie weergegeven
// Roep standaard currentSection.HeadersFooters.LinkToPrevious(false) aan om deze paginabreedte te annuleren
// is anders voor de nieuwe sectie, en daarom moeten we verschillende celbreedtes instellen voor een voetteksttabel.
currentSection.HeadersFooters.LinkToPrevious(false);

// Als we de reeds bestaande kop-/voettekstset voor deze sectie willen gebruiken.
// Maar met enkele kleine aanpassingen kan het handig zijn om kop- en voetteksten te kopiëren
// uit de vorige sectie en pas de nodige wijzigingen toe waar we ze willen hebben.
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];

Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

### Veelgestelde vragen

#### Vraag: Hoe kan ik een koptekst toevoegen aan mijn document in Aspose.Words?

 A: Om een koptekst aan uw document in Aspose.Words toe te voegen, kunt u de`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.HeaderPrimary)` methode. Deze methode voegt een primaire kop toe aan het eerste gedeelte van uw document.

#### Vraag: Hoe kan ik een voettekst toevoegen aan mijn document in Aspose.Words?

 A: Om een voettekst toe te voegen aan uw document in Aspose.Words, kunt u de`Document.FirstSection.HeadersFooters.Add(HeaderFooterType.FooterPrimary)`methode. Deze methode voegt een primaire voettekst toe aan het eerste gedeelte van uw document.

#### Vraag: Hoe kan ik tekst toevoegen aan mijn kop- of voettekst in Aspose.Words?

 A: Om tekst toe te voegen aan uw kop- of voettekst in Aspose.Words, kunt u de`HeaderFooter.Paragraphs` eigenschap om de alineaverzameling van de kop- of voettekst op te halen, en voeg vervolgens een alinea met uw tekst aan deze verzameling toe met behulp van de`ParagraphCollection.Add` methode.

#### Vraag: Kan ik de kop- of voettekstinhoud aanpassen met afbeeldingen en paginanummers in Aspose.Words?

 A: Ja, u kunt de kop- en voettekstinhoud aanpassen met afbeeldingen en paginanummers in Aspose.Words. Je kunt objecten gebruiken zoals`Shape` om afbeeldingen en objecten toe te voegen, zoals`Field` om paginanummers aan uw kop- of voettekst toe te voegen.

#### Vraag: Kan ik het lettertype, de grootte en de kleur van de tekst in mijn kop- of voettekst in Aspose.Words wijzigen?

 A: Ja, u kunt het lettertype, de grootte en de kleur van de tekst in uw kop- of voettekst in Aspose.Words wijzigen. U hebt toegang tot eigenschappen voor tekstopmaak, zoals`Font` om het lettertype te wijzigen,`Size` om de grootte aan te passen, en`Color`om de tekstkleur in te stellen.