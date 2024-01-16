---
title: Krijg een lijst met beschikbare lettertypen
linktitle: Krijg een lijst met beschikbare lettertypen
second_title: Aspose.Words-API voor documentverwerking
description: In deze zelfstudie leert u hoe u de lijst met lettertypen kunt verkrijgen die beschikbaar zijn in Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/get-list-of-available-fonts/
---
In deze zelfstudie leggen we uit hoe u de lijst met lettertypen kunt verkrijgen die beschikbaar zijn in Aspose.Words voor .NET. In de lijst met beschikbare lettertypen weet u welke lettertypen u in uw documenten kunt gebruiken. We nemen u stap voor stap mee om u te helpen de code in uw .NET-project te begrijpen en te implementeren.

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

## Stap 2: Configureer lettertypebronnen
 Vervolgens maken we een exemplaar van`FontSettings` en haal de bestaande lettertypebronnen op met behulp van de`GetFontsSources()` methode. We zullen ook een nieuwe lettertypebron toevoegen door een map met lettertypen op te geven.

```csharp
// Configureer lettertypebronnen
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());

// Voeg een nieuwe lettertypebron toe
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
fontSources.Add(folderFontSource);

FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

## Stap 3: Haal de lijst met beschikbare lettertypen op
 Nu zullen we door de beschikbare lettertypen bladeren met behulp van de`GetAvailableFonts()` methode op de eerste bijgewerkte lettertypebron.

```csharp
// Verkrijg de lijst met beschikbare lettertypen
foreach(PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
Console.WriteLine("Font Family Name: " + fontInfo.FontFamilyName);
Console.WriteLine("Full font name: " + fontInfo.FullFontName);
Console.WriteLine("Version: " + fontInfo.Version);
Console.WriteLine("Path: " + fontInfo.FilePath);
}
```


### Voorbeeldbroncode voor Lijst met beschikbare lettertypen ophalen met Aspose.Words voor .NET 

```csharp

// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
// Voeg een nieuwe mapbron toe die Aspose.Words de opdracht geeft om in de volgende map naar lettertypen te zoeken.
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
// Voeg de aangepaste map die onze lettertypen bevat toe aan de lijst met bestaande lettertypebronnen.
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
	Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
	Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
	Console.WriteLine("Version  : " + fontInfo.Version);
	Console.WriteLine("FilePath : " + fontInfo.FilePath);
}

```

## Conclusie
In deze zelfstudie hebben we gezien hoe u de lijst met lettertypen kunt verkrijgen die beschikbaar zijn in Aspose.Words voor .NET. Zo weet u welke lettertypen u in uw documenten kunt gebruiken. U kunt deze functie gerust gebruiken om de juiste lettertypen voor uw behoeften te kiezen.

### Veelgestelde vragen

#### Vraag: Hoe kan ik de lijst met lettertypen ophalen die beschikbaar zijn in Aspose.Words?

 A: Om de lijst met lettertypen op te halen die beschikbaar zijn in Aspose.Words, kunt u de`FontsProvider` klasse en de`GetAvailableFonts` methode. Deze methode retourneert een lijst met alle lettertypen die op uw systeem zijn geïnstalleerd.

#### Vraag: Kan ik de lijst met beschikbare lettertypen filteren op bepaalde criteria in Aspose.Words?

A: Ja, u kunt de lijst met lettertypen die beschikbaar zijn in Aspose.Words filteren met behulp van specifieke criteria. U kunt lettertypen bijvoorbeeld filteren op familie, stijl of taal.

#### Vraag: Hoe kan ik de lijst met beschikbare lettertypen in mijn Word-documenten gebruiken?

 A: Om de lijst met lettertypen te gebruiken die beschikbaar zijn in uw Word-documenten, kunt u door de lijst bladeren en de juiste lettertypen selecteren met behulp van de methoden en eigenschappen van de`FontSettings` klasse in Aspose.Words.