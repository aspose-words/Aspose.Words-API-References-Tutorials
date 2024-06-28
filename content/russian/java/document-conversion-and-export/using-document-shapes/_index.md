---
title: Использование фигур документов в Aspose.Words для Java
linktitle: Использование фигур документа
second_title: API обработки Java-документов Aspose.Words
description: Раскройте возможности форм документов в Aspose.Words для Java. Научитесь создавать визуально привлекательные документы с помощью пошаговых примеров.
type: docs
weight: 14
url: /ru/java/document-conversion-and-export/using-document-shapes/
---

## Введение в использование фигур документов в Aspose.Words для Java

В этом подробном руководстве мы углубимся в мир форм документов в Aspose.Words для Java. Формы являются важными элементами при создании визуально интересных и интерактивных документов. Если вам нужно добавить выноски, кнопки, изображения или водяные знаки, Aspose.Words for Java предоставит инструменты для эффективного выполнения этого. Давайте шаг за шагом рассмотрим, как использовать эти фигуры, на примерах исходного кода.

## Начало работы с фигурами документов

 Прежде чем мы перейдем к коду, давайте настроим нашу среду. Убедитесь, что Aspose.Words для Java интегрирован в ваш проект. Если вы еще этого не сделали, вы можете скачать его с сайта Aspose.[Скачать Aspose.Words для Java](https://releases.aspose.com/words/java/)

## Добавление фигур в документы

### Вставка GroupShape

 А`GroupShape` Позволяет группировать несколько фигур вместе. Вот как вы можете создать и вставить`GroupShape`:

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

### Вставка формы текстового поля

 Чтобы вставить форму текстового поля, вы можете использовать`insertShape` метод, как показано в примере ниже:

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

## Управление свойствами формы

### Управление соотношением сторон

Вы можете контролировать, заблокировано ли соотношение сторон фигуры или нет. Вот как разблокировать соотношение сторон фигуры:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape shape = builder.insertImage(getImagesDir() + "Transparent background logo.png");
shape.setAspectRatioLocked(false);

doc.save("Your Directory Path" + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Размещение фигуры в ячейке таблицы

Если вам нужно поместить фигуру внутри ячейки таблицы, вы можете добиться этого с помощью следующего кода:

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
watermark.isLayoutInCell(true); // Отобразите фигуру за пределами ячейки таблицы, если она будет помещена в ячейку.
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

## Работа с фигурами SmartArt

### Обнаружение фигур SmartArt

Вы можете обнаружить фигуры SmartArt в документе, используя следующий код:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
List<Shape> shapes = IterableUtils.toList(doc.getChildNodes(NodeType.SHAPE, true));
int count = (int) shapes.stream().filter(s -> s.hasSmartArt()).count();
System.out.println("The document has " + count + " shapes with SmartArt.");
```

### Обновление рисунков SmartArt

Чтобы обновить рисунки SmartArt в документе, используйте следующий код:

```java
Document doc = new Document("Your Directory Path" + "SmartArt.docx");
for (Shape shape : (Iterable<Shape>) doc.getChildNodes(NodeType.SHAPE, true)) {
    if (shape.hasSmartArt())
        shape.updateSmartArtDrawing();
}
```

## Заключение

В этом руководстве мы изучили мир форм документов в Aspose.Words для Java. Вы научились добавлять в документы различные фигуры, управлять их свойствами и работать с фигурами SmartArt. Обладая этими знаниями, вы сможете с легкостью создавать визуально интересные и интерактивные документы.

## Часто задаваемые вопросы

### Что такое Aspose.Words для Java?

Aspose.Words for Java — это библиотека Java, которая позволяет разработчикам программно создавать, изменять и конвертировать документы Word. Он предоставляет широкий набор функций и инструментов для работы с документами различных форматов.

### Как я могу скачать Aspose.Words для Java?

 Вы можете скачать Aspose.Words для Java с сайта Aspose, перейдя по этой ссылке:[Скачать Aspose.Words для Java](https://releases.aspose.com/words/java/)

### Каковы преимущества использования фигур документов?

Формы документов добавляют визуальные элементы и интерактивность вашим документам, делая их более привлекательными и информативными. С помощью фигур вы можете создавать звонки, кнопки, изображения, водяные знаки и многое другое, улучшая общее взаимодействие с пользователем.

### Могу ли я настроить внешний вид фигур?

Да, вы можете настроить внешний вид фигур, настроив их свойства, такие как размер, положение, поворот и цвет заливки. Aspose.Words для Java предоставляет широкие возможности настройки фигур.

### Совместим ли Aspose.Words для Java со SmartArt?

Да, Aspose.Words for Java поддерживает фигуры SmartArt, что позволяет вам работать со сложными диаграммами и графикой в ваших документах.