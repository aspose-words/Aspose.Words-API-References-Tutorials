---
title: Meeteenheid
linktitle: Meeteenheid
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de functie voor maateenheden in Aspose.Words voor .NET configureert om de documentopmaak te behouden tijdens ODT-conversie.
type: docs
weight: 10
url: /nl/net/programming-with-odtsaveoptions/measure-unit/
---
## Invoering

Heeft u ooit uw Word-documenten naar verschillende formaten moeten converteren, maar had u een specifieke maateenheid nodig voor uw lay-out? Of u nu te maken heeft met inches, centimeters of punten, het is van cruciaal belang dat uw document tijdens het conversieproces zijn integriteit behoudt. In deze zelfstudie laten we zien hoe u de functie voor maateenheden in Aspose.Words voor .NET kunt configureren. Deze krachtige functie zorgt ervoor dat de opmaak van uw document precies zo blijft als u deze nodig heeft bij het converteren naar ODT-indeling (Open Document Text).

## Vereisten

Voordat je in de code duikt, zijn er een paar dingen die je nodig hebt om aan de slag te gaan:

1. Aspose.Words voor .NET: Zorg ervoor dat de nieuwste versie van Aspose.Words voor .NET is geïnstalleerd. Als u deze nog niet heeft, kunt u deze downloaden via[hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Een IDE zoals Visual Studio om uw C#-code te schrijven en uit te voeren.
3. Basiskennis van C#: Als u de basisprincipes van C# begrijpt, kunt u de tutorial volgen.
4. Een Word-document: Zorg ervoor dat u een voorbeeld van een Word-document bij de hand heeft dat u voor conversie kunt gebruiken.

## Naamruimten importeren

Voordat we beginnen met coderen, zorgen we ervoor dat de benodigde naamruimten zijn geïmporteerd. Voeg deze toe met behulp van richtlijnen bovenaan uw codebestand:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Stap 1: Stel uw documentenmap in

Eerst moet u het pad naar uw documentmap definiëren. Dit is waar uw Word-document zich bevindt en waar het geconverteerde bestand wordt opgeslagen.

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

 Vervangen`"YOUR DOCUMENTS DIRECTORY"` met het daadwerkelijke pad naar uw map. Dit zorgt ervoor dat uw code weet waar uw Word-document kan worden gevonden.

## Stap 2: Laad het Word-document

 Vervolgens moet u het Word-document laden dat u wilt converteren. Dit gebeurt met behulp van de`Document` klasse van Aspose.Words.

```csharp
// Laad het Word-document
Document doc = new Document(dataDir + "Document.docx");
```

Zorg ervoor dat uw Word-document, genaamd "Document.docx", aanwezig is in de opgegeven map.

## Stap 3: Configureer de meeteenheid

 Laten we nu de meeteenheid voor de ODT-conversie configureren. Dit is waar de magie gebeurt. Wij zetten de`OdtSaveOptions` om inches als meeteenheid te gebruiken.

```csharp
// Configuratie van back-upopties met de functie "Meeteenheid".
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

 In dit voorbeeld stellen we de maateenheid in op inches. U kunt ook andere eenheden kiezen, zoals`OdtSaveMeasureUnit.Centimeters` of`OdtSaveMeasureUnit.Points` afhankelijk van uw vereisten.

## Stap 4: Converteer het document naar ODT

 Ten slotte converteren we het Word-document naar het ODT-formaat met behulp van het geconfigureerde`OdtSaveOptions`.

```csharp
// Converteer het document naar ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

Deze coderegel slaat het geconverteerde document op in de opgegeven map met de nieuwe maateenheid toegepast.

## Conclusie

En daar heb je het! Door deze stappen te volgen, kunt u eenvoudig de functie voor maateenheden in Aspose.Words voor .NET configureren om ervoor te zorgen dat de lay-out van uw document tijdens de conversie behouden blijft. Of u nu met inches, centimeters of punten werkt, deze tutorial heeft u laten zien hoe u eenvoudig de controle over de opmaak van uw document kunt overnemen.

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek voor het programmatisch werken met Word-documenten. Hiermee kunnen ontwikkelaars Word-documenten maken, wijzigen, converteren en verwerken zonder dat Microsoft Word nodig is.

### Kan ik naast inches ook andere meeteenheden gebruiken?
 Ja, Aspose.Words voor .NET ondersteunt andere meeteenheden zoals centimeters en punten. U kunt de gewenste eenheid opgeven met behulp van de`OdtSaveMeasureUnit` opsomming.

### Is er een gratis proefversie beschikbaar voor Aspose.Words voor .NET?
 Ja, u kunt een gratis proefversie van Aspose.Words voor .NET downloaden van[hier](https://releases.aspose.com/).

### Waar kan ik documentatie vinden voor Aspose.Words voor .NET?
 U kunt toegang krijgen tot uitgebreide documentatie voor Aspose.Words voor .NET op[deze link](https://reference.aspose.com/words/net/).

### Hoe kan ik ondersteuning krijgen voor Aspose.Words voor .NET?
 Voor ondersteuning kunt u het Aspose.Words-forum bezoeken op[deze link](https://forum.aspose.com/c/words/8).
