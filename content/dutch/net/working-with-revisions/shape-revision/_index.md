---
title: Vormrevisie
linktitle: Vormrevisie
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u vormrevisies in Word-documenten kunt verwerken met Aspose.Words voor .NET met deze uitgebreide handleiding. Beheer het bijhouden van wijzigingen, het invoegen van vormen en meer.
type: docs
weight: 10
url: /nl/net/working-with-revisions/shape-revision/
---
## Invoering

Het programmatisch bewerken van Word-documenten kan een hele klus zijn, vooral als het gaat om het omgaan met vormen. Of u nu rapporten maakt, sjablonen ontwerpt of eenvoudigweg het maken van documenten automatiseert, de mogelijkheid om vormrevisies bij te houden en te beheren is van cruciaal belang. Aspose.Words voor .NET biedt een krachtige API om dit proces naadloos en efficiënt te maken. In deze zelfstudie gaan we dieper in op de details van het herzien van vormen in Word-documenten, zodat u over de hulpmiddelen en kennis beschikt om uw documenten gemakkelijk te beheren.

## Vereisten

Voordat we in de code duiken, zorgen we ervoor dat je alles hebt wat je nodig hebt:

-  Aspose.Words voor .NET: Zorg ervoor dat de Aspose.Words-bibliotheek is geïnstalleerd. Dat kan[download het hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: U moet een ontwikkelomgeving hebben ingesteld, zoals Visual Studio.
- Basiskennis van C#: Bekendheid met de programmeertaal C# en basisconcepten van objectgeoriënteerd programmeren.
- Word-document: een Word-document om mee te werken, of u kunt er tijdens de tutorial een maken.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren. Deze geven ons toegang tot de klassen en methoden die nodig zijn voor het omgaan met Word-documenten en -vormen.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Stap 1: Uw documentenmap instellen

Voordat we met vormen gaan werken, moeten we het pad naar onze documentmap definiëren. Dit is waar we onze gewijzigde documenten opslaan.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Een nieuw document maken

Laten we een nieuw Word-document maken waarin we vormen invoegen en herzien.

```csharp
Document doc = new Document();
```

## Stap 3: Een inline-vorm invoegen

We beginnen met het invoegen van een inline-vorm in ons document zonder revisies bij te houden. Een inlinevorm is een vorm die met de tekst meevloeit.

```csharp
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Stap 4: Beginnen met het bijhouden van revisies

Om wijzigingen in ons document bij te houden, moeten we het bijhouden van revisies inschakelen. Dit is essentieel voor het identificeren van wijzigingen in vormen.

```csharp
doc.StartTrackRevisions("John Doe");
```

## Stap 5: Een andere vorm met revisies invoegen

Nu het bijhouden van revisies is ingeschakeld, gaan we een andere vorm invoegen. Deze keer worden eventuele wijzigingen bijgehouden.

```csharp
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## Stap 6: Vormen ophalen en wijzigen

We kunnen alle vormen in het document ophalen en indien nodig aanpassen. Hier halen we de vormen en verwijderen we de eerste.

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
shapes[0].Remove();
```

## Stap 7: Het document opslaan

Nadat we onze wijzigingen hebben aangebracht, moeten we het document opslaan. Dit zorgt ervoor dat alle revisies en wijzigingen worden opgeslagen.

```csharp
doc.Save(dataDir + "Revision shape.docx");
```

## Stap 8: Revisies van vormverplaatsingen verwerken

Wanneer een vorm wordt verplaatst, houdt Aspose.Words dit bij als een revisie. Dit betekent dat er twee exemplaren van de vorm zullen zijn: één op de oorspronkelijke locatie en één op de nieuwe locatie.

```csharp
doc = new Document(dataDir + "Revision shape.docx");
shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
```

## Conclusie

En daar heb je het! U hebt met succes geleerd hoe u vormrevisies in Word-documenten kunt verwerken met behulp van Aspose.Words voor .NET. Of u nu documentsjablonen beheert, rapporten automatiseert of eenvoudigweg wijzigingen bijhoudt, deze vaardigheden zijn van onschatbare waarde. Door deze stapsgewijze handleiding te volgen, heeft u niet alleen de basis onder de knie, maar heeft u ook inzicht gekregen in meer geavanceerde technieken voor documentverwerking.

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, wijzigen en converteren met behulp van C#.

### Kan ik wijzigingen in andere elementen in een Word-document bijhouden?
Ja, Aspose.Words voor .NET ondersteunt het bijhouden van wijzigingen in verschillende elementen, waaronder tekst, tabellen en meer.

### Hoe kan ik een gratis proefversie van Aspose.Words voor .NET krijgen?
 U kunt een gratis proefversie van Aspose.Words voor .NET krijgen[hier](https://releases.aspose.com/).

### Is het mogelijk om revisies programmatisch te accepteren of af te wijzen?
Ja, Aspose.Words voor .NET biedt methoden om revisies programmatisch te accepteren of af te wijzen.

### Kan ik Aspose.Words voor .NET gebruiken met andere .NET-talen dan C#?
Absoluut! Aspose.Words voor .NET kan worden gebruikt met elke .NET-taal, inclusief VB.NET en F#.