---
title: Использование верхних и нижних колонтитулов в Aspose.Words для Java
linktitle: Использование верхних и нижних колонтитулов
second_title: API обработки Java-документов Aspose.Words
description: Узнайте шаг за шагом, как использовать верхние и нижние колонтитулы в Aspose.Words для Java. Создавайте профессиональные документы без особых усилий.
type: docs
weight: 16
url: /ru/java/using-document-elements/using-headers-and-footers/
---

В этом подробном руководстве мы познакомим вас с процессом работы с верхними и нижними колонтитулами в Aspose.Words для Java. Верхние и нижние колонтитулы являются важными элементами форматирования документов, и Aspose.Words предоставляет мощные инструменты для их создания и настройки в соответствии с вашими потребностями.

Теперь давайте подробно рассмотрим каждый из этих шагов.

## 1. Введение в Aspose.Words

Aspose.Words — это мощный Java API, который позволяет программно создавать, манипулировать и отображать документы Word. Он предоставляет обширные возможности для форматирования документов, включая верхние и нижние колонтитулы.

## 2. Настройка среды Java

 Прежде чем начать использовать Aspose.Words, убедитесь, что ваша среда разработки Java настроена правильно. Вы можете найти необходимые инструкции по настройке на странице документации Aspose.Words:[Документация Aspose.Words Java](https://reference.aspose.com/words/java/).

## 3.Создание нового документа

Для работы с верхними и нижними колонтитулами вам необходимо создать новый документ с помощью Aspose.Words. Следующий код демонстрирует, как это сделать:

```java
// Java-код для создания нового документа
string dataDir = "Your Document Directory";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 4. Понимание настройки страницы

 Настройка страницы имеет решающее значение для управления макетом вашего документа. Вы можете указать различные свойства, связанные с верхними и нижними колонтитулами, используя`PageSetup` класс. Например:

```java
// Настройка свойств страницы
Section currentSection = builder.getCurrentSection();
PageSetup pageSetup = currentSection.getPageSetup();
pageSetup.setDifferentFirstPageHeaderFooter(true);
pageSetup.setHeaderDistance(20.0);
```

## 5. Другой верхний/нижний колонтитул первой страницы

Aspose.Words позволяет вам иметь разные верхние и нижние колонтитулы для первой страницы вашего документа. Использовать`pageSetup.setDifferentFirstPageHeaderFooter(true);` чтобы включить эту функцию.

## 6. Работа с головами

### 6.1. Добавление текста в заголовки

 Вы можете добавить текст в заголовки, используя`DocumentBuilder`. Вот пример:

```java
// Добавление текста в заголовок первой страницы
builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
builder.getFont().setName("Arial");
builder.getFont().setBold(true);
builder.getFont().setSize(14.0);
builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
```

### 6.2. Вставка изображений в заголовки

 Чтобы вставить изображения в заголовки, вы можете использовать`insertImage` метод. Вот пример:

```java
// Вставка изображения в шапку
builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
    RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
```

### 6.3. Настройка стилей заголовка

Вы можете настроить стили заголовка, задав различные свойства, такие как шрифт, выравнивание и т. д., как показано в примерах выше.

## 7. Работа с нижними колонтитулами

### 7.1. Добавление текста в нижние колонтитулы

 Как и в случае с верхними колонтитулами, вы можете добавлять текст в нижние колонтитулы, используя`DocumentBuilder`. Вот пример:

```java
// Добавление текста в основной нижний колонтитул
builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
// Вставьте текст и поля по мере необходимости
```

### 7.2. Вставка изображений в нижние колонтитулы

 Чтобы вставить изображения в ступни, используйте команду`insertImage` метод, как и в заголовках.

### 7.3. Настройка стилей нижнего колонтитула

 Настройте стили нижнего колонтитула с помощью`DocumentBuilder`аналогично настройке заголовков.

## 8. Нумерация страниц

 Вы можете включать номера страниц в верхние и нижние колонтитулы, используя такие поля, как`PAGE` и`NUMPAGES`. Эти поля автоматически обновляются при добавлении или удалении страниц.

## 9. Информация об авторских правах в нижних колонтитулах.

Чтобы добавить информацию об авторских правах в нижний колонтитул вашего документа, вы можете использовать таблицу с двумя ячейками, выравнивая одну по левому краю, а другую по правому, как показано во фрагменте кода.

## 10. Работа с несколькими разделами

Aspose.Words позволяет работать с несколькими разделами документа. Вы можете установить различные настройки страницы и верхние/нижние колонтитулы для каждого раздела.

## 11. Альбомная ориентация

При необходимости вы можете изменить ориентацию отдельных разделов на альбомную.

## 12. Копирование верхних и нижних колонтитулов из предыдущих разделов.

Копирование верхних и нижних колонтитулов из предыдущих разделов может сэкономить время при создании сложных документов.

## 13. Сохраните свои документы

После создания и настройки документа не забудьте сохранить его, используя`doc.save()` метод.

## Полный исходный код
```java
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        Section currentSection = builder.getCurrentSection();
        PageSetup pageSetup = currentSection.getPageSetup();
        // Укажите, хотим ли мы, чтобы колонтитулы первой страницы отличались от других страниц.
        // Вы также можете использовать свойство PageSetup.OddAndEvenPagesHeaderFooter, чтобы указать
        // Различные верхние и нижние колонтитулы для нечетных и четных страниц.
        pageSetup.setDifferentFirstPageHeaderFooter(true);
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.CENTER);
        builder.getFont().setName("Arial");
        builder.getFont().setBold(true);
        builder.getFont().setSize(14.0);
        builder.write("Aspose.Words Header/Footer Creation Primer - Title Page.");
        pageSetup.setHeaderDistance(20.0);
        builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
        // Вставьте позиционированное изображение в верхний/левый угол заголовка.
        // Расстояние от верхнего/левого края страницы установлено в 10 пунктов.
        builder.insertImage(getImagesDir() + "Graphics Interchange Format.gif", RelativeHorizontalPosition.PAGE, 10.0,
            RelativeVerticalPosition.PAGE, 10.0, 50.0, 50.0, WrapType.THROUGH);
        builder.getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.write("Aspose.Words Header/Footer Creation Primer.");
        builder.moveToHeaderFooter(HeaderFooterType.FOOTER_PRIMARY);
        // Используем таблицу с двумя ячейками, чтобы вынести одну часть текста на строку (с нумерацией страниц).
        // Выровнять по левому краю, а оставшуюся часть текста (с учетом копирайта) по правому краю.
        builder.startTable();
        builder.getCellFormat().clearFormatting();
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        // Он использует поля PAGE и NUMPAGES для автоматического расчета номера текущей страницы и множества страниц.
        builder.write("Page ");
        builder.insertField("PAGE", "");
        builder.write(" of ");
        builder.insertField("NUMPAGES", "");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.LEFT);
        builder.insertCell();
        builder.getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        builder.write("(C) 2001 Aspose Pty Ltd. All rights reserved.");
        builder.getCurrentParagraph().getParagraphFormat().setAlignment(ParagraphAlignment.RIGHT);
        builder.endRow();
        builder.endTable();
        builder.moveToDocumentEnd();
        // Сделайте разрыв страницы, чтобы создать вторую страницу, на которой будут видны основные верхние и нижние колонтитулы.
        builder.insertBreak(BreakType.PAGE_BREAK);
        builder.insertBreak(BreakType.SECTION_BREAK_NEW_PAGE);
        currentSection = builder.getCurrentSection();
        pageSetup = currentSection.getPageSetup();
        pageSetup.setOrientation(Orientation.LANDSCAPE);
        // Для этого раздела не нужен отдельный верхний/нижний колонтитул на первой странице, нам нужна только одна титульная страница в документе.
        //а верхний/нижний колонтитул этой страницы уже определен в предыдущем разделе.
        pageSetup.setDifferentFirstPageHeaderFooter(false);
        // В этом разделе отображаются верхние и нижние колонтитулы из предыдущего раздела.
        // по умолчанию вызовите currentSection.HeadersFooters.LinkToPrevious(false), чтобы отменить эту ширину страницы
        // для нового раздела отличается, поэтому нам нужно установить разную ширину ячеек для таблицы нижнего колонтитула.
        currentSection.getHeadersFooters().linkToPrevious(false);
        // Если мы хотим использовать уже существующий набор верхнего/нижнего колонтитула для этого раздела.
        // Но с небольшими изменениями, возможно, будет целесообразно скопировать верхние/нижние колонтитулы.
        // Из предыдущего раздела и примените необходимые изменения там, где мы хотим.
        copyHeadersFootersFromPreviousSection(currentSection);
        HeaderFooter primaryFooter = currentSection.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
        Row row = primaryFooter.getTables().get(0).getFirstRow();
        row.getFirstCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 / 3));
        row.getLastCell().getCellFormat().setPreferredWidth(PreferredWidth.fromPercent(100 * 2 / 3));
        doc.save("Your Directory Path" + "WorkingWithHeadersAndFooters.CreateHeaderFooter.docx");
