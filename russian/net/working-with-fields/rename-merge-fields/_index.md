---
title: Переименовать поля слияния
linktitle: Переименовать поля слияния
second_title: API обработки документов Aspose.Words
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

### Часто задаваемые вопросы

#### В: Как переименовать объединенные поля в документе Word с помощью Aspose.Words for .NET?

 О: Чтобы переименовать объединенные поля в документе Word с помощью Aspose.Words for .NET, вы можете циклически перебирать поля в документе с помощью команды`FieldMergingArgs` класс и использовать`FieldMergingArgs.FieldName` способ переименовать поле.

#### В: Можно ли переименовать только определенные объединенные поля в документе Word с помощью Aspose.Words для .NET?

О: Да, с помощью Aspose.Words for .NET можно переименовать только определенные объединенные поля в документе Word. Вы можете отфильтровать, какие поля следует переименовать, используя определенные критерии, такие как имя поля или другие соответствующие свойства. Затем вы можете переименовать соответствующие поля с помощью`FieldMergingArgs.FieldName` метод.

#### В: Как я могу проверить, было ли успешно переименовано объединенное поле в документе Word с помощью Aspose.Words for .NET?

 О: Чтобы проверить, было ли успешно переименовано объединенное поле в документе Word с помощью Aspose.Words for .NET, вы можете использовать`FieldMergedArgs` класс и получить доступ к`FieldMergedArgs.IsMerged` свойство, чтобы определить, было ли поле переименовано при попадании.

#### В: Каковы последствия переименования объединенного поля в документе Word с помощью Aspose.Words for .NET?

О: Когда вы переименовываете объединенное поле в документе Word с помощью Aspose.Words for .NET, оно меняет имя поля в документе, что может повлиять на другие функции или процессы, зависящие от имени поля. Обязательно учитывайте эти возможные последствия, прежде чем переименовывать объединенные поля.

#### В: Можно ли восстановить исходное имя объединенного поля после его переименования с помощью Aspose.Words for .NET?

О: Да, можно восстановить исходное имя объединенного поля после его переименования с помощью Aspose.Words для .NET. Вы можете сохранить исходное имя поля в переменной или списке, а затем использовать эту информацию для восстановления исходного имени, если это необходимо.