---
title: Ontvang revisietypes van woorden
linktitle: Ontvang revisietypes van woorden
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u revisietypen van woorden in een Word-document kunt ophalen met Aspose.Words voor .NET. Met deze stapsgewijze handleiding kunt u documentrevisies efficiënt afhandelen.
type: docs
weight: 10
url: /nl/net/working-with-revisions/get-revision-types/
---
## Invoering

Ooit met uw knieën in een zee van documentrevisies terechtgekomen, waarbij u zich afvroeg wie wat wanneer verplaatste? Je bent niet de enige. Het afhandelen van documentrevisies kan een vervelende klus zijn, vooral als het om omvangrijke documenten gaat. Maar maak je geen zorgen! Met Aspose.Words voor .NET kunt u deze revisies eenvoudig identificeren en beheren. In deze handleiding begeleiden we u stapsgewijs door het proces hoe u revisietypen van woorden in een Word-document kunt krijgen met behulp van Aspose.Words voor .NET. Dus doe je gordel om en laten we erin duiken!

## Vereisten

Voordat we onze handen vuil maken met wat code, zijn er een paar dingen die je nodig hebt:

1.  Aspose.Words voor .NET Library: download het van als u dat nog niet heeft gedaan[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Visual Studio of een andere .NET-compatibele IDE.
3. Basiskennis van C#: Een goed begrip van de programmeertaal C# is nuttig.
4.  Een Word-document met revisies: zorg ervoor dat u een`.docx`bestand met bijgehouden wijzigingen om de code te testen.

## Naamruimten importeren

Om aan de slag te gaan, moet u de benodigde naamruimten in uw C#-project importeren. Hierdoor krijgt u toegang tot de functionaliteiten van Aspose.Words voor .NET.

```csharp
using Aspose.Words;
using Aspose.Words.Revision;
using System;
```

Laten we het voorbeeld opsplitsen in meerdere stappen voor een beter begrip en betere implementatie.

## Stap 1: Stel uw documentenmap in

Allereerst moet u het pad naar uw documentenmap definiëren. Dit is waar uw Word-document met revisies zich zal bevinden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw documentenmap.

## Stap 2: Laad uw Word-document

Vervolgens moet u het Word-document in uw project laden. Dit document moet de revisies bevatten die u wilt analyseren.

```csharp
Document doc = new Document(dataDir + "Revisions.docx");
```

 Zorg ervoor dat het bestand`Revisions.docx` bestaat in de opgegeven map.

## Stap 3: Open de paragraafverzameling

Nu uw document is geladen, moet u toegang krijgen tot de paragrafen in het eerste gedeelte van de hoofdtekst van het document. Dit zal u helpen elke paragraaf te herhalen om te controleren op herzieningen.

```csharp
ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
```

## Stap 4: Herhaal de alinea's en controleer op herzieningen

Hier gebeurt de magie. Je doorloopt elke paragraaf en controleert of deze is verplaatst (verwijderd of ingevoegd).

```csharp
for (int i = 0; i < paragraphs.Count; i++)
{
    if (paragraphs[i].IsMoveFromRevision)
        Console.WriteLine("Paragraph {0} has been moved (deleted).", i);
    if (paragraphs[i].IsMoveToRevision)
        Console.WriteLine("Paragraph {0} has been moved (inserted).", i);
}
```

 Deze lus doorloopt elke paragraaf en gebruikt de`IsMoveFromRevision`En`IsMoveToRevision` eigenschappen om te bepalen of de alinea is verplaatst (verwijderd) of verplaatst (ingevoegd).

## Conclusie

En daar heb je het! Met slechts een paar regels code kunt u eenvoudig de soorten revisies in uw Word-document identificeren met Aspose.Words voor .NET. Deze krachtige bibliotheek maakt het verwerken van documentrevisies een fluitje van een cent, zodat u zich kunt concentreren op belangrijkere taken. 

## Veelgestelde vragen

### Kan ik Aspose.Words voor .NET gebruiken om wijzigingen bij te houden die door specifieke gebruikers zijn aangebracht?

Ja, Aspose.Words voor .NET biedt functionaliteit voor toegang tot revisiegegevens, inclusief de auteur van de wijzigingen.

### Is er een gratis proefversie beschikbaar voor Aspose.Words voor .NET?

 Absoluut! U kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).

### Hoe kan ik een tijdelijke licentie aanvragen voor Aspose.Words voor .NET?

 Een tijdelijke licentie kunt u aanvragen en aanvragen via[hier](https://purchase.aspose.com/temporary-license/).

### Waar kan ik meer gedetailleerde documentatie vinden voor Aspose.Words voor .NET?

 Gedetailleerde documentatie is beschikbaar op de[Aspose-website](https://reference.aspose.com/words/net/).

### Kan ik Aspose.Words voor .NET gebruiken in een niet-commercieel project?

Ja, Aspose.Words voor .NET kan worden gebruikt in zowel commerciële als niet-commerciële projecten, maar zorg ervoor dat u de licentievoorwaarden controleert.