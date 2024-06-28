---
title: Stel de standaardinstantie voor lettertypenmappen in
linktitle: Stel de standaardinstantie voor lettertypenmappen in
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van de standaardlettertypemap bij het renderen van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/set-fonts-folders-default-instance/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om de standaardlettertypemap in te stellen bij het renderen van een document met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u de standaardlettertypemap kunt instellen die u wilt gebruiken bij het renderen van uw documenten met Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar u uw bewerkte, gerenderde document wilt opslaan. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Stel de standaardlettertypemap in
 Vervolgens kunt u de standaardlettertypemap instellen met behulp van de`FontSettings.DefaultInstance` klasse en de`SetFontsFolder()`methode. Geef het pad op naar de map met lettertypen die u als standaardmap wilt gebruiken.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Stap 3: Laad het document dat u wilt renderen
 Nu kunt u het document laden om te renderen met behulp van de`Document` klas. Zorg ervoor dat u het juiste documentpad opgeeft.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 4: Sla het gerenderde document op
 Ten slotte kunt u het gerenderde document opslaan in een bestand met behulp van de`Save()` werkwijze van de`Document` klas. Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Voorbeeldbroncode voor Set Fonts Folders Default Instance met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de standaardlettertypemap kunt instellen bij het renderen van een document met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig opgeven welke map met lettertypen u als standaardmap wilt gebruiken bij het renderen van uw documenten. Aspose.Words biedt een krachtige en flexibele API voor woordenverwerking met lettertypen in uw documenten. Met deze kennis kunt u de lettertypebronnen die worden gebruikt bij het renderen van uw documenten beheren en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Hoe kan ik standaard lettertypemappen instellen in Aspose.Words?

 A: Om standaardlettertypemappen in Aspose.Words in te stellen, moet u de`Fonts` klasse en de`SetFontsFolders` methode om aangepaste lettertypemaplocaties op te geven.

#### Vraag: Heeft het instellen van standaardlettertypemappen invloed op alle Word-documenten die worden verwerkt met Aspose.Words?

A: Ja, het instellen van standaardlettertypemappen is van invloed op alle Word-documenten die worden verwerkt met Aspose.Words. Nadat u de standaardlettertypenmappen hebt ingesteld, gebruikt Aspose.Words deze locaties om naar lettertypen in alle documenten te zoeken.

#### Vraag: Kan ik meerdere standaardlettertypemappen instellen in Aspose.Words?

 A: Ja, u kunt meerdere standaardlettertypemappen instellen in Aspose.Words. U hoeft alleen maar de locaties van aangepaste lettertypemappen op te geven met behulp van de`SetFontsFolders` werkwijze van de`Fonts` klas.

#### Vraag: Hoe kan ik de standaardlettertypemappen controleren die momenteel zijn ingesteld in Aspose.Words?

 A: Om de standaardlettertypemappen te controleren die momenteel zijn gedefinieerd in Aspose.Words, kunt u de`GetFolders` werkwijze van de`Fonts` class om de locaties van de geconfigureerde lettertypemappen op te halen.

#### Vraag: Kan ik door het instellen van standaardlettertypemappen aangepaste lettertypen gebruiken in mijn Word-documenten?

A: Ja, door standaard lettertypemappen in te stellen, kunt u aangepaste lettertypen gebruiken in uw Word-documenten. U hoeft alleen maar de lettertypen in de opgegeven mappen te plaatsen en Aspose.Words zal ze gebruiken bij het genereren of manipuleren van de documenten.