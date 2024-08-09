---
title: Tekstinvoerformulierveld exporteren als tekst
linktitle: Tekstinvoerformulierveld exporteren als tekst
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tekstinvoerformuliervelden als platte tekst kunt exporteren met Aspose.Words voor .NET met deze uitgebreide, stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/programming-with-htmlsaveoptions/export-text-input-form-field-as-text/
---
## Invoering

Dus je duikt in de wereld van Aspose.Words voor .NET? Geweldige keuze! Als u wilt leren hoe u een tekstinvoerformulierveld als tekst kunt exporteren, bent u hier op de juiste plek. Of u nu net begint of uw vaardigheden aan het opfrissen bent, deze gids leidt u door alles wat u moet weten. Laten we beginnen, oké?

## Vereisten

Voordat we in de kern duiken, moeten we ervoor zorgen dat je alles hebt wat je nodig hebt om het probleemloos te kunnen volgen:

-  Aspose.Words voor .NET: Download en installeer de nieuwste versie van[hier](https://releases.aspose.com/words/net/).
- IDE: Visual Studio of een andere C#-ontwikkelomgeving.
- Basiskennis van C#: inzicht in de basissyntaxis van C# en objectgeoriënteerde programmeerconcepten.
- Document: een voorbeeld van een Word-document (`Rendering.docx`) met tekstinvoerformuliervelden.

## Naamruimten importeren

Allereerst moet u de benodigde naamruimten importeren. Dit zijn een soort bouwstenen die ervoor zorgen dat alles naadloos werkt.

```csharp
using System;
using System.IO;
using Aspose.Words;
using Aspose.Words.Saving;
```

Oké, nu we onze naamruimtes gereed hebben, gaan we aan de slag!

## Stap 1: Stel het project in

Voordat we ingaan op de code, moeten we ervoor zorgen dat ons project correct is ingesteld.

## Het project maken

1. Open Visual Studio: Begin met het openen van Visual Studio of uw favoriete C#-ontwikkelomgeving.
2.  Maak een nieuw project: Navigeer naar`File > New > Project` . Selecteer`Console App (.NET Core)` of een ander relevant projecttype.
3.  Geef uw project een naam: Geef uw project een betekenisvolle naam, zoiets als`AsposeWordsExportExample`.

## Aspose.Words toevoegen

1.  NuGet-pakketten beheren: klik met de rechtermuisknop op uw project in de Solution Explorer en selecteer`Manage NuGet Packages`.
2.  Zoek naar Aspose.Words: Zoek in NuGet Package Manager naar`Aspose.Words`.
3.  Installeer Aspose.Woorden: Klik op`Install` om de Aspose.Words-bibliotheek aan uw project toe te voegen.

## Stap 2: Laad het Word-document

Nu ons project is opgezet, gaan we het Word-document laden dat de tekstinvoerformuliervelden bevat.

1. Geef de documentmap op: definieer het pad naar de map waar uw document is opgeslagen.
2.  Laad het document: Gebruik de`Document` klasse om uw Word-document te laden.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

## Stap 3: Bereid de exportmap voor

Voordat we gaan exporteren, zorgen we ervoor dat onze exportmap gereed is. Dit is waar ons HTML-bestand en afbeeldingen worden opgeslagen.

1. Definieer de exportmap: geef het pad op waar de geëxporteerde bestanden worden opgeslagen.
2. Controleer en reinig de map: Zorg ervoor dat de map bestaat en leeg is.

```csharp
string imagesDir = Path.Combine(dataDir, "Images");

if (Directory.Exists(imagesDir))
    Directory.Delete(imagesDir, true);

Directory.CreateDirectory(imagesDir);
```

## Stap 4: Configureer de opslagopties

Hier gebeurt de magie. We moeten onze opslagopties instellen om het tekstinvoerformulierveld als platte tekst te exporteren.

1.  Creëer opslagopties: Initialiseer een nieuwe`HtmlSaveOptions` voorwerp.
2.  Optie voor exporttekst instellen: Configureer de`ExportTextInputFormFieldAsText`eigendom aan`true`.
3. Map afbeeldingen instellen: Definieer de map waarin afbeeldingen worden opgeslagen.

```csharp
HtmlSaveOptions saveOptions = new HtmlSaveOptions(SaveFormat.Html)
{
    ExportTextInputFormFieldAsText = true,
    ImagesFolder = imagesDir
};
```

## Stap 5: Sla het document op als HTML

Laten we ten slotte het Word-document opslaan als een HTML-bestand met behulp van onze geconfigureerde opslagopties.

1. Definieer het uitvoerpad: Geef het pad op waar het HTML-bestand zal worden opgeslagen.
2.  Sla het document op: gebruik de`Save` werkwijze van de`Document`klasse om het document te exporteren.

```csharp
doc.Save(dataDir + "ExportedDocument.html", saveOptions);
```

## Conclusie

En daar heb je het! U hebt met succes een tekstinvoerformulierveld als platte tekst geëxporteerd met Aspose.Words voor .NET. Deze gids had u een duidelijke, stapsgewijze aanpak moeten bieden om deze taak te volbrengen. Vergeet niet dat oefening kunst baart, dus blijf experimenteren met verschillende opties en instellingen om te zien wat u nog meer kunt doen met Aspose.Words.

## Veelgestelde vragen

### Kan ik andere typen formuliervelden op dezelfde manier exporteren?

 Ja, u kunt andere typen formuliervelden exporteren door verschillende eigenschappen van het`HtmlSaveOptions` klas.

### Wat moet ik doen als mijn document afbeeldingen bevat?

 De afbeeldingen worden opgeslagen in de opgegeven afbeeldingenmap. Zorg ervoor dat u de`ImagesFolder` eigendom in de`HtmlSaveOptions`.

### Heb ik een licentie nodig voor Aspose.Words?

 Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/) of koop een licentie[hier](https://purchase.aspose.com/buy).

### Kan ik de geëxporteerde HTML aanpassen?

 Absoluut! Aspose.Words biedt verschillende opties om de HTML-uitvoer aan te passen. Raadpleeg de[documentatie](https://reference.aspose.com/words/net/) voor meer informatie.

### Is Aspose.Words compatibel met .NET Core?

Ja, Aspose.Words is compatibel met .NET Core, .NET Framework en andere .NET-platforms.
