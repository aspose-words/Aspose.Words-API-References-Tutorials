---
title: Zwevende afbeelding invoegen in Word-document
linktitle: Zwevende afbeelding invoegen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een zwevende afbeelding invoegt in een Word-document met Aspose.Words voor .NET met deze gedetailleerde stapsgewijze handleiding. Perfect voor het verbeteren van uw documenten.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/insert-floating-image/
---
## Invoering

Stelt u zich eens voor dat u een verbluffend rapport of voorstel maakt waarin afbeeldingen perfect gepositioneerd zijn om uw tekst aan te vullen. Met Aspose.Words voor .NET kunt u dit moeiteloos bereiken. Deze bibliotheek biedt krachtige functies voor documentmanipulatie, waardoor het een go-to-oplossing is voor ontwikkelaars. In deze zelfstudie concentreren we ons op het invoegen van een zwevende afbeelding met behulp van de klasse DocumentBuilder. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze gids begeleidt u bij elke stap.

## Vereisten

Voordat we erin duiken, zorgen we ervoor dat u alles heeft wat u nodig heeft om aan de slag te gaan:

1.  Aspose.Words voor .NET: U kunt de bibliotheek downloaden van de[Aspose-releasespagina](https://releases.aspose.com/words/net/).
2. Visual Studio: elke versie die .NET-ontwikkeling ondersteunt.
3. Basiskennis van C#: Het begrijpen van de basisprincipes van C#-programmeren zal nuttig zijn.
4. Afbeeldingsbestand: een afbeeldingsbestand dat u wilt invoegen, zoals een logo of afbeelding.

## Naamruimten importeren

Om Aspose.Words in uw project te gebruiken, moet u de benodigde naamruimten importeren. Dit doet u door de volgende regels bovenaan uw C#-bestand toe te voegen:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

Nu deze vereisten en naamruimten aanwezig zijn, zijn we klaar om onze zelfstudie te starten.

Laten we het proces van het invoegen van een zwevende afbeelding in een Word-document opsplitsen in beheersbare stappen. Elke stap wordt gedetailleerd uitgelegd, zodat u zonder problemen kunt doorgaan.

## Stap 1: Stel uw project in

Maak eerst een nieuw C#-project in Visual Studio. Voor de eenvoud kunt u een console-app kiezen.

1. Open Visual Studio en maak een nieuw project.
2. Selecteer 'Console-app (.NET Core)' en klik op 'Volgende'.
3. Geef uw project een naam en kies een locatie om het op te slaan. Klik op 'Maken'.
4. Installeer Aspose.Words voor .NET via NuGet Package Manager. Klik met de rechtermuisknop op uw project in de Solution Explorer, selecteer 'NuGet-pakketten beheren' en zoek naar 'Apose.Words'. Installeer de nieuwste versie.

## Stap 2: Initialiseer Document en DocumentBuilder

Nu uw project is ingesteld, gaan we de Document- en DocumentBuilder-objecten initialiseren.

1.  Maak een nieuw exemplaar van de`Document` klas:

```csharp
Document doc = new Document();
```

2. Initialiseer een DocumentBuilder-object:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

 De`Document` object vertegenwoordigt het Word-document, en de`DocumentBuilder` helpt bij het toevoegen van inhoud eraan.

## Stap 3: Definieer het afbeeldingspad

Geef vervolgens het pad naar uw afbeeldingsbestand op. Zorg ervoor dat uw afbeelding toegankelijk is vanuit de map van uw project.

Definieer de afbeeldingsmap en de afbeeldingsbestandsnaam:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string imagePath = dataDir + "Transparent background logo.png";
```

 Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad waar uw afbeelding is opgeslagen.

## Stap 4: Voeg de zwevende afbeelding in

Nu alles is ingesteld, gaan we de zwevende afbeelding in het document invoegen.

 Gebruik de`InsertImage` werkwijze van de`DocumentBuilder` klasse om de afbeelding in te voegen:

```csharp
builder.InsertImage(imagePath,
   RelativeHorizontalPosition.Margin,
   100,
   RelativeVerticalPosition.Margin,
   100,
   200,
   100,
   WrapType.Square);
```

Dit is wat elke parameter betekent:
- `imagePath`Het pad naar uw afbeeldingsbestand.
- `RelativeHorizontalPosition.Margin`: De horizontale positie ten opzichte van de marge.
- `100`: De horizontale verschuiving vanaf de marge (in punten).
- `RelativeVerticalPosition.Margin`: De verticale positie ten opzichte van de marge.
- `100`: De verticale verschuiving vanaf de marge (in punten).
- `200`: De breedte van de afbeelding (in punten).
- `100`: De hoogte van de afbeelding (in punten).
- `WrapType.Square`: De tekstterugloopstijl rond de afbeelding.

## Stap 5: Bewaar het document

Sla het document ten slotte op de gewenste locatie op.

1. Geef het pad voor het uitvoerbestand op:

```csharp
string outputPath = dataDir + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx";
```

2. Bewaar het document:

```csharp
doc.Save(outputPath);
```

Je Word-document met de zwevende afbeelding is nu klaar!

## Conclusie

Het invoegen van een zwevende afbeelding in een Word-document met Aspose.Words voor .NET is een eenvoudig proces als het wordt opgesplitst in beheersbare stappen. Door deze handleiding te volgen, kunt u professioneel ogende afbeeldingen aan uw documenten toevoegen, waardoor de visuele aantrekkingskracht ervan wordt vergroot. Aspose.Words biedt een robuuste API die documentmanipulatie kinderspel maakt, of u nu aan rapporten, voorstellen of een ander documenttype werkt.

## Veelgestelde vragen

### Kan ik meerdere afbeeldingen invoegen met Aspose.Words voor .NET?

 Ja, u kunt meerdere afbeeldingen invoegen door de opdracht te herhalen`InsertImage` methode voor elke afbeelding met de gewenste parameters.

### Hoe wijzig ik de positie van de afbeelding?

 U kunt de`RelativeHorizontalPosition`, `RelativeVerticalPosition`en offsetparameters om de afbeelding naar wens te positioneren.

### Welke andere omslagtypen zijn beschikbaar voor afbeeldingen?

 Aspose.Words ondersteunt verschillende soorten wraps, zoals`Inline`, `TopBottom`, `Tight`, `Through`, en meer. U kunt degene kiezen die het beste bij uw documentindeling past.

### Kan ik verschillende afbeeldingsformaten gebruiken?

Ja, Aspose.Words ondersteunt een breed scala aan afbeeldingsformaten, waaronder JPEG, PNG, BMP en GIF.

### Hoe krijg ik een gratis proefversie van Aspose.Words voor .NET?

 U kunt een gratis proefversie krijgen van de[Aspose gratis proefpagina](https://releases.aspose.com/).