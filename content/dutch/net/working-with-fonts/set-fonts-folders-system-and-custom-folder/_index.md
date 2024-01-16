---
title: Stel lettertypemappen, systeem en aangepaste map in
linktitle: Stel lettertypemappen, systeem en aangepaste map in
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van systeemmappen en aangepaste lettertypemappen bij het renderen van een document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---

In deze zelfstudie begeleiden we u stapsgewijs door het proces voor het instellen van systeemlettertypemappen en een aangepaste map bij het renderen van een document met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u meerdere lettertypemappen kunt opgeven, waaronder de systeemmap en een aangepaste map, die u kunt gebruiken bij het renderen van uw documenten met Aspose.Words voor .NET.

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

## Stap 3: Stel systeem- en aangepaste lettertypemappen in
 Nu kunt u systeemlettertypemappen en een aangepaste map instellen met behulp van de`FontSettings` klasse en de`SetFontsSources()` methode. Eerst moet u de lijst met omgevingsafhankelijke lettertypebronnen ophalen met behulp van`GetFontsSources()` en sla deze op in een lijst. Vervolgens kunt u een nieuw exemplaar van`FolderFontSource` waarbij u het pad opgeeft naar de aangepaste map die uw lettertypen bevat. Voeg deze instantie toe aan de lijst met bestaande lettertypebronnen. Gebruik ten slotte`SetFontsSources()` om de lettertypebronnen bij te werken met de nieuwe lijst.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Stap 4: Pas lettertype-instellingen toe
 Vervolgens moet u de lettertype-instellingen op uw document toepassen met behulp van de`FontSettings` eigendom van de`Document` klas.

```csharp
doc.FontSettings = fontSettings;
```

## Stap 5: Sla het gerenderde document op
Ten slotte kunt u het gerenderde document opslaan in een bestand met

   de ... gebruiken`Save()` werkwijze van de`Document` klas. Zorg ervoor dat u het juiste pad en de juiste bestandsnaam opgeeft.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

### Voorbeeldbroncode voor Set Fonts Folders System en Custom Folder met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Haal de reeks omgevingsafhankelijke lettertypebronnen op die standaard worden doorzocht.
// Dit bevat bijvoorbeeld een "Windows\Fonts\"-bron op Windows-machines.
// We voegen deze array toe aan een nieuwe lijst om het toevoegen of verwijderen van lettertype-items veel eenvoudiger te maken.
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Voeg een nieuwe mapbron toe die Aspose.Words de opdracht geeft om in de volgende map naar lettertypen te zoeken.
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
// Voeg de aangepaste map die onze lettertypen bevat toe aan de lijst met bestaande lettertypebronnen.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u systeemlettertypemappen en een aangepaste map kunt instellen bij het renderen van een document met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig meerdere lettertypemappen opgeven, waaronder de systeemmap en een aangepaste map, die u kunt gebruiken bij het renderen van uw documenten. Aspose.Words biedt een krachtige en flexibele API voor woordenverwerking met lettertypen in uw documenten. Met deze kennis kunt u de lettertypebronnen die worden gebruikt bij het renderen van uw documenten beheren en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Hoe kan ik systeemlettertypemappen instellen in Aspose.Words?

A: Om systeemlettertypemappen in Aspose.Words in te stellen, hoeft u niets te doen. Aspose.Words gebruikt automatisch systeemlettertypen die op uw besturingssysteem zijn geïnstalleerd.

#### Vraag: Hoe kan ik aangepaste lettertypemappen instellen in Aspose.Words?

 A: Om de aangepaste lettertypemappen in Aspose.Words in te stellen, kunt u de`SetFontsFolders` werkwijze van de`Fonts` klasse die de locaties van de aangepaste lettertypemappen specificeert.

#### Vraag: Kan ik meerdere aangepaste lettertypemappen opgeven in Aspose.Words?

 A: Ja, u kunt meerdere aangepaste lettertypemappen opgeven in Aspose.Words met behulp van de`SetFontsFolders` werkwijze van de`Fonts` klasse met een lijst met maplocaties.

#### Vraag: Hoe kan ik de lettertypemappen controleren die zijn gedefinieerd in Aspose.Words?

 Om de lettertypemappen te controleren die zijn gedefinieerd in Aspose.Words, kunt u de`GetFolders` werkwijze van de`Fonts` class om de lijst met geconfigureerde lettertypemappen op te halen.

#### Vraag: Hebben aangepaste maplettertypen voorrang op systeemlettertypen in Aspose.Words?

A: Ja, aangepaste maplettertypen hebben voorrang op systeemlettertypen in Aspose.Words. Als een lettertype aanwezig is in zowel aangepaste mappen als systeemlettertypen, gebruikt Aspose.Words de versie uit de aangepaste map.