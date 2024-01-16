---
title: Stel de map Lettertypen in
linktitle: Stel de map Lettertypen in
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de lettertypemap in Aspose.Words voor .NET instelt en ervoor zorgt dat de lettertypen die in uw documenten worden gebruikt, beschikbaar zijn.
type: docs
weight: 10
url: /nl/net/working-with-fonts/set-fonts-folder/
---
In deze zelfstudie laten we u zien hoe u de lettertypemap in Aspose.Words voor .NET instelt. U leert hoe u de map kunt opgeven die de lettertypen bevat die in uw Word-document worden gebruikt.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd

## Stap 1: Definieer de documentmap
 Begin met het instellen van het mappad naar de locatie van uw Word-document. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Stel de lettertypemap in
 Maak een exemplaar van de`FontSettings` klasse en gebruik de`SetFontsFolder` methode om de map met de lettertypen op te geven. Vervangen`"Fonts"` met de naam van de daadwerkelijke lettertypemap.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
```

## Stap 3: Laad het document met lettertype-instellingen
 Gebruik de`LoadOptions` klasse om lettertype-instellingen op te geven in de`FontSettings` keuze. Gebruik dan de`Document` class om het document te laden met behulp van deze opties.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

### Voorbeeldbroncode voor Set Fonts Folder met Aspose.Words voor .NET 

```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(dataDir + "Fonts", false);
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusie
Gefeliciteerd! U weet nu hoe u de map met lettertypen in Aspose.Words voor .NET instelt. U kunt deze functie gebruiken om de beschikbaarheid van lettertypen die in uw document worden gebruikt te garanderen en om consistentie in de weergave van lettertypen te garanderen.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een aangepaste lettertypemap instellen in Aspose.Words?

 A: Om een map met aangepaste lettertypen in Aspose.Words in te stellen, kunt u de`FontsFolder` klasse en de`SetFontsFolders` methode die het pad specificeert naar de map die uw lettertypen bevat.

#### Vraag: Kan ik meerdere lettertypemappen instellen in Aspose.Words?

 A: Ja, u kunt meerdere lettertypemappen instellen in Aspose.Words door de`SetFontsFolders` method meerdere keren met de paden van de verschillende lettertypemappen die u wilt gebruiken.

#### Vraag: Wat gebeurt er als een lettertype dat in het document wordt gebruikt, niet aanwezig is in de gedefinieerde lettertypemappen?

A: Als een lettertype dat in het document wordt gebruikt niet aanwezig is in de lettertypemappen die zijn gedefinieerd in Aspose.Words, wordt in plaats daarvan een vervangend lettertype gebruikt. Dit zorgt ervoor dat de tekst in het document altijd correct wordt weergegeven, zelfs als het originele lettertype niet beschikbaar is.

#### Vraag: Hebben lettertypemappen die zijn gedefinieerd in Aspose.Words voorrang op lettertypen die op het systeem zijn geïnstalleerd?

A: Ja, lettertypemappen gedefinieerd in Aspose.Words hebben voorrang op lettertypen die op het systeem zijn geïnstalleerd. Dit betekent dat als er zowel in de gedefinieerde lettertypemappen als in de systeemlettertypen een lettertype met dezelfde naam aanwezig is, bij het verwerken van Word-documenten de versie in de lettertypemap wordt gebruikt.