---
title: Verklein de PDF-grootte door WMF-lettertypen te schalen naar metabestandsgrootte
linktitle: Verklein de PDF-grootte door WMF-lettertypen te schalen naar metabestandsgrootte
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om de pdf-grootte te verkleinen door wmf-lettertypen te schalen naar de grootte van metabestanden bij het converteren naar pdf met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-pdfsaveoptions/scale-wmf-fonts-to-metafile-size/
---
## Invoering

Bij het werken met PDF-bestanden, vooral als deze zijn gegenereerd op basis van Word-documenten die WMF-afbeeldingen (Windows Metafile) bevatten, kan formaatbeheer een cruciaal aspect worden van de documentverwerking. Eén manier om de PDF-grootte te beheren is door aan te passen hoe WMF-lettertypen in het document worden weergegeven. In deze zelfstudie onderzoeken we hoe u de PDF-grootte kunt verkleinen door WMF-lettertypen te schalen naar de metabestandsgrootte met behulp van Aspose.Words voor .NET.

## Vereisten

Voordat u in de stappen duikt, moet u ervoor zorgen dat u over het volgende beschikt:

1. Aspose.Words voor .NET: Zorg ervoor dat de Aspose.Words-bibliotheek is geïnstalleerd. Zo niet, dan kan dat[download het hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: in deze zelfstudie wordt ervan uitgegaan dat u een .NET-ontwikkelomgeving hebt ingesteld (zoals Visual Studio) waarin u C#-code kunt schrijven en uitvoeren.
3. Basiskennis van .NET-programmering: Bekendheid met de basisconcepten van .NET-programmering en C#-syntaxis zal nuttig zijn.
4. Word-document met WMF-afbeeldingen: u hebt een Word-document nodig met WMF-afbeeldingen. U kunt uw eigen document gebruiken of er een maken om te testen.

## Naamruimten importeren

Eerst moet u de benodigde naamruimten in uw C#-project importeren. Hiermee krijgt u toegang tot de klassen en methoden die nodig zijn om met Aspose.Words te werken.

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## Stap 1: Laad het Word-document

 Laad om te beginnen het Word-document dat de WMF-afbeeldingen bevat. Dit gebeurt met behulp van de`Document` klasse van Aspose.Words.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "WMF with text.docx");
```

 Hier,`dataDir` is een tijdelijke aanduiding voor het pad van uw documentmap. We maken een exemplaar van de`Document` klasse door het pad naar het Word-bestand door te geven. Hierdoor wordt het document in het geheugen geladen, klaar voor verdere verwerking.

## Stap 2: Configureer de weergaveopties voor metabestanden

 Vervolgens moet u de weergaveopties voor metabestanden configureren. Stel met name de`ScaleWmfFontsToMetafileSize`eigendom aan`false`. Dit bepaalt of WMF-lettertypen worden geschaald zodat ze overeenkomen met de grootte van het metabestand.

```csharp
// Maak een nieuw exemplaar van MetafileRenderingOptions
MetafileRenderingOptions metafileRenderingOptions = new MetafileRenderingOptions
{
    ScaleWmfFontsToMetafileSize = false
};
```

 De`MetafileRenderingOptions` class biedt opties voor hoe metabestanden (zoals WMF) worden weergegeven. Door in te stellen`ScaleWmfFontsToMetafileSize` naar`false`, geeft u Aspose.Words de opdracht om lettertypen niet te schalen op basis van de metabestandsgrootte, wat kan helpen bij het verkleinen van de totale PDF-grootte.

## Stap 3: Stel de PDF-opslagopties in

Configureer nu de PDF-opslagopties om de weergaveopties voor metabestanden te gebruiken die u zojuist hebt ingesteld. Dit vertelt Aspose.Words hoe om te gaan met metabestanden bij het opslaan van het document als PDF.

```csharp
// Maak een nieuw exemplaar van PdfSaveOptions
PdfSaveOptions saveOptions = new PdfSaveOptions
{
    MetafileRenderingOptions = metafileRenderingOptions
};
```

 De`PdfSaveOptions` Met class kunt u verschillende instellingen opgeven voor het opslaan van het document als PDF. Door het eerder geconfigureerde toe te wijzen`MetafileRenderingOptions` naar de`MetafileRenderingOptions` eigendom van`PdfSaveOptions`, zorgt u ervoor dat het document wordt opgeslagen volgens de door u gewenste weergave-instellingen voor metabestanden.

## Stap 4: Sla het document op als PDF

Sla ten slotte het Word-document op als PDF met behulp van de geconfigureerde opslagopties. Hierdoor worden alle instellingen, inclusief de weergaveopties voor metabestanden, toegepast op de uitvoer-PDF.


```csharp
// Sla het document op als PDF
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ScaleWmfFontsToMetafileSize.pdf", saveOptions);
```

 In deze stap wordt de`Save` werkwijze van de`Document` class wordt gebruikt om het document naar een PDF-bestand te exporteren. Het pad waar de PDF wordt opgeslagen, wordt opgegeven, samen met het`PdfSaveOptions` die de weergave-instellingen voor metabestanden bevatten.

## Conclusie

Door WMF-lettertypen te schalen naar de grootte van metabestanden, kunt u de grootte van uw PDF-bestanden die zijn gegenereerd op basis van Word-documenten aanzienlijk verkleinen. Deze techniek helpt bij het optimaliseren van de opslag en distributie van documenten zonder de kwaliteit van de visuele inhoud in gevaar te brengen. Als u de hierboven beschreven stappen volgt, zorgt u ervoor dat uw PDF-bestanden beter beheersbaar en efficiënter van formaat zijn.

## Veelgestelde vragen

### Wat is WMF en waarom is het belangrijk voor PDF-grootte?

WMF (Windows Metafile) is een grafisch formaat dat wordt gebruikt in Microsoft Windows. Het kan zowel vector- als bitmapgegevens bevatten. Omdat vectorgegevens kunnen worden geschaald en gemanipuleerd, is het belangrijk om er op de juiste manier mee om te gaan om onnodig grote PDF-bestanden te voorkomen.

### Welke invloed heeft het schalen van WMF-lettertypen naar de grootte van metabestanden op de PDF?

Door WMF-lettertypen te schalen naar de grootte van metabestanden, kunt u de algehele PDF-grootte verkleinen door lettertypeweergave met hoge resolutie te vermijden, waardoor de bestandsgrootte groter zou kunnen worden.

### Kan ik andere metabestandsformaten gebruiken met Aspose.Words?

Ja, Aspose.Words ondersteunt verschillende metabestandsindelingen, waaronder EMF (Enhanced Metafile) naast WMF.

### Is deze techniek toepasbaar op alle soorten Word-documenten?

Ja, deze techniek kan worden toegepast op elk Word-document dat WMF-afbeeldingen bevat, waardoor de grootte van de gegenereerde PDF wordt geoptimaliseerd.

### Waar kan ik meer informatie vinden over Aspose.Words?

 U kunt meer over Aspose.Words ontdekken in de[Aspose.Words-documentatie](https://reference.aspose.com/words/net/) . Voor downloads, proefversies en ondersteuning gaat u naar de[Aspose.Words-downloadpagina](https://releases.aspose.com/words/net/), [Koop Aspose.Words](https://purchase.aspose.com/buy), [Gratis proefperiode](https://releases.aspose.com/), [Tijdelijke licentie](https://purchase.aspose.com/temporary-license/) , En[Steun](https://forum.aspose.com/c/words/8).