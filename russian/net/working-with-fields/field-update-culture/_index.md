---
title: Культура обновления поля
linktitle: Культура обновления поля
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как обновить культуру полей в документах Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/field-update-culture/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используется функция «Обновление полевой культуры» Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и генератора документов

Начнем с создания нового документа и генератора документов.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3: Вставка поля времени

 Мы используем`InsertField()` метод для вставки поля времени в документ.

```csharp
builder. InsertField(FieldType.FieldTime, true);
```

Это добавит поле времени в документ.

## Шаг 4. Настройка культуры обновления поля

Мы настраиваем параметры поля, чтобы указать, что культура обновления поля должна основываться на коде поля.

```csharp
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();
```

Эти параметры определяют культуру, используемую для обновления полей.

### Пример исходного кода для обновления культуры поля с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и генератор документов.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте поле времени.
builder. InsertField(FieldType.FieldTime, true);

// Настройте культуру обновления полей.
doc.FieldOptions.FieldUpdateCultureSource = FieldUpdateCultureSource.FieldCode;
doc.FieldOptions.FieldUpdateCultureProvider = new FieldUpdateCultureProvider();

// Сохраните документ.
doc.Save(dataDir + "UpdateCultureChamps.pdf");
```

В этом примере мы создали новый документ, вставили поле времени и настроили культуру обновления поля. Затем мы сохранили документ с указанным именем файла.

На этом мы завершаем наше руководство по использованию функции «Обновить культуру поля» в Aspose.Words для .NET.