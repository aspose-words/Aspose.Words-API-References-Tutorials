---
title: Сохранение документов в формате ODT в Aspose.Words для Java
linktitle: Сохранение документов в формате ODT
second_title: API обработки Java-документов Aspose.Words
description: Узнайте, как сохранять документы в формате ODT с помощью Aspose.Words для Java. Обеспечьте совместимость с офисными пакетами с открытым исходным кодом.
type: docs
weight: 19
url: /ru/java/document-loading-and-saving/saving-documents-as-odt-format/
---

## Введение в сохранение документов в формате ODT в Aspose.Words для Java

В этой статье мы рассмотрим, как сохранять документы в формате ODT (текст открытого документа) с помощью Aspose.Words для Java. ODT — это популярный открытый стандартный формат документов, используемый различными офисными пакетами, включая OpenOffice и LibreOffice. Сохраняя документы в формате ODT, вы можете обеспечить совместимость с этими программными пакетами.

## Предварительные условия

Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:

1. Среда разработки Java: убедитесь, что в вашей системе установлен Java Development Kit (JDK).

2.  Aspose.Words для Java: Загрузите и установите библиотеку Aspose.Words для Java. Вы можете найти ссылку для скачивания[здесь](https://releases.aspose.com/words/java/).

3. Образец документа: у вас есть образец документа Word (например, «Document.docx»), который вы хотите преобразовать в формат ODT.

## Шаг 1. Загрузите документ

Сначала давайте загрузим документ Word с помощью Aspose.Words for Java:

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
```

 Здесь,`"Your Directory Path"` должен указывать на каталог, в котором находится ваш документ.

## Шаг 2. Укажите параметры сохранения ODT

Чтобы сохранить документ как ODT, нам нужно указать параметры сохранения ODT. Дополнительно мы можем установить единицу измерения для документа. В Open Office используются сантиметры, а в MS Office — дюймы. Мы установим его в дюймах:

```java
OdtSaveOptions saveOptions = new OdtSaveOptions();
saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES);
```

## Шаг 3. Сохраните документ

Теперь пришло время сохранить документ в формате ODT:

```java
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

 Здесь,`"Your Directory Path"` должен указывать на каталог, в котором вы хотите сохранить преобразованный файл ODT.

## Полный исходный код для сохранения документов в формате ODT в Aspose.Words для Java

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
// Open Office использует сантиметры при указании длины, ширины и другого измеряемого форматирования.
// и свойства содержимого в документах, тогда как MS Office использует дюймы.
OdtSaveOptions saveOptions = new OdtSaveOptions(); { saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES); }
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## Заключение

В этой статье мы узнали, как сохранять документы в формате ODT с помощью Aspose.Words для Java. Это может быть особенно полезно, когда вам нужно обеспечить совместимость с офисными пакетами с открытым исходным кодом, такими как OpenOffice и LibreOffice.

## Часто задаваемые вопросы

### Как я могу скачать Aspose.Words для Java?

 Вы можете скачать Aspose.Words для Java с веб-сайта Aspose. Посещать[эта ссылка](https://releases.aspose.com/words/java/)для доступа к странице загрузки.

### В чем преимущество сохранения документов в формате ODT?

Сохранение документов в формате ODT обеспечивает совместимость с офисными пакетами с открытым исходным кодом, такими как OpenOffice и LibreOffice, что упрощает пользователям этих программных пакетов доступ и редактирование ваших документов.

### Нужно ли указывать единицу измерения при сохранении в формате ODT?

Да, рекомендуется указывать единицу измерения. Open Office по умолчанию использует сантиметры, поэтому установка дюймов обеспечивает единообразие форматирования.

### Могу ли я преобразовать несколько документов в формат ODT в пакетном режиме?

Да, вы можете автоматизировать преобразование нескольких документов в формат ODT с помощью Aspose.Words для Java, просматривая файлы документов и применяя процесс преобразования.

### Совместим ли Aspose.Words for Java с последними версиями Java?

Aspose.Words for Java регулярно обновляется для поддержки последних версий Java, обеспечивая совместимость и повышение производительности. Обязательно проверьте системные требования в документации для получения последней информации.