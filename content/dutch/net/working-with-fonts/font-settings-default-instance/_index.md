---
title: Lettertype-instellingen Standaardinstantie
linktitle: Lettertype-instellingen Standaardinstantie
second_title: Aspose.Words-API voor documentverwerking
description: In deze zelfstudie leert u hoe u standaardlettertype-instellingen in een Word-document configureert met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/font-settings-default-instance/
---

In deze zelfstudie laten we u zien hoe u de standaardlettertype-instellingen in een Word-document configureert met behulp van de Aspose.Words-bibliotheek voor .NET. Met standaardlettertype-instellingen kunt u de lettertypebronnen opgeven die worden gebruikt bij het laden en weergeven van documenten. We nemen u stap voor stap mee om u te helpen de code in uw .NET-project te begrijpen en te implementeren.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd

## Stap 1: Definieer de documentmap
 Eerst moet u het mappad instellen op de locatie van uw Word-document. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad.

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Configureer de standaardlettertype-instellingen
 Vervolgens maken we een exemplaar van`FontSettings` gebruik makend van`FontSettings.DefaultInstance`, en vervolgens specificeren we de lettertypebronnen die worden gebruikt bij het laden en weergeven van documenten. In dit voorbeeld gebruiken we een systeemlettertypebron en een maplettertypebron.

```csharp
// Configureer standaardlettertype-instellingen
FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(),
new FolderFontSource("C:\\MyFonts\\", true)
});
```

## Stap 3: Upload een document met lettertype-instellingen
 Nu laden we het document met behulp van`LoadOptions` en het opgeven van de te gebruiken lettertype-instellingen.

```csharp
// Laad het document met de lettertype-instellingen
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);
```


### Voorbeeldbroncode voor lettertype-instellingen standaardinstantie met Aspose.Words voor .NET 
```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = FontSettings.DefaultInstance;
fontSettings.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(),
	new FolderFontSource("C:\\MyFonts\\", true)
});
LoadOptions loadOptions = new LoadOptions();
loadOptions.FontSettings = fontSettings;
Document doc = new Document(dataDir + "Rendering.docx", loadOptions);

```

## Conclusie
In deze zelfstudie hebben we gezien hoe u standaardlettertype-instellingen in een Word-document kunt configureren met Aspose.Words voor .NET. Door de lettertypebronnen op te geven die worden gebruikt bij het laden en weergeven van documenten, kunt u de weergave van lettertypen in uw documenten bepalen. U kunt deze functie gerust gebruiken om de lettertype-instellingen in uw projecten aan te passen.

### Veelgestelde vragen

#### Vraag: Hoe kan ik het standaardlettertype instellen in Aspose.Words?

 A: Om het standaardlettertype in Aspose.Words in te stellen, kunt u de`FontSettings` klasse en de`DefaultFontName` eigenschap die de naam van het gewenste lettertype specificeert.

#### Vraag: Kan ik de standaardlettergrootte opgeven in Aspose.Words?

 A: Ja, u kunt de standaardlettergrootte in Aspose.Words opgeven met behulp van de`DefaultFontSize` eigendom van de`FontSettings` klas. U kunt de gewenste puntgrootte instellen.

#### Vraag: Is het mogelijk om de standaardletterkleur in Aspose.Words in te stellen?

 A: Ja, u kunt de standaardletterkleur in Aspose.Words instellen met behulp van de`DefaultColor` eigendom van de`FontSettings` klas. U kunt de kleur opgeven met behulp van RGB-waarden of vooraf gedefinieerde namen.

#### Vraag: Zijn de standaardlettertype-instellingen van toepassing op alle documenten?

A: Ja, de standaardlettertype-instellingen zijn van toepassing op alle documenten die zijn gemaakt of bewerkt in Aspose.Words, tenzij er specifieke instellingen zijn ingesteld voor een afzonderlijk document.