---
title: Vergelijkingsdoel in Word-document
linktitle: Vergelijkingsdoel in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer de functie Doel vergelijken in Word-documenten van Aspose.Words voor .NET waarmee u documenten kunt vergelijken en een nieuw document kunt genereren met de aangebrachte wijzigingen.
type: docs
weight: 10
url: /nl/net/compare-documents/comparison-target/
---
Hier is een stapsgewijze handleiding om de onderstaande C#-broncode uit te leggen, die gebruikmaakt van het vergelijkingsdoel in de Word-documentfunctionaliteit van Aspose.Words voor .NET.

## Stap 1: Introductie

Met de doelvergelijkingsfunctie van Aspose.Words voor .NET kunt u twee documenten vergelijken en een nieuw document genereren met de wijzigingen die in het doeldocument zijn aangebracht. Dit kan handig zijn voor het bijhouden van wijzigingen tussen verschillende versies van een document.

## Stap 2: De omgeving instellen

Voordat u begint, moet u uw ontwikkelomgeving instellen om met Aspose.Words voor .NET te werken. Zorg ervoor dat de Aspose.Words-bibliotheek is geïnstalleerd en dat u over een geschikt C#-project beschikt waarin u de code kunt insluiten.

## Stap 3: Voeg de vereiste assemblages toe

Als u de vergelijkingsdoelfunctie van Aspose.Words voor .NET wilt gebruiken, moet u de benodigde samenstellingen aan uw project toevoegen. Zorg ervoor dat u de juiste verwijzingen naar Aspose.Words in uw project hebt.

```csharp
using Aspose.Words;
```

## Stap 4: Documentinitialisatie

In deze stap initialiseren we twee documenten ter vergelijking. U moet het mappad opgeven waar uw documenten zich bevinden, evenals de naam van het brondocument.

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Initialisatie van document A om te vergelijken.
Document docA = new Document(dataDir + "DocumentA.docx");

// Kloon document A om een identieke kopie van document B te maken.
Document docB = docA.Clone();
```

## Stap 5: Vergelijkingsopties configureren

In deze stap zullen we de vergelijkingsopties configureren om het gedrag van de vergelijking te specificeren. Opties omvatten de mogelijkheid om de opmaak te negeren, evenals het vergelijkingsdoel, de optie "Wijzigingen weergeven in" in het dialoogvenster "Documenten vergelijken" van Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Stap 6: Documentvergelijking

Nu gaan we de documenten vergelijken en het resultaat in een nieuw document genereren.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

 De`Compare`methode vergelijkt document A met document B en slaat de wijzigingen in document A op. U kunt ter referentie de gebruikersnaam en de vergelijkingsdatum opgeven.

### Voorbeeldbroncode voor Compare Target met Aspose.Words voor .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Heeft betrekking op de Microsoft Word-optie 'Wijzigingen weergeven in' in het dialoogvenster 'Documenten vergelijken'.
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Conclusie

In dit artikel hebben we de diff-doelfunctie van Aspose.Words voor .NET onderzocht. Met deze functie kunt u twee documenten vergelijken en een nieuw document genereren met de aangebrachte wijzigingen. U kunt deze kennis gebruiken om wijzigingen tussen verschillende versies van uw documenten bij te houden.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het gebruik van Comparison Target in Aspose.Words voor .NET?

A: Met Vergelijkingsdoel in Aspose.Words voor .NET kunt u twee documenten vergelijken en een nieuw document genereren met de wijzigingen die in het doeldocument zijn aangebracht. Deze functie is handig voor het bijhouden van wijzigingen tussen verschillende versies van een document en het visualiseren van de verschillen in een afzonderlijk document.

#### Vraag: Hoe gebruik ik Comparison Target in Aspose.Words voor .NET?

A: Volg deze stappen om Comparison Target in Aspose.Words voor .NET te gebruiken:
1. Richt uw ontwikkelomgeving in met de Aspose.Words-bibliotheek.
2. Voeg de benodigde samenstellingen toe aan uw project door te verwijzen naar Aspose.Words.
3.  Initialiseer de documenten die u wilt vergelijken met behulp van de`Document` klasse of de`DocumentBuilder` klas.
4.  Configureer de vergelijkingsopties door een`CompareOptions` object- en instellingseigenschappen zoals`IgnoreFormatting` En`Target` (bijv.`ComparisonTargetType.New` voor vergelijkingsdoel).
5.  Gebruik de`Compare` methode op het ene document, het andere document doorgeven en de`CompareOptions` object als parameters. Deze methode vergelijkt de documenten en slaat de wijzigingen in het eerste document op.

####  Vraag: Wat is het doel van de`Target` property in the `CompareOptions` class?

 EEN: De`Target` eigendom in de`CompareOptions` Met class kunt u het vergelijkingsdoel opgeven, dat vergelijkbaar is met de optie "Wijzigingen weergeven in" in het dialoogvenster "Documenten vergelijken" van Microsoft Word. Het doel kan worden ingesteld op`ComparisonTargetType.New` om wijzigingen in een nieuw document weer te geven,`ComparisonTargetType.Current` om wijzigingen in het huidige document weer te geven, of`ComparisonTargetType.Formatting` om alleen opmaakwijzigingen weer te geven.