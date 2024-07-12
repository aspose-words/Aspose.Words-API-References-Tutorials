---
title: Afbeelding
linktitle: Afbeelding
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een afbeelding kunt invoegen en aanpassen met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/image/
---

In dit voorbeeld leggen we uit hoe u de afbeeldingsfunctie gebruikt met Aspose.Words voor .NET. Met afbeeldingen kunt u illustraties en afbeeldingen in een document invoegen.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Een afbeelding invoegen

 We kunnen een afbeelding invoegen met behulp van de`Shape` klasse en specificeer hier het type afbeelding`ShapeType.Image` . We stellen ook het omlooptype van de afbeelding in`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## Stap 3: Afbeeldingsaanpassing

 We passen de afbeelding aan door bijvoorbeeld het volledige pad op te geven`"/attachment/1456/pic001.png"`en een titel aan de afbeelding toevoegen.

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Voorbeeldbroncode voor afbeeldingen met Aspose.Words voor .NET

```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

// Voeg afbeelding in.
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

Gefeliciteerd! U hebt nu geleerd hoe u de afbeeldingenfunctie kunt gebruiken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Hoe kan ik een afbeelding uit een lokaal bestand in Aspose.Words invoegen?

 A: Om een afbeelding uit een lokaal bestand in Aspose.Words in te voegen, kunt u de`Shape` klasse en de`InsertImage` methode.

#### Vraag: Kan ik een afbeelding van een URL in Aspose.Words invoegen?

 A: Ja, u kunt een afbeelding invoegen vanaf een URL in Aspose.Words. Je kunt hetzelfde gebruiken`InsertImage`methode en geef de afbeeldings-URL op in plaats van het lokale bestandspad.

#### Vraag: Hoe kan ik het formaat van een afbeelding wijzigen in Aspose.Words?

 A: Om het formaat van een afbeelding in Aspose.Words te wijzigen, kunt u de`Width`En`Height` eigenschappen van de`Shape` voorwerp.

#### Vraag: Kan ik filters toepassen op afbeeldingen in Aspose.Words?

 A: Ja, u kunt filters toepassen op afbeeldingen in Aspose.Words. U kunt bijvoorbeeld een vervagingsfilter op een afbeelding toepassen met behulp van de`ApplyGaussianBlur` werkwijze van de`Shape` voorwerp.

#### Vraag: Hoe kan ik de ene afbeelding vervangen door een andere in Aspose.Words?

 A: Om de ene afbeelding door een andere te vervangen in Aspose.Words, kunt u de`Replace` werkwijze van de`Shape` klas. Deze methode neemt als parameter de`Shape` object van de afbeelding die moet worden vervangen en de`Shape` object van de nieuwe afbeelding.