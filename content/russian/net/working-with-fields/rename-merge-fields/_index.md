---
title: Переименуйте поля слияния
linktitle: Переименуйте поля слияния
second_title: API обработки документов Aspose.Words
description: В этом уроке вы узнаете, как переименовать поля слияния в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/rename-merge-fields/
---

Ниже приведено пошаговое руководство, объясняющее приведенный ниже исходный код C#, в котором используется функция переименования полей слияния Aspose.Words для .NET. Внимательно выполняйте каждый шаг, чтобы получить желаемые результаты.

## Шаг 1. Настройка каталога документов

В предоставленном коде вы должны указать каталог ваших документов. Замените значение «КАТАЛОГ ВАШЕГО ДОКУМЕНТА» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2. Создание документа и вставка полей слияния

Начнем с создания нового документа и использования`DocumentBuilder` для вставки полей слияния.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertField(@"MERGEFIELD MyMergeField1 \* MERGEFORMAT");
builder.InsertField(@"MERGEFIELD MyMergeField2 \* MERGEFORMAT");
```

## Шаг 3. Переименование полей слияния

Мы просматриваем каждое поле в диапазоне документа, и если это поле слияния, мы переименовываем его, добавляя «_Суффикс «Переименован».

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

## Шаг 4. Сохраните документ.

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

Выполните следующие действия, чтобы переименовать поля слияния в документе с помощью Aspose.Words для .NET.

### Часто задаваемые вопросы

#### Вопрос: Как переименовать объединенные поля в документе Word с помощью Aspose.Words для .NET?

 О: Чтобы переименовать объединенные поля в документе Word с помощью Aspose.Words for .NET, вы можете перебирать поля в документе, используя команду`FieldMergingArgs` класс и используйте`FieldMergingArgs.FieldName` метод переименования поля.

#### Вопрос: Можно ли переименовать только определенные объединенные поля в документе Word с помощью Aspose.Words for .NET?

О: Да, с помощью Aspose.Words for .NET можно переименовать только определенные объединенные поля в документе Word. Вы можете отфильтровать поля для переименования, используя определенные критерии, такие как имя поля или другие соответствующие свойства. Затем вы можете переименовать соответствующие поля, используя`FieldMergingArgs.FieldName` метод.

#### Вопрос: Как я могу проверить, было ли объединенное поле успешно переименовано в документе Word с помощью Aspose.Words for .NET?

 О: Чтобы проверить, было ли объединенное поле успешно переименовано в документе Word с помощью Aspose.Words for .NET, вы можете использовать команду`FieldMergedArgs` класс и получить доступ к`FieldMergedArgs.IsMerged` свойство, чтобы определить, было ли поле названо совпадением.

#### Вопрос: Каковы последствия переименования объединенного поля в документе Word с помощью Aspose.Words for .NET?

О: Когда вы переименовываете объединенное поле в документе Word с помощью Aspose.Words for .NET, имя поля в документе меняется, что может повлиять на другие функции или процессы, зависящие от имени поля. Обязательно учтите эти потенциальные последствия перед переименованием объединенных полей.

#### Вопрос: Можно ли восстановить исходное имя объединенного поля после его переименования с помощью Aspose.Words for .NET?

О: Да, исходное имя объединенного поля можно восстановить после переименования его с помощью Aspose.Words for .NET. Вы можете сохранить исходное имя поля в переменной или списке, а затем использовать эту информацию для восстановления исходного имени, если это необходимо.