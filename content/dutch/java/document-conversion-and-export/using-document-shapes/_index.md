---
title: Documentvormen gebruiken in Aspose.Words voor Java
linktitle: Documentvormen gebruiken
second_title: Aspose.Words Java-documentverwerkings-API
description: Ontgrendel de kracht van documentvormen in Aspose.Words voor Java. Leer visueel aantrekkelijke documenten te maken met stapsgewijze voorbeelden.
type: docs
weight: 14
url: /nl/java/document-conversion-and-export/using-document-shapes/
---

## Inleiding tot het gebruik van documentvormen in Aspose.Words voor Java

In deze uitgebreide handleiding duiken we in de wereld van documentvormen in Aspose.Words voor Java. Vormen zijn essentiële elementen als het gaat om het creëren van visueel aantrekkelijke en interactieve documenten. Of u nu toelichtingen, knoppen, afbeeldingen of watermerken moet toevoegen, Aspose.Words voor Java biedt de hulpmiddelen om dit efficiënt te doen. Laten we stap voor stap bekijken hoe u deze vormen kunt gebruiken met broncodevoorbeelden.

## Aan de slag met documentvormen

 Voordat we in de code duiken, gaan we eerst onze omgeving instellen. Zorg ervoor dat Aspose.Words voor Java in uw project is geïntegreerd. Als u dat nog niet heeft gedaan, kunt u het downloaden van de Aspose-website[Download Aspose.Words voor Java](https://releases.aspose.com/words/java/)

## Vormen aan documenten toevoegen

### Een groepsvorm invoegen

 A`GroupShape` Hiermee kunt u meerdere vormen groeperen. Zo kunt u een`GroupShape`:

```java
Document doc = new Document();
doc.ensureMinimum();

GroupShape groupShape = new GroupShape(doc);
Shape accentBorderShape = new Shape(doc, ShapeType.ACCENT_BORDER_CALLOUT_1);
accentBorderShape.setWidth(100.0);
accentBorderShape.setHeight(100.0);

groupShape.appendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ACTION_BUTTON_BEGINNING);
actionButtonShape.setLeft(100.0);
actionButtonShape.setWidth(100.0);
actionButtonShape.setHeight(200.0);

groupShape.appendChild(actionButtonShape);

groupShape.setWidth(200.0);
groupShape.setHeight(200.0);
groupShape.setCoordSize(new Dimension(200, 200));

DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertNode(groupShape);

doc.save("Your Directory Path" + "WorkingWithShapes.AddGroupShape.docx");
```

### Een tekstvakvorm invoegen

 Om een tekstvakvorm in te voegen, kunt u de`insertShape` methode zoals weergegeven in het onderstaande voorbeeld:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertShape(ShapeType.TEXT_BOX, RelativeHorizontalPosition.PAGE, 100.0,
    RelativeVerticalPosition.PAGE, 100.0, 50.0, 50.0, WrapType.NONE);

shape.setRotation(30.0);
builder.writeln();

shape = builder.insertShape(ShapeType.TEXT_BOX, 50.0, 50.0);
shape.setRotation(30.0);

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.DOCX);
saveOptions.setCompliance(OoxmlCompliance.ISO_29500_2008_TRANSITIONAL);

doc.save("Your Directory Path" + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

## Vormeigenschappen manipuleren

### Beeldverhouding beheren

U kunt bepalen of de beeldverhouding van een vorm is vergrendeld of niet. U kunt als volgt de beeldverhouding van een vorm ontgrendelen:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Een vorm in een tabelcel plaatsen

Als u een vorm in een tabelcel moet plaatsen, kunt u dit bereiken met de volgende code:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.startTable();
builder.getRowFormat().setHeight(100.0);
builder.getRowFormat().setHeightRule(HeightRule.EXACTLY);

for (int i = 0; i < 31; i++) {
    if (i != 0 && i % 7 == 0)
        builder.endRow();

    builder.insertCell();
    builder.write("Cell contents");
}

builder.endTable();

Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
watermark.isLayoutInCell(true); // Geef de vorm buiten de tabelcel weer als deze in een cel wordt geplaatst.
watermark.setWidth(300.0);
watermark.setHeight(70.0);
watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);
watermark.setVerticalAlignment(VerticalAlignment.CENTER);
watermark.setRotation(-40);
watermark.setFillColor(Color.GRAY);
watermark.setStrokeColor(Color.GRAY);
watermark.getTextPath().setText("watermarkText");
watermark.getTextPath().setFontFamily("Arial");
watermark.setName("WaterMark_{Guid.NewGuid()}");
watermark.setWrapType(WrapType.NONE);

Run run = (Run) doc.getChildNodes(NodeType.RUN, true).get(doc.getChildNodes(NodeType.RUN, true).getCount() - 1);
builder.moveTo(run);
builder.insertNode(watermark);

doc.getCompatibilityOptions().optimizeFor(MsWordVersion.WORD_2010);
doc.save("Your Directory Path" + "WorkingWithShapes.LayoutInCell.docx");
```

## Werken met SmartArt-vormen

### SmartArt-vormen detecteren

U kunt SmartArt-vormen in een document detecteren met behulp van de volgende code:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### SmartArt-tekeningen bijwerken

Gebruik de volgende code om SmartArt-tekeningen binnen een document bij te werken:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## Conclusie

In deze handleiding hebben we de wereld van documentvormen in Aspose.Words voor Java verkend. U hebt geleerd hoe u verschillende vormen aan uw documenten kunt toevoegen, de eigenschappen ervan kunt manipuleren en met SmartArt-vormen kunt werken. Met deze kennis kunt u eenvoudig visueel aantrekkelijke en interactieve documenten maken.

## Veelgestelde vragen

### Wat is Aspose.Words voor Java?

Aspose.Words voor Java is een Java-bibliotheek waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, wijzigen en converteren. Het biedt een breed scala aan functies en hulpmiddelen voor het werken met documenten in verschillende formaten.

### Hoe kan ik Aspose.Words voor Java downloaden?

 U kunt Aspose.Words voor Java downloaden van de Aspose-website door deze link te volgen:[Download Aspose.Words voor Java](https://releases.aspose.com/words/java/)

### Wat zijn de voordelen van het gebruik van documentvormen?

Documentvormen voegen visuele elementen en interactiviteit toe aan uw documenten, waardoor ze aantrekkelijker en informatiever worden. Met vormen kunt u toelichtingen, knoppen, afbeeldingen, watermerken en meer maken, waardoor de algehele gebruikerservaring wordt verbeterd.

### Kan ik het uiterlijk van vormen aanpassen?

Ja, u kunt het uiterlijk van vormen aanpassen door hun eigenschappen aan te passen, zoals grootte, positie, rotatie en vulkleur. Aspose.Words voor Java biedt uitgebreide mogelijkheden voor vormaanpassing.

### Is Aspose.Words voor Java compatibel met SmartArt?

Ja, Aspose.Words voor Java ondersteunt SmartArt-vormen, waardoor u met complexe diagrammen en afbeeldingen in uw documenten kunt werken.