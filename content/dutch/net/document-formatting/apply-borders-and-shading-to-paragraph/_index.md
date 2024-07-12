---
title: Randen en arcering toepassen op alinea's in Word-document
linktitle: Randen en arcering toepassen op alinea's in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Pas randen en arcering toe op alinea's in Word-documenten met Aspose.Words voor .NET. Volg onze stapsgewijze handleiding om uw documentopmaak te verbeteren.
type: docs
weight: 10
url: /nl/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
## Invoering

Hallo daar, heb je je ooit afgevraagd hoe je je Word-documenten kunt laten opvallen met mooie randen en schaduwen? Nou, je bent op de juiste plek! Vandaag duiken we in de wereld van Aspose.Words voor .NET om onze paragrafen op te fleuren. Stel u voor dat uw document er met slechts een paar regels code net zo strak uitziet als het werk van een professionele ontwerper. klaar om te beginnen? Laten we gaan!

## Vereisten

Voordat we onze mouwen opstropen en in coderen duiken, moeten we ervoor zorgen dat we alles hebben wat we nodig hebben. Hier is uw snelle checklist:

-  Aspose.Words voor .NET: deze bibliotheek moet geïnstalleerd zijn. Je kunt het downloaden van de[Aspose-website](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: Visual Studio of een andere IDE die .NET ondersteunt.
- Basiskennis van C#: net genoeg om de codefragmenten te begrijpen en aan te passen.
- Een geldige licentie: Ofwel a[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) of een gekocht exemplaar[Stel](https://purchase.aspose.com/buy).

## Naamruimten importeren

Voordat we in de code springen, moeten we ervoor zorgen dat we de benodigde naamruimten in ons project hebben geïmporteerd. Dit maakt alle coole functies van Aspose.Words voor ons toegankelijk.

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using Aspose.Words.Drawing;
using System.Drawing;
```

Laten we het proces nu in hapklare stappen opsplitsen. Elke stap heeft een kop en een gedetailleerde uitleg. Klaar? Laten we gaan!

## Stap 1: Stel uw documentenmap in

Allereerst hebben we een plek nodig om ons prachtig opgemaakte document op te slaan. Laten we het pad naar uw documentmap instellen.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 In deze map wordt uw definitieve document opgeslagen. Vervangen`"YOUR DOCUMENT DIRECTORY"` met het daadwerkelijke pad op uw machine.

## Stap 2: Maak een nieuw document en DocumentBuilder

 Vervolgens moeten we een nieuw document maken en een`DocumentBuilder` voorwerp. De`DocumentBuilder` is onze toverstaf waarmee we het document kunnen manipuleren.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 De`Document` object vertegenwoordigt ons hele Word-document, en de`DocumentBuilder` helpt ons inhoud toe te voegen en op te maken.

## Stap 3: Definieer alinearanden

Laten we nu een aantal stijlvolle randen aan onze paragraaf toevoegen. We definiëren de afstand tot de tekst en stellen verschillende randstijlen in.

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders.DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

Hier stellen we een afstand van 20 punten in tussen de tekst en de randen. De randen aan alle zijden (links, rechts, boven, onder) zijn ingesteld op dubbele lijnen. Zin, toch?

## Stap 4: Pas arcering toe op de alinea

Randen zijn geweldig, maar laten we een stapje verder gaan met wat schaduw. We gebruiken een diagonaal kruispatroon met een mix van kleuren om onze alinea te laten opvallen.

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

In deze stap hebben we een diagonale kruistextuur toegepast met licht koraal als achtergrondkleur en licht zalm als voorgrondkleur. Het is alsof je je paragraaf in merkkleding kleedt!

## Stap 5: Voeg tekst toe aan de alinea

Wat is een alinea zonder tekst? Laten we een voorbeeldzin toevoegen om onze opmaak in actie te zien.

```csharp
builder.Write("I'm a formatted paragraph with double border and nice shading.");
```

Deze regel voegt onze tekst in het document in. Eenvoudig, maar nu verpakt in een stijlvol kader en een schaduwrijke achtergrond.

## Stap 6: Bewaar het document

Eindelijk is het tijd om ons werk te redden. Laten we het document opslaan in de opgegeven map met een beschrijvende naam.

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

 Hiermee wordt ons document met de naam opgeslagen`DocumentFormatting.ApplyBordersAndShadingToParagraph.doc` in de map die we eerder hebben opgegeven.

## Conclusie

En daar heb je het! Met slechts een paar regels code hebben we een eenvoudige alinea omgezet in een visueel aantrekkelijk stukje inhoud. Aspose.Words voor .NET maakt het ongelooflijk eenvoudig om professioneel ogende opmaak aan uw documenten toe te voegen. Of u nu een rapport, een brief of een ander document voorbereidt, deze trucs zullen u helpen een geweldige indruk te maken. Dus ga uw gang, probeer het uit en zie hoe uw documenten tot leven komen!

## Veelgestelde vragen

### Kan ik voor elke rand verschillende lijnstijlen gebruiken?  
 Absoluut! Met Aspose.Words voor .NET kunt u elke rand afzonderlijk aanpassen. Stel gewoon de`LineStyle` voor elk randtype, zoals weergegeven in de handleiding.

### Welke andere schaduwtexturen zijn beschikbaar?  
 Er zijn verschillende texturen die u kunt gebruiken, zoals effen, horizontale strepen, verticale strepen en meer. Controleer de[Documentatie aanvragen](https://reference.aspose.com/words/net/) voor een volledige lijst.

### Hoe kan ik de randkleur wijzigen?  
 U kunt de randkleur instellen met behulp van de`Color` eigendom voor elke grens. Bijvoorbeeld,`borders[BorderType.Left].Color = Color.Red;`.

### Is het mogelijk om randen en arcering toe te passen op een specifiek deel van de tekst?  
 Ja, u kunt randen en arcering toepassen op specifieke tekstgedeelten met behulp van de`Run` voorwerp binnen de`DocumentBuilder`.

### Kan ik dit proces voor meerdere alinea's automatiseren?  
Zeker! U kunt door uw alinea's lopen en dezelfde instellingen voor randen en arcering programmatisch toepassen.
