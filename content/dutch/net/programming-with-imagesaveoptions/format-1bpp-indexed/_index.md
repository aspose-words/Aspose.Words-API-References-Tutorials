---
title: Formaat 1Bpp geïndexeerd
linktitle: Formaat 1Bpp geïndexeerd
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een Word-document converteert naar een 1Bpp-geïndexeerde afbeelding met Aspose.Words voor .NET. Volg onze stapsgewijze handleiding voor eenvoudige conversie.
type: docs
weight: 10
url: /nl/net/programming-with-imagesaveoptions/format-1bpp-indexed/
---
## Invoering

Heeft u zich ooit afgevraagd hoe u een Word-document kunt opslaan als zwart-witafbeelding met slechts een paar regels code? Nou, je hebt geluk! Vandaag duiken we in een leuk trucje met Aspose.Words voor .NET waarmee u uw documenten kunt converteren naar 1Bpp-geïndexeerde afbeeldingen. Dit formaat is perfect voor bepaalde soorten digitale archivering, afdrukken of wanneer u ruimte wilt besparen. We zullen elke stap opsplitsen om het zo eenvoudig mogelijk te maken. Klaar om aan de slag te gaan? Laten we erin duiken!

## Vereisten

Voordat we onze handen vuil maken, zijn er een paar dingen die je op orde moet hebben:

-  Aspose.Words voor .NET: Zorg ervoor dat de bibliotheek is geïnstalleerd. Dat kan[download het hier](https://releases.aspose.com/words/net/).
- .NET-ontwikkelomgeving: Visual Studio is een goede optie, maar u kunt elke omgeving gebruiken waar u zich prettig bij voelt.
- Basiskennis van C#: Maak je geen zorgen, we houden het simpel, maar een beetje bekendheid met C# zal helpen.
- Een Word-document: Zorg ervoor dat u een voorbeeld van een Word-document gereed heeft om te worden geconverteerd.

## Naamruimten importeren

Allereerst moeten we de benodigde naamruimten importeren. Dit is cruciaal omdat het ons toegang geeft tot de klassen en methoden die we nodig hebben vanuit Aspose.Words.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Stap 1: Stel uw documentenmap in

U moet het pad naar uw documentmap opgeven. Dit is waar uw Word-document wordt opgeslagen en waar de geconverteerde afbeelding wordt opgeslagen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Laad het Word-document

 Laten we nu het Word-document in een Aspose.Words laden`Document` voorwerp. Dit object vertegenwoordigt uw Word-bestand en stelt u in staat het te manipuleren.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 3: Configureer de opties voor het opslaan van afbeeldingen

 Vervolgens moeten we de`ImageSaveOptions`Dit is waar de magie gebeurt. We zullen het configureren om de afbeelding op te slaan in PNG-indeling met 1Bpp geïndexeerde kleurmodus.

```csharp
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFormat.Png)
{
    PageSet = new PageSet(1),
    ImageColorMode = ImageColorMode.BlackAndWhite,
    PixelFormat = ImagePixelFormat.Format1bppIndexed
};
```

- SaveFormat.Png: Dit geeft aan dat we het document willen opslaan als een PNG-afbeelding.
- PageSet(1): Dit geeft aan dat we alleen de eerste pagina converteren.
- ImageColorMode.BlackAndWhite: Hiermee wordt de afbeelding ingesteld op zwart en wit.
- ImagePixelFormat.Format1bppIndexed: Hiermee wordt het afbeeldingsformaat ingesteld op 1Bpp geïndexeerd.

## Stap 4: Sla het document op als afbeelding

 Ten slotte slaan we het document op als afbeelding met behulp van de`Save` werkwijze van de`Document` voorwerp.

```csharp
doc.Save(dataDir + "WorkingWithImageSaveOptions.Format1BppIndexed.Png", saveOptions);
```

## Conclusie

En daar heb je het! Met slechts een paar regels code heeft u uw Word-document omgezet in een 1Bpp-geïndexeerde afbeelding met Aspose.Words voor .NET. Deze methode is ongelooflijk handig voor het maken van contrastrijke, ruimtebesparende afbeeldingen van uw documenten. Nu kunt u dit eenvoudig integreren in uw projecten en workflows. Veel codeerplezier!

## Veelgestelde vragen

### Wat is een 1Bpp-geïndexeerde afbeelding?
Een 1Bpp (1 Bit Per Pixel) geïndexeerde afbeelding is een zwart-wit beeldformaat waarbij elke pixel wordt weergegeven door een enkele bit, 0 of 1. Dit formaat is zeer ruimtebesparend.

### Kan ik meerdere pagina's van een Word-document tegelijk converteren?
 Ja, dat kan. Wijzig de`PageSet` eigendom in de`ImageSaveOptions` om meerdere pagina's of het hele document op te nemen.

### Heb ik een licentie nodig om Aspose.Words voor .NET te gebruiken?
 Ja, Aspose.Words voor .NET vereist een licentie voor volledige functionaliteit. Je kunt een[tijdelijke licentie hier](https://purchase.aspose.com/temporary-license/).

### Naar welke andere afbeeldingsformaten kan ik mijn Word-document converteren?
 Aspose.Words ondersteunt verschillende afbeeldingsformaten, waaronder JPEG, BMP en TIFF. Verander eenvoudigweg de`SaveFormat` in de`ImageSaveOptions`.

### Waar kan ik meer documentatie vinden over Aspose.Words voor .NET?
 Uitgebreide documentatie vindt u op de website[Aspose.Words voor .NET-documentatiepagina](https://reference.aspose.com/words/net/).
