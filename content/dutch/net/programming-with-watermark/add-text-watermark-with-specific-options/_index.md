---
title: Voeg tekstwatermerk toe met specifieke opties
linktitle: Voeg tekstwatermerk toe met specifieke opties
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tekstwatermerk met specifieke opties aan uw Word-documenten kunt toevoegen met Aspose.Words voor .NET. Pas het lettertype, de grootte, de kleur en de lay-out eenvoudig aan.
type: docs
weight: 10
url: /nl/net/programming-with-watermark/add-text-watermark-with-specific-options/
---
## Invoering

Watermerken kunnen een stijlvolle en functionele toevoeging zijn aan uw Word-documenten, van het markeren van documenten als vertrouwelijk tot het toevoegen van een persoonlijk tintje. In deze zelfstudie onderzoeken we hoe u een tekstwatermerk aan een Word-document kunt toevoegen met Aspose.Words voor .NET. We gaan dieper in op de specifieke opties die u kunt configureren, zoals lettertypefamilie, lettergrootte, kleur en lay-out. Tegen het einde kunt u het watermerk van uw document aanpassen aan uw exacte behoeften. Dus pak je code-editor en laten we aan de slag gaan!

## Vereisten

Voordat we aan de slag gaan, moet u ervoor zorgen dat u over het volgende beschikt:

1.  Aspose.Words voor .NET-bibliotheek: de Aspose.Words-bibliotheek moet zijn geïnstalleerd. Als u dit nog niet heeft gedaan, kunt u het downloaden via de[Aspose.Words downloadlink](https://releases.aspose.com/words/net/).
2. Basiskennis van C#: In deze tutorial wordt C# als programmeertaal gebruikt. Een fundamenteel begrip van de C#-syntaxis zal nuttig zijn.
3. .NET-ontwikkelomgeving: Zorg ervoor dat u een ontwikkelomgeving hebt ingesteld (zoals Visual Studio) waar u uw .NET-applicaties kunt maken en uitvoeren.

## Naamruimten importeren

Om met Aspose.Words te kunnen werken, moet u de benodigde naamruimten in uw project opnemen. Dit is wat u moet importeren:

```csharp
using Aspose.Words;
using Aspose.Words.Rendering;
using System.Drawing;
```

## Stap 1: Stel uw document in

 Eerst moet u het document laden waarmee u wilt werken. Voor deze zelfstudie gebruiken we een voorbeelddocument met de naam`Document.docx`. Zorg ervoor dat dit document in de door u opgegeven directory aanwezig is.

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

 In deze stap definieert u de map waarin uw document zich bevindt en laadt u deze in een exemplaar van het`Document` klas.

## Stap 2: Configureer watermerkopties

Configureer vervolgens de opties voor uw tekstwatermerk. U kunt verschillende aspecten aanpassen, zoals de lettertypefamilie, de lettergrootte, de kleur en de lay-out. Laten we deze opties instellen.

```csharp
TextWatermarkOptions options = new TextWatermarkOptions()
{
    FontFamily = "Arial",
    FontSize = 36,
    Color = Color.Black,
    Layout = WatermarkLayout.Horizontal,
    IsSemitrasparent = false
};
```

Dit is wat elke optie doet:
- `FontFamily`: specificeert het lettertype van de watermerktekst.
- `FontSize`: stelt de grootte van de watermerktekst in.
- `Color`: definieert de kleur van de watermerktekst.
- `Layout`bepaalt de richting van het watermerk (horizontaal of diagonaal).
- `IsSemitrasparent`: Stelt in of het watermerk semi-transparant is.

## Stap 3: Voeg de watermerktekst toe

Pas nu het watermerk op uw document toe met behulp van de eerder geconfigureerde opties. In deze stap stelt u de watermerktekst in op 'Test' en past u de opties toe die u hebt gedefinieerd.

```csharp
doc.Watermark.SetText("Test", options);
```

Deze coderegel voegt het watermerk met de tekst "Test" toe aan het document, waarbij de opgegeven opties worden toegepast.

## Stap 4: Sla het document op

Sla ten slotte het document op met het nieuwe watermerk toegepast. U kunt het onder een nieuwe naam opslaan om te voorkomen dat u het originele document overschrijft.

```csharp
doc.Save(dataDir + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
```

Dit codefragment slaat het gewijzigde document op in dezelfde map met een nieuwe bestandsnaam.

## Conclusie

Het toevoegen van een tekstwatermerk aan uw Word-documenten met Aspose.Words voor .NET is een eenvoudig proces als u het opsplitst in beheersbare stappen. Door deze zelfstudie te volgen, heeft u geleerd hoe u verschillende watermerkopties kunt configureren, waaronder lettertype, grootte, kleur, lay-out en transparantie. Met deze vaardigheden kunt u uw documenten nu aanpassen zodat ze beter aan uw behoeften voldoen of essentiële informatie bevatten, zoals vertrouwelijkheid of branding.

 Als u vragen heeft of meer hulp nodig heeft, neem dan gerust een kijkje op de[Aspose.Words-documentatie](https://reference.aspose.com/words/net/) of bezoek de[Aspose-ondersteuningsforum](https://forum.aspose.com/c/words/8) voor meer hulp.

## Veelgestelde vragen

### Kan ik verschillende lettertypen gebruiken voor het watermerk?

 Ja, u kunt elk lettertype kiezen dat op uw systeem is geïnstalleerd door het`FontFamily` eigendom in de`TextWatermarkOptions`.

### Hoe wijzig ik de kleur van het watermerk?

 U kunt de kleur van het watermerk wijzigen door de`Color` eigendom in de`TextWatermarkOptions` aan wie dan ook`System.Drawing.Color` waarde.

### Is het mogelijk om meerdere watermerken aan een document toe te voegen?

Aspose.Words ondersteunt het toevoegen van één watermerk tegelijk. Als u meerdere watermerken wilt toevoegen, moet u ze opeenvolgend maken en toepassen.

### Kan ik de positie van het watermerk aanpassen?

 De`WatermarkLayout`eigenschap bepaalt de oriëntatie, maar nauwkeurige positioneringsaanpassingen worden niet direct ondersteund. Mogelijk moet u andere technieken gebruiken voor de exacte plaatsing.

### Wat moet ik doen als ik een semi-transparant watermerk nodig heb?

 Stel de`IsSemitrasparent`eigendom aan`true` om uw watermerk semi-transparant te maken.