---
title: Wijzig Vba-macro's van een Word-document
linktitle: Wijzig Vba-macro's van een Word-document
second_title: Aspose.Words-API voor documentverwerking
description: In deze zelfstudie leert u hoe u VBA-macro's van een Word-document bewerkt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-vba-macros/modify-vba-macros/
---
In deze zelfstudie leggen we uit hoe u VBA-macro's van een Word-document kunt wijzigen met behulp van de Aspose.Words-bibliotheek voor .NET. Door VBA-macro's te bewerken, kunt u bestaande VBA-code in uw Word-document bijwerken. We nemen u stap voor stap mee om u te helpen de code in uw .NET-project te begrijpen en te implementeren.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd
- Een Word-document met VBA-macro's die u wilt wijzigen

## Stap 1: Definieer de documentmap
 Eerst moet u het mappad instellen op de locatie van uw Word-document. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad.

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het document met de VBA-macro's
Vervolgens laden we het Word-document met de VBA-macro's die we willen wijzigen.

```csharp
// Laad het document met de VBA-macro's
Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
```

## Stap 3: Wijzig de macrobroncode
We gaan nu de broncode van de eerste macro van het VBA-project aanpassen. Vervang de`newSourceCode` variabele met de nieuwe broncode die u wilt gebruiken.

```csharp
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
```

## Stap 4: Sla het gewijzigde document op
Ten slotte slaan we het gewijzigde document met de bijgewerkte VBA-macro's op in een bestand.

```csharp
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");
```

### Voorbeeldbroncode voor het wijzigen van Vba-macro's met Aspose.Words voor .NET
 
```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "VBA project.docm");
VbaProject project = doc.VbaProject;
const string newSourceCode = "Test change source code";
project.Modules[0].SourceCode = newSourceCode;
doc.Save(dataDir + "WorkingWithVba.ModifyVbaMacros.docm");

```

## Conclusie
In deze zelfstudie hebben we gezien hoe u VBA-macro's in een Word-document kunt bewerken met Aspose.Words voor .NET. Door VBA-macro's te bewerken, kunt u bestaande VBA-code in uw document bijwerken om wijzigingen of verbeteringen aan te brengen. U kunt deze functie gerust gebruiken om uw Word-documenten verder aan te passen en te automatiseren.

### Veelgestelde vragen

#### Vraag: Wat is een VBA-macro in een Word-document?

A: Een VBA-macro in een Word-document is een stukje code dat kan worden uitgevoerd om specifieke acties in het document uit te voeren. Met VBA-macro's kunt u taken automatiseren, aangepaste functionaliteit toevoegen en communiceren met documentinhoud.

#### Vraag: Wat zijn de vereisten voor het bewerken van VBA-macro's in een Word-document?

A: Voordat u VBA-macro's in een Word-document kunt bewerken, moet u praktische kennis hebben van de programmeertaal C#. U moet ook de Aspose.Words voor .NET-bibliotheek in uw project installeren. U hebt ook een Word-document nodig met de VBA-macro's die u wilt wijzigen.

#### Vraag: Hoe kan ik de documentmap in de code instellen?

 A: In de verstrekte code moet u vervangen`"YOUR DOCUMENTS DIRECTORY"` met het juiste pad naar de map waar uw Word-document met de VBA-macro's zich bevindt.

#### Vraag: Hoe specificeer ik de nieuwe broncode van de macro die moet worden gewijzigd?

 A: Om de nieuwe broncode op te geven van de macro die u wilt wijzigen, kunt u de`SourceCode` eigendom van de corresponderende`VbaModule` object door er een tekenreeks aan toe te wijzen die de nieuwe VBA-code bevat.

#### Vraag: Kan ik meerdere VBA-macro's tegelijk in een Word-document bewerken?

 A: Ja, u kunt meerdere VBA-macro's in een Word-document wijzigen door een lus te gebruiken of rechtstreeks toegang te krijgen tot de overeenkomstige`VbaModule` voorwerpen in de`Modules` verzameling van de`VbaProject` voorwerp. Hierdoor kunt u meerdere VBA-macro's tegelijkertijd in één handeling bijwerken.