---
title: Używanie kształtów dokumentów w Aspose.Words dla Java
linktitle: Korzystanie z kształtów dokumentów
second_title: Aspose.Words API przetwarzania dokumentów Java
description: Odblokuj moc kształtów dokumentów w Aspose.Words dla Java. Naucz się tworzyć atrakcyjne wizualnie dokumenty na podstawie przykładów krok po kroku.
type: docs
weight: 14
url: /pl/java/document-conversion-and-export/using-document-shapes/
---

## Wprowadzenie do używania kształtów dokumentów w Aspose.Words dla Java

tym obszernym przewodniku zagłębimy się w świat kształtów dokumentów w Aspose.Words dla Java. Kształty są niezbędnymi elementami podczas tworzenia atrakcyjnych wizualnie i interaktywnych dokumentów. Niezależnie od tego, czy chcesz dodać objaśnienia, przyciski, obrazy czy znaki wodne, Aspose.Words dla Java zapewnia narzędzia, które pozwalają to efektywnie zrobić. Przyjrzyjmy się krok po kroku, jak korzystać z tych kształtów, korzystając z przykładów kodu źródłowego.

## Pierwsze kroki z kształtami dokumentów

 Zanim przejdziemy do kodu, skonfigurujmy nasze środowisko. Upewnij się, że w Twoim projekcie znajduje się Aspose.Words for Java. Jeśli jeszcze tego nie zrobiłeś, możesz pobrać go ze strony internetowej Aspose[Pobierz Aspose.Words dla Javy](https://releases.aspose.com/words/java/)

## Dodawanie kształtów do dokumentów

### Wstawianie GroupShape

 A`GroupShape` pozwala grupować wiele kształtów razem. Oto jak możesz utworzyć i wstawić plik`GroupShape`:

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

### Wstawianie kształtu pola tekstowego

 Aby wstawić kształt pola tekstowego, możesz użyć opcji`insertShape` sposób pokazany w poniższym przykładzie:

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

## Manipulowanie właściwościami kształtu

### Zarządzanie współczynnikiem proporcji

Możesz kontrolować, czy współczynnik proporcji kształtu jest zablokowany, czy nie. Oto jak odblokować proporcje kształtu:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Umieszczanie kształtu w komórce tabeli

Jeśli chcesz umieścić kształt w komórce tabeli, możesz to osiągnąć za pomocą następującego kodu:

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
watermark.isLayoutInCell(true); // Wyświetl kształt poza komórką tabeli, jeśli zostanie on umieszczony w komórce.
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

## Praca z kształtami SmartArt

### Wykrywanie kształtów SmartArt

Kształty SmartArt można wykryć w dokumencie za pomocą następującego kodu:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### Aktualizowanie rysunków SmartArt

Aby zaktualizować rysunki SmartArt w dokumencie, użyj następującego kodu:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## Wniosek

W tym przewodniku poznaliśmy świat kształtów dokumentów w Aspose.Words dla Java. Wiesz już, jak dodawać różne kształty do dokumentów, manipulować ich właściwościami i pracować z kształtami SmartArt. Dzięki tej wiedzy możesz z łatwością tworzyć atrakcyjne wizualnie i interaktywne dokumenty.

## Często zadawane pytania

### Co to jest Aspose.Words dla Java?

Aspose.Words for Java to biblioteka Java, która umożliwia programistom programowe tworzenie, modyfikowanie i konwertowanie dokumentów programu Word. Zapewnia szeroką gamę funkcji i narzędzi do pracy z dokumentami w różnych formatach.

### Jak mogę pobrać Aspose.Words dla Java?

 Możesz pobrać Aspose.Words dla Java ze strony internetowej Aspose, klikając ten link:[Pobierz Aspose.Words dla Javy](https://releases.aspose.com/words/java/)

### Jakie są korzyści z używania kształtów dokumentów?

Kształty dokumentów dodają elementy wizualne i interaktywność do dokumentów, czyniąc je bardziej wciągającymi i pouczającymi. Dzięki kształtom możesz tworzyć objaśnienia, przyciski, obrazy, znaki wodne i nie tylko, poprawiając ogólne wrażenia użytkownika.

### Czy mogę dostosować wygląd kształtów?

Tak, możesz dostosować wygląd kształtów, dostosowując ich właściwości, takie jak rozmiar, położenie, obrót i kolor wypełnienia. Aspose.Words dla Java zapewnia rozbudowane opcje dostosowywania kształtu.

### Czy Aspose.Words dla Java jest kompatybilny z SmartArt?

Tak, Aspose.Words for Java obsługuje kształty SmartArt, umożliwiając pracę ze złożonymi diagramami i grafiką w dokumentach.