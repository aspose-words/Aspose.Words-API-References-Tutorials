---
title: Watermerken gebruiken voor documenten in Aspose.Words voor Java
linktitle: Watermerken gebruiken voor documenten
second_title: Aspose.Words Java-documentverwerkings-API
description: Leer hoe u watermerken aan documenten toevoegt in Aspose.Words voor Java. Pas tekst- en afbeeldingswatermerken aan voor professioneel ogende documenten.
type: docs
weight: 15
url: /nl/java/document-conversion-and-export/using-watermarks-to-documents/
---

## Inleiding tot het toevoegen van watermerken aan documenten in Aspose.Words voor Java

In deze zelfstudie onderzoeken we hoe u watermerken aan documenten kunt toevoegen met behulp van de Aspose.Words voor Java API. Watermerken zijn een handige manier om documenten te labelen met tekst of afbeeldingen om hun status, vertrouwelijkheid of andere relevante informatie aan te geven. In deze handleiding behandelen we zowel tekst- als afbeeldingswatermerken.

## Aspose.Words instellen voor Java

Voordat we watermerken aan documenten gaan toevoegen, moeten we Aspose.Words voor Java instellen. Volg deze stappen om aan de slag te gaan:

1.  Download Aspose.Words voor Java van[hier](https://releases.aspose.com/words/java/).
2. Voeg de Aspose.Words voor Java-bibliotheek toe aan uw Java-project.
3. Importeer de benodigde klassen in uw Java-code.

Nu we de bibliotheek hebben ingesteld, gaan we verder met het toevoegen van watermerken.

## Tekstwatermerken toevoegen

Tekstwatermerken zijn een gebruikelijke keuze als u tekstuele informatie aan uw documenten wilt toevoegen. Zo kunt u een tekstwatermerk toevoegen met Aspose.Words voor Java:

```java
//Maak een documentinstantie
Document doc = new Document("Document.docx");

// Definieer TextWatermarkOptions
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// Stel de watermerktekst en opties in
doc.getWatermark().setText("Test", options);

// Sla het document op met het watermerk
doc.save("DocumentWithWatermark.docx");
```

## Afbeeldingswatermerken toevoegen

Naast tekstwatermerken kunt u ook afbeeldingswatermerken aan uw documenten toevoegen. Zo voegt u een afbeeldingswatermerk toe:

```java
//Maak een documentinstantie
Document doc = new Document("Document.docx");

// Laad de afbeelding voor het watermerk
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// Stel de grootte en positie van het watermerk in
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// Voeg het watermerk toe aan het document
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Sla het document op met het watermerk
doc.save("DocumentWithImageWatermark.docx");
```

## Watermerken aanpassen

U kunt watermerken aanpassen door het uiterlijk en de positie ervan aan te passen. Voor tekstwatermerken kunt u het lettertype, de grootte, de kleur en de lay-out wijzigen. Voor afbeeldingswatermerken kunt u hun grootte en positie wijzigen, zoals aangetoond in de vorige voorbeelden.

## Watermerken verwijderen

Om watermerken uit een document te verwijderen, kunt u de volgende code gebruiken:

```java
//Maak een documentinstantie
Document doc = new Document("DocumentWithWatermark.docx");

// Verwijder het watermerk
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// Sla het document op zonder watermerk
doc.save("DocumentWithoutWatermark.docx");
```


## Conclusie

In deze zelfstudie hebben we geleerd hoe u watermerken aan documenten kunt toevoegen met Aspose.Words voor Java. Of u nu tekst- of afbeeldingswatermerken moet toevoegen, Aspose.Words biedt de tools om deze efficiënt aan te passen en te beheren. U kunt ook watermerken verwijderen wanneer ze niet langer nodig zijn, zodat uw documenten er schoon en professioneel uitzien.

## Veelgestelde vragen

### Hoe kan ik het lettertype van een tekstwatermerk wijzigen?

 Als u het lettertype van een tekstwatermerk wilt wijzigen, wijzigt u het`setFontFamily` eigendom in de`TextWatermarkOptions`. Bijvoorbeeld:

```java
options.setFontFamily("Times New Roman");
```

### Kan ik meerdere watermerken aan één document toevoegen?

 Ja, u kunt meerdere watermerken aan een document toevoegen door er meerdere te maken`Shape` objecten met verschillende instellingen en deze aan het document toevoegen.

### Is het mogelijk om een watermerk te roteren?

 Ja, u kunt een watermerk roteren door de`setRotation` eigendom in de`Shape` voorwerp. Positieve waarden draaien het watermerk met de klok mee, en negatieve waarden draaien het tegen de klok in.

### Hoe kan ik een watermerk semi-transparant maken?

 Om een watermerk semi-transparant te maken, stelt u de`setSemitransparent`eigendom aan`true` in de`TextWatermarkOptions`.

### Kan ik watermerken toevoegen aan specifieke secties van een document?

Ja, u kunt watermerken toevoegen aan specifieke secties van een document door de secties te doorlopen en het watermerk aan de gewenste secties toe te voegen.