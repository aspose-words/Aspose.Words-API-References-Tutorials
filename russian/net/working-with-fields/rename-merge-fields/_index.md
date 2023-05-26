---
title: Переименовать поля слияния
linktitle: Переименовать поля слияния
second_title: Справочник по API Aspose.Words для .NET
description: В этом руководстве вы узнаете, как переименовать поля слияния в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/rename-merge-fields/
---

Вот пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция переименования поля слияния Aspose.Words для .NET. Внимательно выполняйте каждый шаг, чтобы получить желаемый результат.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа и вставка полей слияния

 Начнем с создания нового документа и использования`DocumentBuilder` для вставки полей слияния.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Шаг 3: Переименование полей слияния

Мы перебираем каждое поле в диапазоне документа, и если это поле слияния, мы переименовываем поле, добавляя "_Суффикс «переименован».

```csharp
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}
```

## Шаг 4: Сохранение документа

 Наконец, мы вызываем`Save()` метод сохранения измененного документа.

```csharp
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

### Пример исходного кода для переименования полей слияния с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создайте документ и вставьте поля слияния.
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");

// Переименуйте поля слияния.
foreach(Field f in doc.Range.Fields)
{
     if (f.Type == FieldType.FieldMergeField)
     {
         FieldMergeField mergeField = (FieldMergeField)f;
         mergeField.FieldName = mergeField.FieldName + "_Renamed";
         mergeField.Update();
     }
}

// Сохраните документ.
doc.Save(dataDir + "WorkingWithFields.RenameMergeFields.docx");
```

Выполните следующие действия, чтобы переименовать поля слияния в документе с помощью Aspose.Words for .NET.