---
title: Kloon Vba-module vanuit een Word-document
linktitle: Kloon Vba-module vanuit een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: In deze zelfstudie leert u hoe u een VBA-module uit een Word-document kunt klonen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-vba-macros/clone-vba-module/
---

In deze zelfstudie gaan we u vertellen hoe u een VBA-module uit een Word-document met macro's kunt klonen met behulp van de Aspose.Words-bibliotheek voor .NET. Door een VBA-module te klonen kunt u VBA-code hergebruiken of kopiëren van het ene brondocument naar het andere document. We nemen u stap voor stap mee om u te helpen de code in uw .NET-project te begrijpen en te implementeren.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd
- Een Word-document met daarin een VBA-project met de module die u wilt klonen

## Stap 1: Definieer de documentmap
 Eerst moet u het mappad instellen op de locatie van uw Word-document. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad.

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Brondocument laden
Vervolgens laden we het Word-brondocument, dat het VBA-project bevat en de module die we willen klonen.

```csharp
// Laad het brondocument
Document doc = new Document(dataDir + "VBA project.docm");
```

## Stap 3: Maak een nieuw document met het VBA-project en kloon de module
We zullen een nieuw document maken met een leeg VBA-project en de opgegeven module uit het brondocument klonen.

```csharp
// Maak een nieuw document met een leeg VBA-project
Document destDoc = new Document { VbaProject = new VbaProject() };

// Kloon de module
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);
```

## Stap 4: Sla het bestemmingsdocument op
Ten slotte slaan we het doeldocument met de gekloonde VBA-module op in een bestand.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");
```

### Voorbeeldbroncode voor Clone Vba Module met Aspose.Words voor .NET 
```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = new VbaProject() };
VbaModule copyModule = doc.VbaProject.Modules["Module1"].Clone();
destDoc.VbaProject.Modules.Add(copyModule);

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaModule.docm");

```

## Conclusie
In deze zelfstudie hebben we gezien hoe u een VBA-module uit een Word-document kunt klonen met macro's met behulp van Aspose.Words voor .NET. Door VBA-modules te klonen kunt u VBA-code uit het ene brondocument eenvoudig hergebruiken in een ander document. U kunt deze functie gerust gebruiken om uw macro's in verschillende documenten te ordenen en beheren.

### Veelgestelde vragen

#### Vraag: Wat is het dupliceren van een VBA-module?

A: Het dupliceren van een VBA-module bestaat uit het kopiëren van een module met VBA-code van een Word-brondocument naar een ander document. Hierdoor kunt u VBA-code in verschillende contexten hergebruiken of delen met andere documenten.

#### Vraag: Wat zijn de vereisten voor het klonen van een VBA-module uit een Word-document?

A: Voordat u een VBA-module uit een Word-document kunt klonen, moet u praktische kennis hebben van de programmeertaal C#. U moet ook de Aspose.Words voor .NET-bibliotheek in uw project installeren. Ook hebt u een Word-document nodig met daarin een VBA-project met de module die u wilt klonen.

#### Vraag: Hoe kan ik de documentmap in de code instellen?

 A: In de verstrekte code moet u vervangen.`"YOUR DOCUMENTS DIRECTORY"` met het juiste pad naar de map waar uw Word-document met het VBA-project zich bevindt.

#### Vraag: Hoe kan ik een bestemmingsdocument opslaan met een gekloonde VBA-module?

 A: Om het doeldocument op te slaan met de gekloonde VBA-module, kunt u de`Save` werkwijze van de`Document` klasse door het gewenste bestemmingspad en de bestandsnaam op te geven.