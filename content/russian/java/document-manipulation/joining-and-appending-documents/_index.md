---
title: Объединение и добавление документов в Aspose.Words для Java
linktitle: Объединение и добавление документов
second_title: API обработки Java-документов Aspose.Words
description: Узнайте, как легко объединять и добавлять документы с помощью Aspose.Words для Java. Сохраняйте форматирование, управляйте верхними и нижними колонтитулами и т. д.
type: docs
weight: 30
url: /ru/java/document-manipulation/joining-and-appending-documents/
---

## Введение в объединение и добавление документов в Aspose.Words для Java

В этом уроке мы рассмотрим, как объединять и добавлять документы с помощью библиотеки Aspose.Words для Java. Вы узнаете, как легко объединить несколько документов, сохраняя при этом форматирование и структуру.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что в вашем Java-проекте настроен Aspose.Words for Java API.

## Параметры объединения документов

### Простое добавление

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Добавить с параметрами формата импорта

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### Добавить в пустой документ

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Добавить с преобразованием номера страницы

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); // Преобразование полей NUMPAGES
dstDoc.updatePageLayout(); // Обновите макет страницы для правильной нумерации.
```

## Обработка различных настроек страницы

При добавлении документов с разными настройками страницы:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
// Убедитесь, что настройки страницы соответствуют целевому документу.
```

## Объединение документов с разными стилями

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## Умный стиль поведения

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## Вставка документов с помощью DocumentBuilder

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Сохранение нумерации источников

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Обработка текстовых полей

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## Управление верхними и нижними колонтитулами

### Связывание верхних и нижних колонтитулов

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### Отсоединение верхних и нижних колонтитулов

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## Заключение

Aspose.Words for Java предоставляет гибкие и мощные инструменты для объединения и добавления документов, независимо от того, нужно ли вам поддерживать форматирование, обрабатывать различные настройки страниц или управлять верхними и нижними колонтитулами. Поэкспериментируйте с этими методами, чтобы удовлетворить ваши конкретные потребности в обработке документов.

## Часто задаваемые вопросы

### Как можно легко объединить документы с разными стилями?

 Чтобы объединить документы с разными стилями, используйте`ImportFormatMode.USE_DESTINATION_STYLES` при добавлении.

### Могу ли я сохранить нумерацию страниц при добавлении документов?

 Да, вы можете сохранить нумерацию страниц, используя`convertNumPageFieldsToPageRef` метод и обновление макета страницы.

### Что такое умный стиль поведения?

 Функция Smart Style Behavior помогает поддерживать единообразие стилей при добавлении документов. Используйте его с`ImportFormatOptions` для лучших результатов.

### Как обрабатывать текстовые поля при добавлении документов?

Набор`importFormatOptions.setIgnoreTextBoxes(false)` для включения текстовых полей во время добавления.

### Что делать, если я хочу связать/отсоединить верхние и нижние колонтитулы между документами?

 Вы можете связать верхние и нижние колонтитулы с`linkToPrevious(true)` или отсоедините их от`linkToPrevious(false)` по мере необходимости.