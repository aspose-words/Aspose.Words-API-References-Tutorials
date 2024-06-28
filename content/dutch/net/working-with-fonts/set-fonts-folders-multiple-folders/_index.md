---
title: Lettertypenmappen instellen Meerdere mappen
linktitle: Lettertypenmappen instellen Meerdere mappen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van meerdere lettertypemappen bij het renderen van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/set-fonts-folders-multiple-folders/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om meerdere lettertypemappen in te stellen bij het renderen van een document met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u meerdere lettertypemappen kunt opgeven die u kunt gebruiken bij het renderen van uw documenten met Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar u uw bewerkte, gerenderde document wilt opslaan. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Laad het document dat u wilt renderen
 Vervolgens kunt u het document laden om te renderen met behulp van de`Document` klas. Zorg ervoor dat u het juiste documentpad opgeeft.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 3: Stel lettertypemappen in
 Nu kunt u meerdere lettertypemappen instellen met behulp van de`FontSettings` klasse en de`SetFontsFolders()` methode. U kunt de paden opgeven naar de lettertypemappen die u in een array wilt gebruiken. In dit voorbeeld hebben we twee lettertypemappen opgegeven: "C:\MyFonts\" en "D:\Misc\Fonts\".

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
```

## Stap 4: Pas lettertype-instellingen toe
 Vervolgens moet u de lettertype-instellingen op uw document toepassen met behulp van de`FontSettings` eigendom van de`Document` klas.

```csharp
doc.FontSettings = fontSettings;
```

## Stap 5: Sla het gerenderde document op
 Ten slotte kunt u het gerenderde document opslaan in een bestand met behulp van de`Save()` werkwijze van de`Document` klas. Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

### Voorbeeldbroncode voor Set Fonts Folders Multiple Folders met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Houd er rekening mee dat deze instelling alle standaardlettertypebronnen overschrijft die standaard worden doorzocht. Nu wordt alleen naar deze mappen gezocht
// lettertypen bij het renderen of insluiten van lettertypen. Als u een extra lettertypebron wilt toevoegen terwijl u de systeemlettertypebronnen behoudt, gebruikt u zowel FontSettings.GetFontSources als
// FontSettings.SetFontSources in plaats daarvan.
fontSettings.SetFontsFolders(new[] { @"C:\MyFonts\", @"D:\Misc\Fonts\" }, true);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersMultipleFolders.pdf");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u meerdere lettertypemappen kunt instellen bij het renderen van een document met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig meerdere lettertypemappen opgeven die u kunt gebruiken bij het renderen van uw documenten. Aspose.Words biedt een krachtige en flexibele API voor woordenverwerking met lettertypen in uw documenten. Met deze kennis kunt u de lettertypebronnen die worden gebruikt bij het renderen van uw documenten beheren en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Hoe kan ik meerdere lettertypemappen instellen in Aspose.Words?

 A: Om meerdere lettertypemappen in Aspose.Words in te stellen, kunt u de`SetFontsFolders` werkwijze van de`Fonts` klasse met een lijst met aangepaste lettertypemaplocaties.

#### Vraag: Heeft het instellen van meerdere lettertypemappen invloed op alle documenten die worden verwerkt met Aspose.Words?

A: Ja, het instellen van meerdere lettertypemappen heeft invloed op alle documenten die worden verwerkt met Aspose.Words. Nadat u de lettertypemappen hebt gedefinieerd, gebruikt Aspose.Words deze locaties om in alle documenten naar lettertypen te zoeken.

#### Vraag: Hoeveel lettertypemappen kan ik definiëren in Aspose.Words?

A: U kunt zoveel lettertypemappen definiëren als nodig in Aspose.Words. Er is geen specifieke limiet voor het aantal lettertypemappen dat u kunt definiëren.

#### Vraag: Hoe kan ik de lettertypemappen controleren die zijn gedefinieerd in Aspose.Words?

 A: Om de lettertypemappen te controleren die zijn gedefinieerd in Aspose.Words, kunt u de`GetFolders` werkwijze van de`Fonts` class om de locaties van de geconfigureerde lettertypemappen op te halen.

#### Vraag: Moeten lettertypemappen specifieke lettertypen bevatten?

A: Ja, lettertypemappen moeten de lettertypen bevatten die u in uw Word-documenten wilt gebruiken. Aspose.Words zoekt naar lettertypen in de opgegeven mappen bij het verwerken van documenten.