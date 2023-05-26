---
title: Вставить поле
linktitle: Вставить поле
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить поле в документы Word с помощью Aspose.Words для .NET. Персонализируйте свои документы с помощью динамических полей.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-field/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используется функция «Вставить поле» Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и DocumentBuilder

Начнем с создания нового документа и инициализации DocumentBuilder.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3: Вставка поля

 Мы используем`InsertField()` метод DocumentBuilder для вставки поля в документ. В этом примере мы вставляем поле слияния (MERGEFIELD) с именем поля «MyFieldName» и форматом слияния.

```csharp
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");
```

### Пример исходного кода для вставки поля с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте поле.
builder.InsertField(@"MERGEFIELD MyFieldName \* MERGEFORMAT");

doc.Save(dataDir + "InsertionField.docx");
```

В этом примере мы создали новый документ, инициализировали DocumentBuilder, а затем вставили поле слияния с именем поля «MyFieldName» и форматом слияния. Затем документ сохраняется с указанным именем файла.

На этом мы завершаем наше руководство по использованию функции «Вставить поле» с Aspose.Words для .NET.
