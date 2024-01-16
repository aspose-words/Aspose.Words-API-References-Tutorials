---
title: Inline-afbeelding invoegen in Word-document
linktitle: Inline-afbeelding invoegen in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u inline afbeeldingen in Word-documenten invoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/add-content-using-documentbuilder/insert-inline-image/
---
In deze uitgebreide zelfstudie leert u hoe u inline-afbeeldingen invoegt in een Word-document met behulp van Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u afbeeldingen rechtstreeks aan de tekst van uw documenten toevoegen.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een nieuw document en DocumentBuilder
Maak om te beginnen een nieuw document met behulp van de klasse Document en initialiseer een DocumentBuilder-object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg een inlineafbeelding in
Gebruik vervolgens de InsertImage-methode van de DocumentBuilder-klasse om een inline-afbeelding in het document in te voegen. Geef het afbeeldingsbestandspad op als parameter:

```csharp
builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## Stap 3: Sla het document op
Nadat u de inline-afbeelding hebt ingevoegd, slaat u het document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

### Voorbeeldbroncode voor inline-afbeelding invoegen met Aspose.Words voor .NET
Hier is de volledige broncode voor het invoegen van een inline-afbeelding met Aspose.Words voor .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertImage(ImagesDir + "Transparent background logo.png");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u inline-afbeeldingen in een Word-document kunt invoegen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu naadloos afbeeldingen toevoegen aan de tekst van uw documenten.

Inline-afbeeldingen zijn handig voor verschillende scenario's, zoals het rechtstreeks toevoegen van illustraties, logo's of andere visuele elementen aan de stroom van het document.

### Veelgestelde vragen over het invoegen van een inline-afbeelding in een Word-document

#### Vraag: Kan ik het formaat van de inline afbeeldingen in het Word-document wijzigen?

A: Ja, u kunt het formaat van de inline afbeeldingen wijzigen met Aspose.Words voor .NET. Nadat u de afbeelding hebt ingevoegd, kunt u de grootte ervan manipuleren door de breedte- en hoogte-eigenschappen aan te passen van het Shape-object dat de afbeelding vertegenwoordigt.

#### Vraag: Is het mogelijk om alternatieve tekst toe te voegen aan inline afbeeldingen voor toegankelijkheidsdoeleinden?

A: Ja, u kunt alternatieve tekst toevoegen aan inline afbeeldingen om de toegankelijkheid te verbeteren. Aspose.Words voor .NET ondersteunt de toevoeging van alternatieve tekst aan afbeeldingen, waardoor schermlezers en andere ondersteunende technologieën de afbeeldingsinhoud kunnen beschrijven voor visueel gehandicapte gebruikers.

#### Vraag: Kan ik opmaak of stijlen toepassen op de inline afbeeldingen?

EEN: Absoluut! Aspose.Words voor .NET biedt uitgebreide opmaakopties voor inline afbeeldingen. U kunt verschillende stijlen, randen, effecten en andere opmaakkenmerken op de afbeeldingen toepassen, zodat deze overeenkomen met het visuele ontwerp van uw document.

#### Vraag: Ondersteunt Aspose.Words voor .NET het invoegen van afbeeldingen uit een stream- of byte-array?

A: Ja, u kunt inline afbeeldingen uit streams of byte-arrays invoegen met Aspose.Words voor .NET. Hierdoor kunt u werken met afbeeldingen die zijn geladen vanuit externe bronnen of met dynamisch gegenereerde afbeeldingen.

#### Vraag: Kan ik afbeeldingen op specifieke posities in de tekstinhoud invoegen?

A: Ja, de klasse DocumentBuilder in Aspose.Words voor .NET biedt nauwkeurige controle over de invoegpositie van inline afbeeldingen. U kunt binnen de tekst de exacte locatie opgeven waar de afbeelding moet worden ingevoegd.