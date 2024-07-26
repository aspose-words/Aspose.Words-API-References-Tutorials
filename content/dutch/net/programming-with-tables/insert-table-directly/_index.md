---
title: Tabel rechtstreeks invoegen
linktitle: Tabel rechtstreeks invoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tabellen rechtstreeks in Word-documenten kunt invoegen met Aspose.Words voor .NET. Volg onze gedetailleerde, stapsgewijze handleiding om uw documentcreatie te stroomlijnen.
type: docs
weight: 10
url: /nl/net/programming-with-tables/insert-table-directly/
---
## Invoering
Programmatisch tabellen maken kan een behoorlijke uitdaging zijn, vooral als het om complexe documentstructuren gaat. Maar maak je geen zorgen, we zijn hier om het voor je uit te leggen! In deze handleiding doorlopen we de stappen voor het rechtstreeks invoegen van een tabel in een Word-document met behulp van Aspose.Words voor .NET. Of je nu een doorgewinterde ontwikkelaar bent of net begint, deze tutorial helpt je het proces gemakkelijk onder de knie te krijgen.

## Vereisten

Voordat we in de code duiken, zorgen we ervoor dat u alles heeft wat u nodig heeft om aan de slag te gaan. Hier is een korte checklist:

1.  Aspose.Words voor .NET-bibliotheek: Zorg ervoor dat u de Aspose.Words voor .NET-bibliotheek hebt gedownload en geïnstalleerd. U kunt deze verkrijgen bij de[downloadpagina](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Een ontwikkelomgeving zoals Visual Studio.
3. Basiskennis van C#: Inzicht in de basisprincipes van C#-programmeren.
4. Documentmap: een mappad waar u uw documenten opslaat.

Als u aan deze vereisten voldoet, bent u klaar om te beginnen met coderen!

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren. Deze naamruimten bieden ons de klassen en methoden die nodig zijn om met Word-documenten te werken.

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Tables;
```

Nu we onze naamruimten hebben ingesteld, gaan we verder met het spannende gedeelte: tabellen rechtstreeks in een Word-document maken en invoegen.

## Stap 1: Het document instellen

Laten we beginnen met het opzetten van een nieuw Word-document. Dit is waar onze tabel zal worden ingevoegd.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

 Deze code initialiseert een nieuw Word-document. Je zult moeten vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentmap.

## Stap 2: Het tabelobject maken

Vervolgens maken we het tabelobject. Hier definiëren we de structuur van onze tabel.

```csharp
// We beginnen met het maken van het tabelobject. Merk op dat we het documentobject moeten doorgeven
// naar de constructor van elk knooppunt. Dit komt omdat elk knooppunt dat we creëren erbij moet horen
// naar een of ander document.
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Hier maken we een nieuwe tabel en voegen deze toe aan de hoofdtekst van het eerste gedeelte van ons document.

## Stap 3: Rijen en cellen toevoegen

Een tabel bestaat uit rijen en cellen. Laten we deze elementen stap voor stap toevoegen.

### Een rij toevoegen

```csharp
// Hier kunnen we VerzekerMinimum bellen om de rijen en cellen voor ons te maken. Deze methode wordt gebruikt
// om ervoor te zorgen dat het opgegeven knooppunt geldig is. In dit geval moet een geldige tabel minimaal één rij en één cel bevatten.
// In plaats daarvan zullen we zelf de rij en tabel maken.
// Dit zou de beste manier zijn om dit te doen als we een tabel binnen een algoritme zouden maken.
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);
```

Deze code maakt een nieuwe rij en voegt deze toe aan onze tabel.

### Cellen aan de rij toevoegen

Laten we nu enkele cellen aan onze rij toevoegen. 

```csharp
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
row.AppendChild(cell);
```

In dit fragment maken we een cel, stellen we de achtergrondkleur in op lichtblauw en definiëren we de breedte ervan. Vervolgens voegen we een alinea en een run toe aan de cel om onze tekst vast te houden.

## Stap 4: Cellen klonen

Om het proces van het toevoegen van cellen te versnellen, kunnen we bestaande cellen klonen.

```csharp
// Vervolgens herhaalden we het proces voor de andere cellen en rijen in de tabel.
// We kunnen de zaken ook versnellen door bestaande cellen en rijen te klonen.
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
```

Deze code kloont de bestaande cel en voegt deze toe aan de rij. Vervolgens voegen we een alinea en een run toe aan de nieuwe cel.

## Stap 5: Auto Fit-instellingen toepassen

Laten we tot slot de instellingen voor automatisch aanpassen op onze tabel toepassen om ervoor te zorgen dat de kolommen een vaste breedte hebben.

```csharp
// We kunnen nu alle instellingen voor automatisch aanpassen toepassen.
table.AutoFit(AutoFitBehavior.FixedColumnWidths);
```

## Stap 6: Het document opslaan

Nu onze tafel volledig is opgesteld, is het tijd om het document op te slaan.

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Met deze code wordt het document opgeslagen waarin de tabel is ingevoegd.

## Conclusie

Gefeliciteerd! U hebt met succes een tabel rechtstreeks in een Word-document ingevoegd met behulp van Aspose.Words voor .NET. Dit proces kan worden gebruikt om programmatisch complexe tabellen te maken, waardoor uw documentautomatiseringstaken veel eenvoudiger worden. Of u nu rapporten, facturen of een ander documenttype genereert, het is een cruciale vaardigheid om te begrijpen hoe u tabellen moet manipuleren.

## Veelgestelde vragen

### Hoe kan ik Aspose.Words voor .NET downloaden?
 U kunt Aspose.Words voor .NET downloaden van de[downloadpagina](https://releases.aspose.com/words/net/).

### Kan ik Aspose.Words voor .NET uitproberen voordat ik het aanschaf?
 Ja, u kunt een aanvraag indienen[gratis proefperiode](https://releases.aspose.com/) om de bibliotheek te evalueren voordat u deze aanschaft.

### Hoe koop ik Aspose.Words voor .NET?
 U kunt Aspose.Words voor .NET kopen bij de[aankooppagina](https://purchase.aspose.com/buy).

### Waar kan ik de documentatie voor Aspose.Words voor .NET vinden?
 De documentatie is beschikbaar[hier](https://reference.aspose.com/words/net/).

### Wat moet ik doen als ik ondersteuning nodig heb bij het gebruik van Aspose.Words voor .NET?
 Voor ondersteuning kunt u terecht op de[Aspose.Words-forum](https://forum.aspose.com/c/words/8).