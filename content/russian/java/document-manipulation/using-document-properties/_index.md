---
title: Использование свойств документа в Aspose.Words для Java
linktitle: Использование свойств документа
second_title: API обработки Java-документов Aspose.Words
description: Оптимизируйте управление документами с помощью Aspose.Words для Java. В этом подробном руководстве вы научитесь работать со свойствами документа, добавлять собственные метаданные и выполнять другие действия.
type: docs
weight: 32
url: /ru/java/document-manipulation/using-document-properties/
---

## Введение в свойства документа

Свойства документа являются важной частью любого документа. Они предоставляют дополнительную информацию о самом документе, такую как его название, автор, тема, ключевые слова и многое другое. В Aspose.Words for Java вы можете манипулировать как встроенными, так и настраиваемыми свойствами документа.

## Перечисление свойств документа

### Встроенные свойства

Чтобы получить встроенные свойства документа и работать с ними, вы можете использовать следующий фрагмент кода:

```java
@Test
public void enumerateProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    System.out.println(MessageFormat.format("1. Document name: {0}", doc.getOriginalFileName()));
    System.out.println("2. Built-in Properties");
    for (DocumentProperty prop : doc.getBuiltInDocumentProperties())
        System.out.println(MessageFormat.format("{0} : {1}", prop.getName(), prop.getValue()));
}
```

Этот код отобразит имя документа и встроенные свойства, включая такие свойства, как «Название», «Автор» и «Ключевые слова».

### Пользовательские свойства

Для работы с настраиваемыми свойствами документа вы можете использовать следующий фрагмент кода:

```java
@Test
public void addCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    CustomDocumentProperties customDocumentProperties = doc.getCustomDocumentProperties();

    if (customDocumentProperties.get("Authorized") != null) return;

    customDocumentProperties.add("Authorized", true);
    customDocumentProperties.add("Authorized By", "John Smith");
    customDocumentProperties.add("Authorized Date", new Date());
    customDocumentProperties.add("Authorized Revision", doc.getBuiltInDocumentProperties().getRevisionNumber());
    customDocumentProperties.add("Authorized Amount", 123.45);
}
```

В этом фрагменте кода показано, как добавлять пользовательские свойства документа, включая логическое значение, строку, дату, номер версии и числовое значение.

## Удаление свойств документа

Чтобы удалить определенные свойства документа, вы можете использовать следующий код:

```java
@Test
public void removeCustomDocumentProperties() throws Exception
{
    Document doc = new Document("Your Directory Path" + "Properties.docx");
    doc.getCustomDocumentProperties().remove("Authorized Date");
}
```

Этот код удаляет из документа настраиваемое свойство «Дата авторизации».

## Настройка ссылки на контент

В некоторых случаях вам может потребоваться создать ссылки внутри документа. Вот как вы можете это сделать:

```java
@Test
public void configuringLinkToContent() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.startBookmark("MyBookmark");
    builder.writeln("Text inside a bookmark.");
    builder.endBookmark("MyBookmark");

    CustomDocumentProperties customProperties = doc.getCustomDocumentProperties();

    // Добавьте свойство «связано с содержимым».
    DocumentProperty customProperty = customProperties.addLinkToContent("Bookmark", "MyBookmark");
    customProperty = customProperties.get("Bookmark");
    boolean isLinkedToContent = customProperty.isLinkToContent();
    String linkSource = customProperty.getLinkSource();
    String customPropertyValue = customProperty.getValue().toString();
}
```

В этом фрагменте кода показано, как создать закладку в документе и добавить настраиваемое свойство документа, которое ссылается на эту закладку.

## Преобразование между единицами измерения

В Aspose.Words для Java вы можете легко конвертировать единицы измерения. Вот пример того, как это сделать:

```java
@Test
public void convertBetweenMeasurementUnits() throws Exception
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);
    PageSetup pageSetup = builder.getPageSetup();

    // Установите поля в дюймах.
    pageSetup.setTopMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setBottomMargin(ConvertUtil.inchToPoint(1.0));
    pageSetup.setLeftMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setRightMargin(ConvertUtil.inchToPoint(1.5));
    pageSetup.setHeaderDistance(ConvertUtil.inchToPoint(0.2));
    pageSetup.setFooterDistance(ConvertUtil.inchToPoint(0.2));
}
```

Этот фрагмент кода устанавливает различные поля и расстояния в дюймах, преобразуя их в точки.

## Использование управляющих символов

Управляющие символы могут быть полезны при работе с текстом. Вот как заменить управляющий символ в тексте:

```java
@Test
public void useControlCharacters()
{
    final String TEXT = "test\r";

    // Замените управляющий символ «\r» на «\r\n».
    String replace = TEXT.replace(ControlChar.CR, ControlChar.CR_LF);
}
```

В этом примере мы заменяем возврат каретки (`\r`) с возвратом каретки и последующим переводом строки (`\r\n`).

## Заключение

Свойства документа играют важную роль в эффективном управлении и организации ваших документов в Aspose.Words for Java. Независимо от того, работаете ли вы со встроенными свойствами, настраиваемыми свойствами или используете управляющие символы, в вашем распоряжении имеется ряд инструментов для расширения возможностей управления документами.

## Часто задаваемые вопросы

### Как получить доступ к встроенным свойствам документа?

 Чтобы получить доступ к встроенным свойствам документа в Aspose.Words для Java, вы можете использовать команду`getBuiltInDocumentProperties` метод на`Document` объект. Этот метод возвращает коллекцию встроенных свойств, которые можно перебирать.

### Могу ли я добавить в документ собственные свойства?

 Да, вы можете добавить в документ собственные свойства, используя`CustomDocumentProperties` коллекция. Вы можете определить настраиваемые свойства с различными типами данных, включая строки, логические значения, даты и числовые значения.

### Как удалить определенное свойство пользовательского документа?

 Чтобы удалить определенное пользовательское свойство документа, вы можете использовать команду`remove` метод на`CustomDocumentProperties`коллекцию, передав в качестве параметра имя свойства, которое вы хотите удалить.

### Какова цель ссылки на контент внутри документа?

Ссылки на содержимое внутри документа позволяют создавать динамические ссылки на определенные части документа. Это может быть полезно для создания интерактивных документов или перекрестных ссылок между разделами.

### Как я могу конвертировать различные единицы измерения в Aspose.Words для Java?

 Вы можете конвертировать различные единицы измерения в Aspose.Words для Java, используя`ConvertUtil` сорт. Он предоставляет методы для преобразования таких единиц, как дюймы в пункты, точки в сантиметры и т. д.