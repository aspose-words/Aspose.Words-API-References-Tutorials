---
title: Stel lettertypemappen met prioriteit in
linktitle: Stel lettertypemappen met prioriteit in
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van lettertypemappen met prioriteit bij het renderen van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/set-fonts-folders-with-priority/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om lettertypemappen met prioriteit in te stellen bij het renderen van een document met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u meerdere lettertypemappen met aangepaste zoekprioriteit kunt opgeven bij het renderen van uw documenten met Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar u uw bewerkte, gerenderde document wilt opslaan. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Stel lettertypemappen met prioriteit in
 Vervolgens kunt u de lettertypemappen met prioriteit instellen met behulp van de`FontSettings` klasse en de`SetFontsSources()`methode. U kunt meerdere lettertypebronnen opgeven met behulp van exemplaren van`SystemFontSource`En`FolderFontSource`. In dit voorbeeld hebben we twee lettertypebronnen gedefinieerd: de standaard systeemlettertypebron en een aangepaste lettertypemap met prioriteit 1.

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## Stap 3: Laad het document dat u wilt renderen
 Nu kunt u het document laden om te renderen met behulp van de`Document` klas. Zorg ervoor dat u het juiste documentpad opgeeft.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 4: Sla het gerenderde document op
 Ten slotte kunt u het gerenderde document opslaan in een bestand met behulp van de`Save()` werkwijze van de`Document` klas. Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### Voorbeeldbroncode voor het instellen van lettertypemappen met prioriteit met behulp van Aspose.Words voor .NET 
```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u lettertypemappen met prioriteit kunt instellen bij het renderen van een document met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u bij het renderen van uw documenten eenvoudig meerdere lettertypemappen met aangepaste zoekprioriteit opgeven. Aspose.Words biedt een krachtige en flexibele API voor woordenverwerking met lettertypen in uw documenten. Met deze kennis kunt u de lettertypebronnen die worden gebruikt bij het renderen van uw documenten beheren en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Hoe kan ik lettertypemappen met prioriteit instellen in Aspose.Words?

 A: Om lettertypemappen met prioriteit in Aspose.Words in te stellen, kunt u de`SetFontsFoldersWithPriority` werkwijze van de`Fonts` klasse door de locaties van de lettertypemap en hun prioriteitsvolgorde op te geven.

#### Vraag: Wat gebeurt er als een lettertype in meerdere mappen met verschillende prioriteit aanwezig is?

A: Als een lettertype in meerdere mappen met verschillende prioriteit aanwezig is, gebruikt Aspose.Words bij het verwerken van documenten de versie uit de map met de hoogste prioriteit.

#### Vraag: Kan ik meerdere lettertypemappen met dezelfde prioriteit opgeven in Aspose.Words?

A: Ja, u kunt meerdere lettertypemappen met dezelfde prioriteit opgeven in Aspose.Words. Aspose.Words zal ze allemaal met gelijke prioriteit in overweging nemen bij het zoeken naar lettertypen in uw documenten.

#### Vraag: Hoe kan ik de lettertypemappen controleren die met prioriteit zijn gedefinieerd in Aspose.Words?

 A: Om de lettertypemappen te controleren die met prioriteit zijn gedefinieerd in Aspose.Words, kunt u de`GetFolders` werkwijze van de`Fonts` class om de lijst met geconfigureerde lettertypemappen op te halen, inclusief hun prioriteitsvolgorde.

#### Vraag: Wat is het nut van het instellen van lettertypemappen met prioriteit in Aspose.Words?

A: Door lettertypemappen met prioriteit in te stellen in Aspose.Words kunt u de zoekvolgorde van lettertypen in uw Word-documenten bepalen. Zo weet u zeker dat de gewenste lettertypen worden gebruikt en voorkomt u ongewenste problemen met het vervangen van lettertypen.