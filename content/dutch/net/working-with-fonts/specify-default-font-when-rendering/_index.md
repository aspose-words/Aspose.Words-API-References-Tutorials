---
title: Geef het standaardlettertype op bij het renderen
linktitle: Geef het standaardlettertype op bij het renderen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het opgeven van het standaardlettertype bij het renderen van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/specify-default-font-when-rendering/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om het standaardlettertype op te geven bij het renderen van een document met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u een standaardlettertype kunt opgeven dat u wilt gebruiken bij het renderen van uw documenten met Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar u uw bewerkte, gerenderde document wilt opslaan. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het document dat u wilt renderen
 Vervolgens moet u het document laden om te renderen met behulp van de`Document` klas. Zorg ervoor dat u het juiste documentpad opgeeft.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 3: Stel het standaardlettertype in
 Nu kunt u het standaardlettertype opgeven dat u bij het renderen wilt gebruiken, door een exemplaar van het`FontSettings` klasse en het instellen van de`DefaultFontName` eigendom van de`DefaultFontSubstitution` bezwaar maken tegen de`DefaultFontSubstitution` voorwerp`SubstitutionSettings` van`FontSettings`.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
```

## Stap 4: Sla het gerenderde document op
 Ten slotte kunt u het gerenderde document opslaan in een bestand met behulp van de`Save()` werkwijze van de`Document` klas. Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

### Voorbeeldbroncode voor Specificeer standaardlettertype bij weergave met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Als het hier gedefinieerde standaardlettertype niet kan worden gevonden tijdens het renderen, dan
// In plaats daarvan wordt het dichtstbijzijnde lettertype op de machine gebruikt.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u het standaardlettertype kunt opgeven bij het renderen van een document met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig een standaardlettertype instellen dat u kunt gebruiken bij het renderen van uw documenten. Aspose.Words biedt een krachtige en flexibele API voor woordenverwerking met lettertypen in uw documenten. Met deze kennis kunt u de weergave van uw documenten controleren en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een standaardlettertype opgeven bij het converteren naar PDF in Aspose.Words?

 A: Om een standaardlettertype op te geven bij het converteren naar PDF in Aspose.Words, kunt u de`PdfOptions` klasse en stel de`DefaultFontName` eigenschap toe aan de naam van het gewenste lettertype.

#### Vraag: Wat moet ik doen als het standaardlettertype niet beschikbaar is bij het converteren naar PDF?

A: Als het opgegeven standaardlettertype niet beschikbaar is bij het converteren naar PDF, gebruikt Aspose.Words een vervangend lettertype om de tekst in het geconverteerde document weer te geven. Dit kan een klein verschil in uiterlijk veroorzaken met het originele lettertype.

#### Vraag: Kan ik een standaardlettertype opgeven voor andere uitvoerformaten, zoals DOCX of HTML?

A: Ja, u kunt een standaardlettertype opgeven voor andere uitvoerformaten, zoals DOCX of HTML, door de juiste conversieopties te gebruiken en de bijbehorende eigenschap voor elk formaat in te stellen.

#### Vraag: Hoe kan ik het standaardlettertype controleren dat is opgegeven in Aspose.Words?

 A: Om het standaardlettertype dat is opgegeven in Aspose.Words te controleren, kunt u de`DefaultFontName` eigendom van de`PdfOptions` class en haal de naam van het geconfigureerde lettertype op.

#### Vraag: Is het mogelijk om voor elke sectie van het document een ander standaardlettertype op te geven?

A: Ja, het is mogelijk om voor elke sectie van het document een ander standaardlettertype op te geven met behulp van opmaakopties die specifiek zijn voor elke sectie. Dit zou echter een meer geavanceerde manipulatie van het document vereisen met behulp van de Aspose.Words-functies.