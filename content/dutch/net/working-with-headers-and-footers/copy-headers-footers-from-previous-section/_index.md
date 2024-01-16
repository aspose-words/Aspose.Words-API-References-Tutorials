---
title: Kopieer kopteksten en voetteksten uit de vorige sectie
linktitle: Kopieer kopteksten en voetteksten uit de vorige sectie
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u kop- en voetteksten uit de vorige sectie in Word-documenten kopieert met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-headers-and-footers/copy-headers-footers-from-previous-section/
---

In deze stapsgewijze zelfstudie begeleiden we u bij het kopiëren van kop- en voetteksten uit de vorige sectie in een Word-document met Aspose.Words voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Om aan de slag te gaan, moet u ervoor zorgen dat Aspose.Words voor .NET is geïnstalleerd en ingesteld in uw ontwikkelomgeving. Als u dit nog niet hebt gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Toegang tot het vorige gedeelte

 Haal eerst het vorige gedeelte op door naar het bestand te gaan`PreviousSibling` eigenschap van de huidige sectie:

```csharp
Section previousSection = (Section)section.PreviousSibling;
```

## Stap 2: Controleren op vorige sectie

Controleer vervolgens of er een vorige sectie bestaat. Als er geen vorige sectie is, retourneren we eenvoudigweg:

```csharp
if (previousSection == null)
    return;
```

## Stap 3: Kop- en voetteksten wissen en kopiëren

Om de kop- en voetteksten van de vorige sectie naar de huidige sectie te kopiëren, wissen we de bestaande kop- en voetteksten in de huidige sectie en doorlopen we vervolgens de kop- en voetteksten van de vorige sectie om gekloonde kopieën aan de huidige sectie toe te voegen:

```csharp
section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));
```

## Stap 4: Het document opslaan

Sla ten slotte het gewijzigde document op:

```csharp
doc.Save("OutputDocument.docx");
```

Dat is het! U hebt met succes kop- en voetteksten van de vorige sectie naar de huidige sectie in een Word-document gekopieerd met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor het kopiëren van kopteksten en voetteksten uit de vorige sectie met Aspose.Words voor .NET

```csharp
Section previousSection = (Section)section.PreviousSibling;

if (previousSection == null)
    return;

section.HeadersFooters.Clear();

foreach (HeaderFooter headerFooter in previousSection.HeadersFooters)
    section.HeadersFooters.Add(headerFooter.Clone(true));

doc.Save("OutputDocument.docx");
```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke vereisten.

### Veelgestelde vragen

#### Vraag: Hoe kan ik de kop- en voetteksten uit de vorige sectie kopiëren naar Aspose.Words?

 A: Om kop- en voetteksten uit de vorige sectie naar Aspose.Words te kopiëren, kunt u de`CopyHeadersFootersFromPreviousSection()` methode op de stroom`Section`voorwerp. Hiermee worden de kop- en voetteksten van de vorige sectie naar de huidige sectie gekopieerd.

#### Vraag: Is het mogelijk om alleen de kop- of voettekst uit de vorige sectie in Aspose.Words te kopiëren?

 A: Ja, het is mogelijk om alleen de kop- of voettekst uit de vorige sectie in Aspose.Words te kopiëren. Hiervoor kunt u gebruik maken van de`CopyHeaderFromPreviousSection()` En`CopyFooterFromPreviousSection()` methoden op de huidige`Section` object om specifiek de kop- of voettekst van de vorige sectie naar de huidige sectie te kopiëren.

#### Vraag: Vervangt het kopiëren van kop- en voetteksten uit de vorige sectie de bestaande kop- en voetteksten in de huidige sectie?

A: Ja, het kopiëren van kop- en voetteksten uit de vorige sectie vervangt de bestaande kop- en voetteksten in de huidige sectie. Als u de bestaande kop- en voetteksten wilt behouden en deze wilt toevoegen aan de gekopieerde kop- en voetteksten, moet u een extra bewerking uitvoeren om de inhoud samen te voegen.

#### Vraag: Hoe kan ik controleren of een sectie een kop- of voettekst heeft uit de vorige sectie in Aspose.Words?

A: Om te controleren of een sectie een kop- of voettekst heeft uit de vorige sectie in Aspose.Words, kunt u de`HasHeader` En`HasFooter` eigendommen op`Section` object om te bepalen of de koptekst of voettekst aanwezig is. Als`HasHeader` of`HasFooter` geeft terug`false`betekent dit dat er geen kop- of voettekst uit de vorige sectie in deze sectie aanwezig is.