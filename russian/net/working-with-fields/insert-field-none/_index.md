---
title: Вставить поле Нет
linktitle: Вставить поле Нет
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как использовать AUCUN в документах Word с Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-field-none/
---

Вот пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция «Insert NONE Field» Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

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

## Шаг 3: Вставка поля NONE

 Мы используем`InsertField()` Метод DocumentBuilder для вставки поля NONE в документ.

```csharp
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);
```

### Пример исходного кода для вставки поля NONE с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и DocumentBuilder.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставьте поле НЕТ.
FieldUnknown field = (FieldUnknown)builder.InsertField(FieldType.FieldNone, false);

doc.Save(dataDir + "InsertionFieldNone.docx");
```

В этом примере мы создали новый документ, инициализировали DocumentBuilder, а затем вставили поле NONE. Затем документ сохраняется с указанным именем файла.

На этом мы завершаем наше руководство по использованию функции «Вставить НИ ОДНОГО поля» с Aspose.Words для .NET.