---
title: Stel lettertypemappen, systeem en aangepaste map in
linktitle: Stel lettertypemappen, systeem en aangepaste map in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u systeemmappen en aangepaste lettertypemappen in Word-documenten instelt met behulp van Aspose.Words voor .NET, zodat uw documenten correct worden weergegeven in verschillende omgevingen.
type: docs
weight: 10
url: /nl/net/working-with-fonts/set-fonts-folders-system-and-custom-folder/
---
## Invoering

Stel je voor dat je een document aan het maken bent met een unieke lettertypestijl, maar er vervolgens achter komt dat de lettertypen niet correct worden weergegeven op een andere machine. Frustrerend, toch? Dit is waar het configureren van lettertypemappen een rol speelt. Met Aspose.Words voor .NET kunt u systeemmappen en aangepaste lettertypemappen definiëren om ervoor te zorgen dat uw documenten er altijd uitzien zoals bedoeld. Laten we eens kijken hoe u dit kunt bereiken.

## Vereisten

Voordat we beginnen, zorg ervoor dat je het volgende hebt:

-  Aspose.Words voor .NET Library: Download het als je dat nog niet hebt gedaan[hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: een IDE zoals Visual Studio.
- Basiskennis van C#: Bekendheid met C# zal u helpen de codevoorbeelden te volgen.

## Naamruimten importeren

Importeer eerst de benodigde naamruimten in uw project:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

Laten we het proces nu in eenvoudige stappen opsplitsen.

## Stap 1: Laad het document

 Laad om te beginnen uw Word-document in een Aspose.Words`Document` voorwerp. Dit document is het document waarin u de lettertypemappen wilt instellen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 2: Initialiseer lettertype-instellingen

 Maak een nieuw exemplaar van`FontSettings`. Met dit object kunt u lettertypebronnen beheren.

```csharp
FontSettings fontSettings = new FontSettings();
```

## Stap 3: Systeemlettertypebronnen ophalen

Haal de standaard systeemlettertypebronnen op. Op een Windows-computer omvat dit doorgaans de map "Windows\Fonts\" map.

```csharp
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

## Stap 4: Voeg een aangepaste lettertypemap toe

Voeg een aangepaste map toe die uw extra lettertypen bevat. Dit is handig als bepaalde lettertypen niet in de systeemlettertypenmap zijn geïnstalleerd.

```csharp
FolderFontSource folderFontSource = new FolderFontSource("C:\\MyFonts\\", true);
fontSources.Add(folderFontSource);
```

## Stap 5: Lettertypebronnen bijwerken

 Converteer de lijst met lettertypebronnen terug naar een array en stel deze in op de`FontSettings` voorwerp.

```csharp
FontSourceBase[] updatedFontSources = fontSources.ToArray();
fontSettings.SetFontsSources(updatedFontSources);
```

## Stap 6: Pas lettertype-instellingen toe op document

 Pas ten slotte het geconfigureerde`FontSettings` naar uw document en sla het op in het gewenste formaat, zoals PDF.

```csharp
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersSystemAndCustomFolder.pdf");
```

## Conclusie

En daar heb je het! Door deze stappen te volgen, kunt u ervoor zorgen dat uw Word-documenten de juiste lettertypen gebruiken, of het nu systeemlettertypen zijn of aangepaste lettertypen die in een specifieke map zijn opgeslagen. Deze opstelling helpt de integriteit van het uiterlijk van uw document in verschillende omgevingen te behouden.

## Veelgestelde vragen

### Wat gebeurt er als een lettertype ontbreekt in zowel systeemmappen als aangepaste mappen?

Aspose.Words gebruikt een standaardlettertype om het ontbrekende lettertype te vervangen, zodat het document leesbaar blijft.

### Kan ik meerdere aangepaste lettertypemappen toevoegen?

 Ja, u kunt meerdere aangepaste lettertypemappen toevoegen door het maakproces te herhalen`FolderFontSource` objecten en deze toe te voegen aan de lijst met lettertypebronnen.

### Is het mogelijk om netwerkpaden te gebruiken voor aangepaste lettertypemappen?

 Ja, u kunt een netwerkpad opgeven in het`FolderFontSource` bouwer.

### Welke bestandsformaten ondersteunt Aspose.Words voor het opslaan van documenten?

Aspose.Words ondersteunt verschillende formaten, waaronder DOCX, PDF, HTML en meer.

### Hoe ga ik om met meldingen over lettertypevervanging?

 U kunt meldingen over lettertypevervanging afhandelen met behulp van de`FontSettings` klasse`FontSubstitutionWarning`evenement.