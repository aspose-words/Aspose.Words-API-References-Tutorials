---
title: Удалить поле
linktitle: Удалить поле
second_title: Справочник по API Aspose.Words для .NET
description: В этом руководстве вы узнаете, как удалить определенное поле в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/remove-field/
---
Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используется функция «Удаление поля» Aspose.Words для .NET. Внимательно выполняйте каждый шаг, чтобы получить желаемый результат.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Загрузка документа

Начнем с загрузки существующего документа из указанного файла.

```csharp
Document doc = new Document(dataDir + "Various fields.docx");
```

## Шаг 3: Удаление поля

 Мы выбираем первое поле в диапазоне документа и используем`Remove()` метод его удаления.

```csharp
Field field = doc.Range.Fields[0];
field. Remove();
```

## Шаг 4: Сохранение документа

 Наконец, мы вызываем`Save()` метод сохранения измененного документа.

```csharp
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

### Пример исходного кода для удаления поля с помощью Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Загрузите документ.
Document doc = new Document(dataDir + "Various fields.docx");

// Выбор поля для удаления.
Field field = doc.Range.Fields[0];
field. Remove();

// Сохраните документ.
doc.Save(dataDir + "WorkingWithFields.RemoveField.docx");
```

Выполните следующие действия, чтобы удалить определенное поле в документе с помощью Aspose.Words для .NET.
