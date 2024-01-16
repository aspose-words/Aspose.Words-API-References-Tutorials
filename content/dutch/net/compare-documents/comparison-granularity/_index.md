---
title: Vergelijking granulariteit in Word-document
linktitle: Vergelijking granulariteit in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer Vergelijken Granulariteit in de Word-documentfunctie van Aspose.Words voor .NET waarmee documenten karakter voor karakter kunnen worden vergeleken, waarbij de aangebrachte wijzigingen worden gerapporteerd.
type: docs
weight: 10
url: /nl/net/compare-documents/comparison-granularity/
---
Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van de functie Granulariteit vergelijken in Word-documenten van Aspose.Words voor .NET.

## Stap 1: Introductie

Met de functie Granulariteit vergelijken van Aspose.Words voor .NET kunt u documenten op tekenniveau vergelijken. Dit betekent dat elk karakter wordt vergeleken en dat wijzigingen dienovereenkomstig worden gerapporteerd.

## Stap 2: De omgeving instellen

Voordat u begint, moet u uw ontwikkelomgeving instellen om met Aspose.Words voor .NET te werken. Zorg ervoor dat de Aspose.Words-bibliotheek is geïnstalleerd en dat u over een geschikt C#-project beschikt waarin u de code kunt insluiten.

## Stap 3: Voeg de vereiste assemblages toe

Als u de functie Vergelijk granulariteit van Aspose.Words voor .NET wilt gebruiken, moet u de benodigde samenstellingen aan uw project toevoegen. Zorg ervoor dat u de juiste verwijzingen naar Aspose.Words in uw project hebt.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Stap 4: Documenten maken

In deze stap maken we twee documenten met behulp van de DocumentBuilder-klasse. Deze documenten zullen worden gebruikt voor de vergelijking.

```csharp
// Maak document A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Maak document B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Stap 5: Vergelijkingsopties configureren

In deze stap zullen we de vergelijkingsopties configureren om de granulariteit van de vergelijking te specificeren. Hier zullen we granulariteit op karakterniveau gebruiken.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Stap 6: Documentvergelijking

Laten we nu de documenten vergelijken met behulp van de Compare-methode van de Document-klasse. Wijzigingen worden opgeslagen in document A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

 De`Compare` methode vergelijkt document A met document B en slaat de wijzigingen in document A op. U kunt ter referentie de naam van de auteur en de vergelijkingsdatum opgeven.

## Conclusie

In dit artikel hebben we de functie Granulariteit vergelijken van Aspose.Words voor .NET onderzocht. Met deze functie kunt u documenten op tekenniveau vergelijken en wijzigingen rapporteren. Deze kennis kunt u gebruiken om gedetailleerde documentvergelijkingen in uw projecten uit te voeren.

### Voorbeeldbroncode voor granulariteit van vergelijking met Aspose.Words voor .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

## Conclusie

In deze zelfstudie hebben we de functie Comparison Granularity van Aspose.Words voor .NET onderzocht. Met deze functie kunt u het detailniveau opgeven bij het vergelijken van documenten. Door verschillende granulariteitsniveaus te kiezen, kunt u gedetailleerde vergelijkingen uitvoeren op teken-, woord- of blokniveau, afhankelijk van uw specifieke vereisten. Aspose.Words voor .NET biedt een flexibele en krachtige mogelijkheid om documenten te vergelijken, waardoor het gemakkelijk wordt om verschillen in documenten met verschillende niveaus van granulariteit te identificeren.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het gebruik van Comparison Granularity in Aspose.Words voor .NET?

A: Dankzij de granulariteit van vergelijkingen in Aspose.Words voor .NET kunt u het detailniveau opgeven bij het vergelijken van documenten. Met deze functie kunt u documenten op verschillende niveaus vergelijken, zoals tekenniveau, woordniveau of zelfs blokniveau. Elk granulariteitsniveau biedt een ander detailniveau in de vergelijkingsresultaten.

#### Vraag: Hoe gebruik ik Comparison Granularity in Aspose.Words voor .NET?

A: Volg deze stappen om de granulariteit van vergelijkingen in Aspose.Words voor .NET te gebruiken:
1. Richt uw ontwikkelomgeving in met de Aspose.Words-bibliotheek.
2. Voeg de benodigde samenstellingen toe aan uw project door te verwijzen naar Aspose.Words.
3.  Maak de documenten die u wilt vergelijken met behulp van de`DocumentBuilder` klas.
4.  Configureer de vergelijkingsopties door een`CompareOptions` object en het instellen van de`Granularity` woning op het gewenste niveau brengen (bijv.`Granularity.CharLevel` voor vergelijking op tekenniveau).
5.  Gebruik de`Compare` methode op het ene document, het andere document doorgeven en de`CompareOptions` object als parameters. Deze methode vergelijkt de documenten op basis van de opgegeven granulariteit en slaat de wijzigingen op in het eerste document.

#### Vraag: Wat zijn de beschikbare niveaus van vergelijkingsgranulariteit in Aspose.Words voor .NET?

A: Aspose.Words voor .NET biedt drie niveaus van vergelijkingsgranulariteit:
- `Granularity.CharLevel`: vergelijkt documenten op tekenniveau.
- `Granularity.WordLevel`: vergelijkt documenten op woordniveau.
- `Granularity.BlockLevel`: vergelijkt documenten op blokniveau.

#### Vraag: Hoe kan ik de vergelijkingsresultaten interpreteren met granulariteit op tekenniveau?

A: Met granulariteit op tekenniveau wordt elk teken in de vergeleken documenten geanalyseerd op verschillen. De vergelijkingsresultaten tonen veranderingen op individueel karakterniveau, inclusief toevoegingen, verwijderingen en wijzigingen.