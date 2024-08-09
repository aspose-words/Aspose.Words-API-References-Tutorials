---
title: Beeldverhouding vergrendeld
linktitle: Beeldverhouding vergrendeld
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de beeldverhouding van vormen in Word-documenten kunt vergrendelen met Aspose.Words voor .NET. Volg deze stapsgewijze handleiding om uw afbeeldingen en vormen proportioneel te houden.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/aspect-ratio-locked/
---
## Invoering

Heeft u zich ooit afgevraagd hoe u de perfecte verhoudingen van afbeeldingen en vormen in uw Word-documenten kunt behouden? Soms moet u ervoor zorgen dat uw afbeeldingen en vormen niet vervormd raken als u het formaat wijzigt. Dit is waar het vergrendelen van de beeldverhouding van pas komt. In deze zelfstudie onderzoeken we hoe u de beeldverhouding voor vormen in Word-documenten kunt instellen met Aspose.Words voor .NET. We splitsen het op in eenvoudig te volgen stappen, zodat u deze vaardigheden met vertrouwen op uw projecten kunt toepassen.

## Vereisten

Voordat we in de code duiken, laten we eens kijken wat u nodig heeft om aan de slag te gaan:

- Aspose.Words voor .NET-bibliotheek: Aspose.Words voor .NET moet geïnstalleerd zijn. Als je dat nog niet hebt gedaan, dan kan dat[download het hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: Zorg ervoor dat u een .NET-ontwikkelomgeving hebt ingesteld. Visual Studio is een populaire keuze.
- Basiskennis van C#: Enige bekendheid met programmeren in C# zal nuttig zijn.

## Naamruimten importeren

Laten we eerst de benodigde naamruimten importeren. Deze naamruimten geven ons toegang tot de klassen en methoden die we nodig hebben om met Word-documenten en -vormen te werken.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Stap 1: Stel uw documentenmap in

 Voordat we vormen gaan manipuleren, moeten we een map opzetten waarin onze documenten worden opgeslagen. Voor de eenvoud gebruiken we een tijdelijke aanduiding`YOUR DOCUMENT DIRECTORY`. Vervang dit door het daadwerkelijke pad naar uw documentmap.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Stap 2: Maak een nieuw document

Vervolgens maken we een nieuw Word-document met Aspose.Words. Dit document zal dienen als ons canvas voor het toevoegen van vormen en afbeeldingen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Hier maken we een exemplaar van de`Document` klasse en gebruik een`DocumentBuilder` om ons te helpen de documentinhoud op te bouwen.

## Stap 3: Voeg een afbeelding in

 Laten we nu een afbeelding in ons document invoegen. Wij gebruiken de`InsertImage` werkwijze van de`DocumentBuilder`klas. Zorg ervoor dat u een afbeelding in de door u opgegeven map heeft.

```csharp
Shape shape = builder.InsertImage(dataDir + "Transparent background logo.png");
```

 Vervangen`dataDir + "Transparent background logo.png"` met het pad naar uw afbeeldingsbestand.

## Stap 4: Vergrendel de beeldverhouding

Zodra de afbeelding is ingevoegd, kunnen we de beeldverhouding vergrendelen. Het vergrendelen van de beeldverhouding zorgt ervoor dat de verhoudingen van de afbeelding constant blijven bij het wijzigen van het formaat.

```csharp
shape.AspectRatioLocked = true;
```

 Instelling`AspectRatioLocked` naar`true` zorgt ervoor dat de afbeelding de oorspronkelijke beeldverhouding behoudt.

## Stap 5: Bewaar het document

Ten slotte slaan we het document op in de opgegeven map. Met deze stap worden alle wijzigingen geschreven die we in het documentbestand hebben aangebracht.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u de beeldverhouding voor vormen in Word-documenten kunt instellen met Aspose.Words voor .NET. Door deze stappen te volgen, kunt u ervoor zorgen dat uw afbeeldingen en vormen hun verhoudingen behouden, waardoor uw documenten er professioneel en verzorgd uitzien. Experimenteer gerust met verschillende afbeeldingen en vormen om te zien hoe de vergrendelingsfunctie voor de beeldverhouding in verschillende scenario's werkt.

## Veelgestelde vragen

### Kan ik de beeldverhouding ontgrendelen nadat ik deze heb vergrendeld?
Ja, u kunt de beeldverhouding ontgrendelen door in te stellen`shape.AspectRatioLocked = false`.

### Wat gebeurt er als ik het formaat van een afbeelding met een vergrendelde beeldverhouding wijzig?
Het formaat van de afbeelding wordt proportioneel aangepast, waarbij de oorspronkelijke breedte-hoogteverhouding behouden blijft.

### Kan ik dit naast afbeeldingen ook op andere vormen toepassen?
Absoluut! De functie voor het vergrendelen van de beeldverhouding kan op elke vorm worden toegepast, inclusief rechthoeken, cirkels en meer.

### Is Aspose.Words voor .NET compatibel met .NET Core?
Ja, Aspose.Words voor .NET ondersteunt zowel .NET Framework als .NET Core.

### Waar kan ik meer documentatie vinden over Aspose.Words voor .NET?
 U kunt uitgebreide documentatie vinden[hier](https://reference.aspose.com/words/net/).