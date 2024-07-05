---
title: Kloon Vba-project vanuit een Word-document
linktitle: Kloon Vba-project vanuit een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: In deze zelfstudie leert u hoe u een VBA-project uit een Word-document kunt klonen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-vba-macros/clone-vba-project/
---

In deze zelfstudie gaan we u vertellen hoe u een VBA-project uit een Word-document met macro's kunt klonen met behulp van de Aspose.Words-bibliotheek voor .NET. Door een VBA-project te klonen, kunt u alle VBA-code van het ene brondocument naar het andere document kopiëren. We nemen u stap voor stap mee om u te helpen de code in uw .NET-project te begrijpen en te implementeren.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd
- Een Word-document met een VBA-project dat u wilt klonen

## Stap 1: Definieer de documentmap
 Eerst moet u het mappad instellen op de locatie van uw Word-document. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad.

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Brondocument laden
Vervolgens laden we het Word-brondocument, dat het VBA-project bevat dat we willen klonen.

```csharp
// Laad het brondocument
Document doc = new Document(dataDir + "VBA project.docm");
```

## Stap 3: Maak een nieuw document met het gekloonde VBA-project
We zullen een nieuw document maken met een leeg VBA-project en het VBA-project uit het brondocument klonen.

```csharp
// Maak een nieuw document met een leeg VBA-project
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };
```

## Stap 4: Sla het bestemmingsdocument op
Ten slotte slaan we het doeldocument samen met het gekloonde VBA-project op in een bestand.

```csharp
destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");
```

### Voorbeeldbroncode voor Clone Vba Project met Aspose.Words voor .NET 
```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
Document destDoc = new Document { VbaProject = doc.VbaProject.Clone() };

destDoc.Save(dataDir + "WorkingWithVba.CloneVbaProject.docm");

```

## Conclusie
In deze zelfstudie hebben we gezien hoe u een VBA-project uit een Word-document kunt klonen met macro's met behulp van Aspose.Words voor .NET. Door VBA-projecten te klonen kunt u alle VBA-code van het ene brondocument naar het andere document kopiëren. U kunt deze functie gerust gebruiken om uw macro's in verschillende documenten te ordenen en beheren.

### Veelgestelde vragen

#### Vraag: Wat is het dupliceren van een VBA-project?

A: Het dupliceren van een VBA-project bestaat uit het kopiëren van alle VBA-code van een Word-brondocument naar een ander document. Hierdoor kunt u VBA-code in verschillende contexten hergebruiken of delen met andere documenten.

#### Vraag: Wat zijn de vereisten voor het klonen van een VBA-project uit een Word-document?

A: Voordat u een VBA-project uit een Word-document kunt klonen, moet u over praktische kennis van de programmeertaal C# beschikken. U moet ook de Aspose.Words voor .NET-bibliotheek in uw project installeren. U hebt ook een Word-document nodig met daarin een VBA-project dat u wilt klonen.

#### Vraag: Hoe kan ik de documentmap in de code instellen?
 A: In de verstrekte code moet u vervangen`"YOUR DOCUMENTS DIRECTORY"` met het juiste pad naar de map waar uw Word-document met het VBA-project zich bevindt.

#### Vraag: Hoe kan ik het bestemmingsdocument opslaan met een gekloond VBA-project?

A: Om het doeldocument met het gekloonde VBA-project op te slaan, kunt u de`Save` werkwijze van de`Document` klasse door het gewenste bestemmingspad en de bestandsnaam op te geven.

#### Vraag: Kan ik Aspose.Words voor .NET gebruiken om andere aspecten van Word-documenten te manipuleren?

A: Ja, Aspose.Words voor .NET is een krachtige bibliotheek waarmee u verschillende aspecten van Word-documenten kunt manipuleren. U kunt gegevens uit Word-documenten maken, bewerken, converteren en extraheren, inclusief inhoud, opmaak, afbeeldingen, tabellen, grafieken en meer.