```	
Исходный код метода copyHeadersFootersFromPreviousSection
```java
    /// <сводка>
    /// Клонирует и копирует верхние и нижние колонтитулы из предыдущего раздела в указанный раздел.
    /// </сводка>
    private void copyHeadersFootersFromPreviousSection(Section section)
    {
        Section previousSection = (Section)section.getPreviousSibling();
        if (previousSection == null)
            return;
        section.getHeadersFooters().clear();
        for (HeaderFooter headerFooter : (Iterable<HeaderFooter>) previousSection.getHeadersFooters())
            section.getHeadersFooters().add(headerFooter.deepClone(true));
	}
```

## Заключение

В этом уроке мы рассмотрели основы работы с верхними и нижними колонтитулами в Aspose.Words для Java. Вы узнали, как создавать, настраивать и стилизовать верхние и нижние колонтитулы, а также другие важные методы форматирования документов.

 Более подробную информацию и расширенные функции см.[Документация Aspose.Words Java](https://reference.aspose.com/words/java/).

## Часто задаваемые вопросы

### 1. Как добавить номера страниц в нижний колонтитул документа?
 Вы можете добавить номера страниц, вставив`PAGE` поле в нижний колонтитул с помощью Aspose.Words.

### 2. Совместим ли Aspose.Words со средами разработки Java?
Да, Aspose.Words обеспечивает поддержку разработки на Java. Убедитесь, что у вас есть необходимые настройки.

### 3. Могу ли я настроить шрифт и стиль верхних и нижних колонтитулов?
Конечно, вы можете настроить шрифты, выравнивание и другие стили, чтобы сделать верхние и нижние колонтитулы визуально привлекательными.

### 4. Можно ли иметь разные заголовки для нечетных и четных страниц?
 Да, вы можете использовать`PageSetup.OddAndEvenPagesHeaderFooter` указать разные заголовки для нечетных и четных страниц.

### 5. Как мне начать работу с Aspose.Words для Java?
 Для начала посетите[Документация Aspose.Words Java](https://reference.aspose.com/words/java/) для получения подробного руководства по использованию API.