---
title: Сохранение документов в виде текстовых файлов в Aspose.Words для Java
linktitle: Сохранение документов в виде текстовых файлов
second_title: API обработки Java-документов Aspose.Words
description: Узнайте, как сохранять документы в виде текстовых файлов в Aspose.Words для Java. Следуйте нашему пошаговому руководству с примерами кода Java.
type: docs
weight: 24
url: /ru/java/document-loading-and-saving/saving-documents-as-text-files/
---

## Введение в сохранение документов в виде текстовых файлов в Aspose.Words для Java

В этом уроке мы рассмотрим, как сохранять документы в виде текстовых файлов с помощью библиотеки Aspose.Words для Java. Aspose.Words — это мощный Java API для работы с документами Word, предоставляющий различные возможности сохранения документов в разных форматах, включая обычный текст. Мы рассмотрим шаги для достижения этой цели и попутно предоставим пример кода Java.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

- В вашей системе установлен Java Development Kit (JDK).
-  Библиотека Aspose.Words для Java, интегрированная в ваш проект. Вы можете скачать его с[здесь](https://releases.aspose.com/words/java/).
- Базовые знания Java-программирования.

## Шаг 1. Создайте документ

Чтобы сохранить документ в виде текстового файла, нам сначала нужно создать документ с помощью Aspose.Words. Вот простой фрагмент кода Java для создания документа с некоторым содержимым:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.writeln("Hello world!");
builder.getParagraphFormat().setBidi(true);
builder.writeln("שלום עולם!");
builder.writeln("مرحبا بالعالم!");
```

В этом коде мы создаем новый документ и добавляем в него текст, в том числе на разных языках.

## Шаг 2. Определите параметры сохранения текста

Далее нам нужно определить параметры сохранения текста, которые определяют, как документ должен быть сохранен в виде текстового файла. Мы можем настроить различные параметры, такие как добавление меток биди, идентификация списка и многое другое. Давайте рассмотрим два примера:

### Пример 1. Добавление меток двунаправленного текста

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
doc.save("output.txt", saveOptions);
```

 В этом примере мы создаем`TxtSaveOptions` объект и установите`AddBidiMarks`собственность`true` Чтобы включить метки биди в текстовый вывод.

### Пример 2. Использование символа табуляции для отступа списка

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
doc.save("output.txt", saveOptions);
```

Здесь мы настраиваем параметры сохранения для использования символа табуляции для идентификации списка со счетчиком 1.

## Шаг 3. Сохраните документ как текст

Теперь, когда мы определили параметры сохранения текста, мы можем сохранить документ как текстовый файл. Следующий код демонстрирует, как это сделать:

```java
doc.save("output.txt", saveOptions);
```

 Заменять`"output.txt"` с желаемым путем к файлу, в котором вы хотите сохранить текстовый файл.

## Полный исходный код для сохранения документов в виде текстовых файлов в Aspose.Words для Java

```java
    public void addBidiMarks() throws Exception
    {        
		Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        builder.writeln("Hello world!");
        builder.getParagraphFormat().setBidi(true);
        builder.writeln("שלום עולם!");
        builder.writeln("مرحبا بالعالم!");
        TxtSaveOptions saveOptions = new TxtSaveOptions(); { saveOptions.setAddBidiMarks(true); }
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.AddBidiMarks.txt", saveOptions);
    }
    @Test
    public void useTabCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Создайте список с тремя уровнями идентификации.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(1);
        saveOptions.getListIndentation().setCharacter('\t');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
    }
    @Test
    public void useSpaceCharacterPerLevelForListIndentation() throws Exception
    {
        Document doc = new Document();
        DocumentBuilder builder = new DocumentBuilder(doc);
        // Создайте список с тремя уровнями идентификации.
        builder.getListFormat().applyNumberDefault();
        builder.writeln("Item 1");
        builder.getListFormat().listIndent();
        builder.writeln("Item 2");
        builder.getListFormat().listIndent(); 
        builder.write("Item 3");
        TxtSaveOptions saveOptions = new TxtSaveOptions();
        saveOptions.getListIndentation().setCount(3);
        saveOptions.getListIndentation().setCharacter(' ');
        doc.save("Your Directory Path" + "WorkingWithTxtSaveOptions.UseSpaceCharacterPerLevelForListIndentation.txt", saveOptions);
	}
```

## Заключение

В этом уроке мы узнали, как сохранять документы в виде текстовых файлов в Aspose.Words для Java. Мы рассмотрели шаги по созданию документа, определению параметров сохранения текста и сохранению документа в текстовом формате. Aspose.Words обеспечивает большую гибкость при сохранении документов, позволяя адаптировать вывод к вашим конкретным требованиям.

## Часто задаваемые вопросы

### Как добавить метки биди к текстовому выводу?

 Чтобы добавить метки биди к текстовому выводу, установите`AddBidiMarks` свойство`TxtSaveOptions` к`true`. Например:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.setAddBidiMarks(true);
```

### Могу ли я настроить идентификацию символов списка?

 Да, вы можете настроить символ отступа списка, настроив`ListIndentation` свойство`TxtSaveOptions`. Например, чтобы использовать символ табуляции для отступа списка, вы можете сделать следующее:

```java
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.getListIndentation().setCount(1);
saveOptions.getListIndentation().setCharacter('\t');
```

### Подходит ли Aspose.Words для Java для обработки многоязычного текста?

Да, Aspose.Words for Java подходит для обработки многоязычного текста. Он поддерживает различные языки и кодировки символов, что делает его универсальным выбором для работы с документами на разных языках.

### Как я могу получить доступ к дополнительной документации и ресурсам для Aspose.Words для Java?

 Вы можете найти подробную документацию и ресурсы для Aspose.Words для Java на веб-сайте документации Aspose:[Документация Aspose.Words для Java](https://reference.aspose.com/words/java/).

### Где я могу скачать Aspose.Words для Java?

 Вы можете скачать библиотеку Aspose.Words для Java с сайта Aspose:[Скачать Aspose.Words для Java](https://releases.aspose.com/words/java/).