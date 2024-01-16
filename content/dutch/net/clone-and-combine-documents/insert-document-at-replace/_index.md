---
title: Document invoegen bij vervangen
linktitle: Document invoegen bij vervangen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een document bij vervanging invoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/clone-and-combine-documents/insert-document-at-replace/
---
In deze zelfstudie laten we u zien hoe u een document in een ander document kunt invoegen wanneer u het vervangt met behulp van de functie Document invoegen bij vervangen van Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en het document in te voegen.

## Stap 1: Het hoofddocument laden

Om te beginnen geeft u de directory voor uw documenten op en laadt u het hoofddocument in een Document-object. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## Stap 2: Configureer zoek- en vervangopties

Nu gaan we de zoek- en vervangopties configureren door de zoekrichting en de vervang-callback op te geven om een document in een ander document in te voegen. Hier is hoe:

```csharp
// Configureer zoek- en vervangopties.
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## Stap 3: De vervangingsmethode oproepen

We zullen nu de vervangingsmethode aanroepen om de opgegeven tekst te vinden en te vervangen door een lege tekenreeks, met behulp van de geconfigureerde opties. Hier is hoe:

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### Voorbeeldbroncode voor Document invoegen bij vervangen met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Document invoegen bij het vervangen van Aspose.Words voor .NET:

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

// Opties voor zoeken en vervangen instellen.
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

// Roep de vervangingsmethode aan.
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u tijdens het vervangen een document in een ander document kunt invoegen met behulp van de functie Document invoegen bij vervangen van Aspose.Words voor .NET. Door de opties voor zoeken en vervangen te configureren en de benodigde gegevens aan te leveren, kunt u documenten dynamisch samenstellen door specifieke tijdelijke aanduidingen te vervangen door de inhoud van andere documentsjablonen of secties. Aspose.Words voor .NET biedt een krachtige en flexibele manier om complexe documentmanipulatietaken te beheren, waardoor het een waardevol hulpmiddel is voor het automatiseren van scenario's voor het maken van documenten en het invoegen van inhoud.

### Veelgestelde vragen

#### Vraag: Wat is het doel van het invoegen van een document in een ander document tijdens het vervangen?

A: Door tijdens het vervangen een document in een ander document in te voegen, kunt u een specifieke tijdelijke aanduiding dynamisch vervangen door de inhoud van een afzonderlijk document. Deze functie is vooral handig als u een groter document wilt samenstellen door verschillende vooraf gedefinieerde documentsjablonen of secties te combineren in specifieke tijdelijke aanduidingen.

#### Vraag: Hoe voeg ik een document in een ander document in tijdens het vervangen met Aspose.Words voor .NET?

A: Volg deze stappen om een document in een ander document in te voegen tijdens het vervangen met Aspose.Words voor .NET:
1. Laad het hoofddocument dat de tijdelijke aanduidingen bevat in een Document-object.
2. Configureer de zoek- en vervangopties, inclusief de zoekrichting en vervang callback om het invoegen van documenten af te handelen.
3. Roep de vervangingsmethode aan met het juiste zoekpatroon, waarbij u de tijdelijke aanduidingen vervangt door een lege tekenreeks, met behulp van de geconfigureerde opties.

#### Vraag: Kan ik het invoeggedrag tijdens het vervangen aanpassen?

A: Ja, u kunt het invoeggedrag tijdens het vervangen aanpassen door een aangepaste ReplacingCallback te implementeren. Door over te nemen van de IReplacingCallback-interface kunt u bepalen hoe de documenten worden ingevoegd en samengevoegd op basis van uw specifieke vereisten bij het vervangen van de tijdelijke aanduidingen.

#### Vraag: Kan ik meerdere tijdelijke aanduidingen vervangen door verschillende documenten?

A: Ja, u kunt meerdere tijdelijke aanduidingen vervangen door verschillende documenten door de juiste zoekpatronen voor elke tijdelijke aanduiding op te geven en de bijbehorende documenten op te geven die moeten worden ingevoegd.