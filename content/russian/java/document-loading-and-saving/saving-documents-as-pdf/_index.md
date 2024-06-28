---
title: Сохранение документов в формате PDF в Aspose.Words для Java
linktitle: Сохранение документов в формате PDF
second_title: API обработки Java-документов Aspose.Words
description: Узнайте, как сохранять документы Word в формате PDF с помощью Aspose.Words для Java. Настраивайте шрифты, свойства и качество изображения. Полное руководство по конвертации PDF.
type: docs
weight: 22
url: /ru/java/document-loading-and-saving/saving-documents-as-pdf/
---

## Введение в сохранение документов в формате PDF в Aspose.Words для Java

В этом пошаговом руководстве мы рассмотрим, как сохранять документы в формате PDF с помощью Aspose.Words для Java. Мы рассмотрим различные аспекты преобразования PDF-файлов и предоставим примеры кода, чтобы упростить этот процесс.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

- В вашей системе установлен Java Development Kit (JDK).
-  Библиотека Aspose.Words для Java. Вы можете скачать его с[здесь](https://releases.aspose.com/words/java/).

## Преобразование документа в PDF

Чтобы преобразовать документ Word в PDF, вы можете использовать следующий фрагмент кода:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Заменять`"input.docx"` с путем к вашему документу Word и`"output.pdf"` с желаемым путем к выходному PDF-файлу.

## Управление параметрами сохранения PDF

 Вы можете управлять различными параметрами сохранения PDF с помощью`PdfSaveOptions` класс. Например, вы можете установить отображаемый заголовок для PDF-документа следующим образом:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## Встраивание шрифтов в PDF

Чтобы встроить шрифты в созданный PDF-файл, используйте следующий код:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## Настройка свойств документа

Вы можете настроить свойства документа в созданном PDF-файле. Например:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## Экспорт структуры документа

 Чтобы экспортировать структуру документа, установите`exportDocumentStructure` возможность`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## Сжатие изображения

Вы можете управлять сжатием изображений, используя следующий код:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## Обновить последнее напечатанное свойство

Чтобы обновить свойство «Последняя печать» в PDF-файле, используйте:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## Рендеринг DML 3D-эффектов

Для расширенного рендеринга 3D-эффектов DML установите режим рендеринга:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## Интерполяция изображений

Вы можете включить интерполяцию изображения, чтобы улучшить качество изображения:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## Заключение

Aspose.Words for Java предоставляет комплексные возможности для преобразования документов Word в формат PDF с гибкостью и возможностями настройки. Вы можете управлять различными аспектами вывода PDF, включая шрифты, свойства документа, сжатие изображений и многое другое.

## Часто задаваемые вопросы

### Как преобразовать документ Word в PDF с помощью Aspose.Words для Java?

Чтобы преобразовать документ Word в PDF, используйте следующий код:

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

 Заменять`"input.docx"` с путем к вашему документу Word и`"output.pdf"` с желаемым путем к выходному PDF-файлу.

### Могу ли я встроить шрифты в PDF-файл, созданный Aspose.Words для Java?

 Да, вы можете вставлять шрифты в PDF, установив`setEmbedFullFonts` возможность`true` в`PdfSaveOptions`. Вот пример:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### Как настроить свойства документа в созданном PDF-файле?

 Вы можете настроить свойства документа в PDF с помощью`setCustomPropertiesExport` вариант в`PdfSaveOptions`. Например:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Какова цель сжатия изображений в Aspose.Words для Java?

 Сжатие изображений позволяет контролировать качество и размер изображений в создаваемом PDF-файле. Вы можете установить режим сжатия изображения, используя`setImageCompression` в`PdfSaveOptions`.

### Как обновить свойство «Последняя печать» в PDF-файле?

 Вы можете обновить свойство «Последняя печать» в PDF-файле, установив`setUpdateLastPrintedProperty` к`true` в`PdfSaveOptions`. Это будет отражать дату последней печати в метаданных PDF.

### Как улучшить качество изображения при конвертации в PDF?

 Чтобы улучшить качество изображения, включите интерполяцию изображения, установив`setInterpolateImages` к`true` в`PdfSaveOptions`. Это приведет к более плавному и качественному изображению в формате PDF.