---
title: Koptekst-voettekst maken
linktitle: Koptekst-voettekst maken
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u kop- en voetteksten in Word-documenten kunt toevoegen en aanpassen met Aspose.Words voor .NET. Deze stapsgewijze handleiding zorgt voor een professionele documentopmaak.
type: docs
weight: 10
url: /nl/net/working-with-headers-and-footers/create-header-footer/
---

Het toevoegen van kop- en voetteksten aan uw documenten kan de professionaliteit en leesbaarheid ervan vergroten. Met Aspose.Words voor .NET kunt u eenvoudig kop- en voetteksten voor uw Word-documenten maken en aanpassen. In deze zelfstudie leiden we u stap voor stap door het proces, zodat u deze functies naadloos kunt implementeren.

## Vereisten

Zorg ervoor dat u over het volgende beschikt voordat u begint:

-  Aspose.Words voor .NET: downloaden en installeren vanaf de[download link](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: zoals Visual Studio, om uw code te schrijven en uit te voeren.
- Basiskennis van C#: begrip van C# en .NET-framework.
- Voorbeelddocument: Een voorbeelddocument om de kop- en voetteksten toe te passen, of om een nieuw document te maken, zoals getoond in de tutorial.

## Naamruimten importeren

Eerst moet u de benodigde naamruimten importeren om toegang te krijgen tot de Aspose.Words-klassen en -methoden.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System;
```

## Stap 1: Definieer de documentmap

Definieer de map waar uw document zal worden opgeslagen. Dit helpt bij het effectief beheren van het pad.

```csharp
// Het pad naar de documentenmap
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

## Stap 2: Maak een nieuw document

 Maak een nieuw document en a`DocumentBuilder` om het toevoegen van inhoud te vergemakkelijken.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Configureer pagina-instelling

Stel de pagina-instellingen in, inclusief of de eerste pagina een andere kop-/voettekst zal hebben.

```csharp
Section currentSection = builder.CurrentSection;
PageSetup pageSetup = currentSection.PageSetup;

pageSetup.DifferentFirstPageHeaderFooter = true;
pageSetup.HeaderDistance = 20;
```

## Stap 4: Voeg een koptekst toe aan de eerste pagina

Ga naar het koptekstgedeelte voor de eerste pagina en configureer de koptekst.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderFirst);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;

builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.Font.Size = 14;

builder.Write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

## Stap 5: Voeg een primaire header toe

Ga naar het primaire koptekstgedeelte en voeg een afbeelding en tekst in.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);

// Voeg een afbeelding in de koptekst in
builder.InsertImage(dataDir + "Graphics Interchange Format.gif", 
    RelativeHorizontalPosition.Page, 10, RelativeVerticalPosition.Page, 10, 50, 50, WrapType.Through);

builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Aspose.Words Header/Footer Creation Primer.");
```

## Stap 6: Voeg een primaire voettekst toe

Ga naar de primaire voettekstsectie en maak een tabel om de voettekstinhoud op te maken.

```csharp
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);

builder.StartTable();
builder.CellFormat.ClearFormatting();
builder.InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);

// Paginanummering toevoegen
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
```

## Stap 7: Voeg inhoud en pagina-einden toe

Ga naar het einde van het document, voeg een pagina-einde toe en maak een nieuwe sectie met andere pagina-instellingen.

```csharp
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.PageBreak);
builder.InsertBreak(BreakType.SectionBreakNewPage);

currentSection = builder.CurrentSection;
pageSetup = currentSection.PageSetup;
pageSetup.Orientation = Orientation.Landscape;
pageSetup.DifferentFirstPageHeaderFooter = false;

currentSection.HeadersFooters.LinkToPrevious(false);
CopyHeadersFootersFromPreviousSection(currentSection);

HeaderFooter primaryFooter = currentSection.HeadersFooters[HeaderFooterType.FooterPrimary];
Row row = primaryFooter.Tables[0].FirstRow;
row.FirstCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 / 3);
row.LastCell.CellFormat.PreferredWidth = PreferredWidth.FromPercent(100 * 2 / 3);

doc.Save(dataDir + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```

## Stap 8: Kopieer kop- en voetteksten uit de vorige sectie

Als je kop- en voetteksten uit een vorige sectie opnieuw wilt gebruiken, kopieer ze dan en breng de nodige wijzigingen aan.

```csharp
private static void CopyHeadersFootersFromPreviousSection(Section section)
{
    Section previousSection = (Section)section.PreviousSibling;
    if (previousSection == null) return;

    section.HeadersFooters.Clear();

    foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    {
        section.HeadersFooters.Add(headerFooter.Clone(true));
    }
}
```

## Conclusie

Door deze stappen te volgen, kunt u kop- en voetteksten in uw Word-documenten effectief toevoegen en aanpassen met Aspose.Words voor .NET. Dit verbetert het uiterlijk en de professionaliteit van uw document, waardoor het leesbaarder en aantrekkelijker wordt.

## Veelgestelde vragen

### V1: Wat is Aspose.Words voor .NET?

Aspose.Words voor .NET is een bibliotheek waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, bewerken en converteren binnen .NET-toepassingen.

### Vraag 2: Kan ik afbeeldingen toevoegen aan de kop- of voettekst?

 Ja, u kunt eenvoudig afbeeldingen toevoegen aan de kop- of voettekst met behulp van de`DocumentBuilder.InsertImage` methode.

### Vraag 3: Hoe stel ik verschillende kop- en voetteksten in voor de eerste pagina?

 U kunt voor de eerste pagina verschillende kop- en voetteksten instellen met behulp van de`DifferentFirstPageHeaderFooter` eigendom van de`PageSetup` klas.

### V4: Waar kan ik meer documentatie over Aspose.Words vinden?

 Uitgebreide documentatie vindt u op de website[Aspose.Words API-documentatiepagina](https://reference.aspose.com/words/net/).

### V5: Is er ondersteuning beschikbaar voor Aspose.Words?

 Ja, Aspose biedt ondersteuning via hun[Helpforum](https://forum.aspose.com/c/words/8).
