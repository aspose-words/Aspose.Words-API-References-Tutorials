---
title: Hulpbronnen exporteren
linktitle: Hulpbronnen exporteren
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u bronnen zoals CSS en lettertypen kunt exporteren en tegelijkertijd Word-documenten als HTML kunt opslaan met Aspose.Words voor .NET. Volg onze stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/export-resources/
---
## Invoering

Hallo daar, mede-technologieliefhebber! Als u ooit Word-documenten naar HTML moet converteren, bent u hier aan het juiste adres. Vandaag duiken we in de wondere wereld van Aspose.Words voor .NET. Deze krachtige bibliotheek maakt het een fluitje van een cent om programmatisch met Word-documenten te werken. In deze zelfstudie doorlopen we de stappen voor het exporteren van bronnen, zoals lettertypen en CSS, bij het opslaan van een Word-document als HTML met Aspose.Words voor .NET. Maak je vast voor een leuke, informatieve rit!

## Vereisten

Voordat we in de code duiken, zorgen we ervoor dat u alles heeft wat u nodig heeft om aan de slag te gaan. Hier is een korte checklist:

1.  Visual Studio: Zorg ervoor dat Visual Studio op uw computer is geïnstalleerd. Je kunt het downloaden van de[Visual Studio-website](https://visualstudio.microsoft.com/).
2.  Aspose.Words voor .NET: Je hebt de Aspose.Words voor .NET-bibliotheek nodig. Als je het nog niet hebt, vraag dan een gratis proefperiode aan[Aspose-releases](https://releases.aspose.com/words/net/) of koop het bij de[Aspose-winkel](https://purchase.aspose.com/buy).
3. Basiskennis van C#: Een fundamenteel begrip van C# zal u helpen de codevoorbeelden te volgen.

Heb je dat allemaal? Geweldig! Laten we verder gaan met het importeren van de benodigde naamruimten.

## Naamruimten importeren

Om Aspose.Words voor .NET te gebruiken, moet u de relevante naamruimten in uw project opnemen. Zo doe je het:

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

Deze naamruimten zijn cruciaal voor toegang tot de Aspose.Words-klassen en -methoden die we in onze tutorial zullen gebruiken.

Laten we het proces van het exporteren van bronnen bij het opslaan van een Word-document als HTML uitsplitsen. We doen het stap voor stap, zodat het gemakkelijk te volgen is.

## Stap 1: Stel uw documentenmap in

Allereerst moet u het pad naar uw documentenmap opgeven. Dit is waar uw Word-document zich bevindt en waar het HTML-bestand wordt opgeslagen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad naar uw directory.

## Stap 2: Laad het Word-document

 Laten we vervolgens het Word-document laden dat u naar HTML wilt converteren. Voor deze zelfstudie gebruiken we een document met de naam`Rendering.docx`.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

Deze coderegel laadt het document vanuit de opgegeven map.

## Stap 3: Configureer HTML-opslagopties

Om bronnen zoals CSS en lettertypen te exporteren, moet u het`HtmlSaveOptions`. Deze stap is cruciaal om ervoor te zorgen dat uw HTML-uitvoer goed gestructureerd is en de nodige bronnen bevat.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions
{
    CssStyleSheetType = CssStyleSheetType.External,
    ExportFontResources = true,
    ResourceFolder = dataDir + "Resources",
    ResourceFolderAlias = "http://voorbeeld.com/resources"
};
```

Laten we eens kijken wat elke optie doet:
- `CssStyleSheetType = CssStyleSheetType.External`: deze optie geeft aan dat CSS-stijlen moeten worden opgeslagen in een extern stylesheet.
- `ExportFontResources = true`: Hiermee wordt de export van lettertypebronnen mogelijk gemaakt.
- `ResourceFolder = dataDir + "Resources"`: specificeert de lokale map waarin bronnen (zoals lettertypen en CSS-bestanden) worden opgeslagen.
- `ResourceFolderAlias = "http://example.com/resources"`: Stelt een alias in voor de bronmap, die in het HTML-bestand zal worden gebruikt.

## Stap 4: Sla het document op als HTML

Als de opslagopties zijn geconfigureerd, is de laatste stap het opslaan van het document als een HTML-bestand. Zo doe je het:

```csharp
doc.Save(dataDir + "WorkingWithHtmlSaveOptions.ExportResources.html", saveOptions);
```

Deze coderegel slaat het document op in HTML-indeling, samen met de geëxporteerde bronnen.

## Conclusie

En daar heb je het! U hebt met succes bronnen geëxporteerd terwijl u een Word-document als HTML hebt opgeslagen met Aspose.Words voor .NET. Met deze krachtige bibliotheek wordt het programmatisch omgaan met Word-documenten een fluitje van een cent. Of u nu aan een webapplicatie werkt of gewoon documenten moet converteren voor offline gebruik, Aspose.Words heeft de oplossing voor u.

## Veelgestelde vragen

### Kan ik afbeeldingen samen met lettertypen en CSS exporteren?
 Ja, dat kan! Aspose.Words voor .NET ondersteunt ook het exporteren van afbeeldingen. Zorg ervoor dat u de`HtmlSaveOptions` overeenkomstig.

### Is er een manier om CSS in te sluiten in plaats van een extern stylesheet te gebruiken?
 Absoluut. Je kunt instellen`CssStyleSheetType` naar`CssStyleSheetType.Embedded` als u de voorkeur geeft aan ingebedde stijlen.

### Hoe kan ik de naam van het HTML-uitvoerbestand aanpassen?
 U kunt elke gewenste bestandsnaam opgeven in het`doc.Save` methode. Bijvoorbeeld,`doc.Save(dataDir + "CustomFileName.html", saveOptions);`.

### Ondersteunt Aspose.Words naast HTML ook andere formaten?
 Ja, het ondersteunt verschillende formaten, waaronder PDF, DOCX, TXT en meer. Bekijk de[documentatie](https://reference.aspose.com/words/net/) voor een volledige lijst.

### Waar kan ik meer ondersteuning en middelen krijgen?
Ga voor meer hulp naar de[Aspose.Words-ondersteuningsforum](https://forum.aspose.com/c/words/8) . Gedetailleerde documentatie en voorbeelden vindt u ook op de[Aspose-website](https://reference.aspose.com/words/net/).