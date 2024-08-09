---
title: Krijg een lijst met beschikbare lettertypen
linktitle: Krijg een lijst met beschikbare lettertypen
second_title: Aspose.Words-API voor documentverwerking
description: Ontdek hoe u een lijst met beschikbare lettertypen kunt krijgen met Aspose.Words voor .NET in deze gedetailleerde stapsgewijze zelfstudie. Verbeter uw vaardigheden op het gebied van lettertypebeheer.
type: docs
weight: 10
url: /nl/net/working-with-fonts/get-list-of-available-fonts/
---
## Invoering

Heeft u ooit moeite gehad met het beheren van lettertypen in uw Word-documenten? Als u een .NET-ontwikkelaar bent, is Aspose.Words voor .NET hier om u te redden! Deze krachtige bibliotheek helpt u niet alleen programmatisch Word-documenten te maken en te manipuleren, maar biedt ook uitgebreide mogelijkheden voor lettertypebeheer. In deze handleiding leiden we u stapsgewijs door een zelfstudie over hoe u een lijst met beschikbare lettertypen kunt krijgen met Aspose.Words voor .NET. We zullen het opsplitsen in begrijpelijke stappen, zodat u het gemakkelijk kunt volgen. Dus laten we erin duiken en lettertypebeheer een fluitje van een cent maken!

## Vereisten

Voordat we beginnen, zijn er een paar dingen die je nodig hebt:

-  Aspose.Words voor .NET: Zorg ervoor dat de Aspose.Words voor .NET-bibliotheek is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/words/net/).
- Visual Studio: In dit voorbeeld wordt Visual Studio als ontwikkelomgeving gebruikt.
- .NET Framework: Zorg ervoor dat .NET Framework op uw computer is geïnstalleerd.
- Documentmap: een mappad waar uw documenten worden opgeslagen.

## Naamruimten importeren

Importeer eerst de benodigde naamruimten in uw project:

```csharp
using System;
using System.Collections.Generic;
using Aspose.Words;
using Aspose.Words.Fonts;
```

## Stap 1: Initialiseer lettertype-instellingen

De eerste stap is het initialiseren van de lettertype-instellingen. Hiermee kunt u de lettertypebronnen voor uw documenten beheren.

```csharp
FontSettings fontSettings = new FontSettings();
List<FontSourceBase> fontSources = new List<FontSourceBase>(fontSettings.GetFontsSources());
```

- FontSettings: Deze klasse wordt gebruikt om de instellingen voor lettertypevervanging en lettertypebronnen op te geven.
- fontSources: We maken een lijst met bestaande lettertypebronnen op basis van de huidige lettertype-instellingen.

## Stap 2: Definieer de documentmap

Geef vervolgens het pad naar uw documentmap op. Dit is waar Aspose.Words naar lettertypen zoekt.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

-  dataDir: Deze stringvariabele bevat het pad naar de map waar uw lettertypen zich bevinden. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad.

## Stap 3: Voeg een aangepaste lettertypemap toe

Voeg nu een nieuwe mapbron toe om Aspose.Words te instrueren om in deze map naar lettertypen te zoeken.

```csharp
FolderFontSource folderFontSource = new FolderFontSource(dataDir, true);
```

- FolderFontSource: deze klasse vertegenwoordigt een maplettertypebron. De tweede parameter (`true`) geeft aan of er recursief naar lettertypen in submappen moet worden gezocht.

## Stap 4: Update lettertypebronnen

Voeg de aangepaste lettertypemap toe aan de lijst met bestaande lettertypebronnen en werk de lettertype-instellingen bij.

```csharp
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
```

- fontSources.Add(folderFontSource): Voegt de aangepaste lettertypemap toe aan de bestaande lettertypebronnen.
- bijgewerktFontSources: Converteert de lijst met lettertypebronnen naar een array.

## Stap 5: Lettertypen ophalen en weergeven

Haal ten slotte de beschikbare lettertypen op en geef hun details weer.

```csharp
foreach (PhysicalFontInfo fontInfo in updatedFontSources[0].GetAvailableFonts())
{
    Console.WriteLine("FontFamilyName : " + fontInfo.FontFamilyName);
    Console.WriteLine("FullFontName  : " + fontInfo.FullFontName);
    Console.WriteLine("Version  : " + fontInfo.Version);
    Console.WriteLine("FilePath : " + fontInfo.FilePath);
}
```

- GetAvailableFonts(): Haalt de lijst met beschikbare lettertypen op uit de eerste lettertypebron in de bijgewerkte lijst.
-  fontInfo: een exemplaar van`PhysicalFontInfo` met details over elk lettertype.

## Conclusie

Gefeliciteerd! U hebt met succes een lijst met beschikbare lettertypen opgehaald met Aspose.Words voor .NET. In deze zelfstudie wordt u door elke stap geleid, van het initialiseren van de lettertype-instellingen tot het weergeven van lettertypedetails. Met deze kennis kunt u nu eenvoudig lettertypen in uw Word-documenten beheren. Vergeet niet dat Aspose.Words voor .NET een krachtig hulpmiddel is dat uw documentverwerkingsmogelijkheden aanzienlijk kan verbeteren. Ga dus aan de slag en ontdek meer functies om uw ontwikkelingsproces nog efficiënter te maken.

## Veelgestelde vragen

### Kan ik Aspose.Words voor .NET gebruiken met andere .NET-frameworks?
Ja, Aspose.Words voor .NET is compatibel met verschillende .NET-frameworks, waaronder .NET Core en .NET 5+.

### Hoe installeer ik Aspose.Words voor .NET?
U kunt het installeren via NuGet Package Manager in Visual Studio door te zoeken naar "Aspose.Words".

### Is het mogelijk om meerdere aangepaste lettertypemappen toe te voegen?
 Ja, u kunt meerdere aangepaste lettertypemappen toevoegen door er meerdere te maken`FolderFontSource` exemplaren en voeg ze toe aan de lijst met lettertypebronnen.

### Kan ik lettertypedetails ophalen uit een specifieke lettertypebron?
 Ja, u kunt lettertypedetails uit elke lettertypebron ophalen door de index van de lettertypebron op te geven in het`updatedFontSources` reeks.

### Ondersteunt Aspose.Words voor .NET lettertypevervanging?
Ja, het ondersteunt lettertypevervanging om ervoor te zorgen dat tekst correct wordt weergegeven, zelfs als het originele lettertype niet beschikbaar is.