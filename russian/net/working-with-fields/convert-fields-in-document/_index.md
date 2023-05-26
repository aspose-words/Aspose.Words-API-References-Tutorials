---
title: Преобразование полей в документе
linktitle: Преобразование полей в документе
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по преобразованию полей документа в текст с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/convert-fields-in-document/
---

В этом руководстве мы дадим вам пошаговое руководство по использованию функции ConvertFieldsInDocument программного обеспечения Aspose.Words для .NET. Мы подробно объясним исходный код C#, необходимый для этой функции, и предоставим примеры выходных форматов уценки.

## Шаг 1: Предпосылки
Прежде чем начать, убедитесь, что у вас есть следующее:

- Aspose.Words for .NET установлен на вашем компьютере для разработки.
- Документ Word, содержащий связанные поля, которые вы хотите преобразовать в текст.
- Каталог документов, в котором вы можете сохранить преобразованный документ.

## Шаг 2. Настройка среды
Убедитесь, что вы правильно настроили среду разработки для использования Aspose.Words for .NET. Импортируйте необходимые пространства имен и укажите путь к каталогу ваших документов.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 3: Загрузите документ
 Использовать`Document` класс Aspose.Words, чтобы загрузить документ Word, содержащий связанные поля, которые вы хотите преобразовать.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");
```

## Шаг 4. Преобразование связанных полей в текст
 Использовать`Unlink()` метод для преобразования всех полей типа «IF», встречающихся в документе, в текст. Этот метод используется для преобразования связанных полей в их текстовое содержимое.

```csharp
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());
```

## Шаг 5: Сохраните преобразованный документ
 Использовать`Save()` метод сохранения документа с полями, преобразованными в текст, в указанном каталоге документа.

```csharp
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Пример исходного кода для ConvertFieldsInDocument с использованием Aspose.Words для .NET

Вот полный исходный код функции ConvertFieldsInDocument:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(MyDir + "Linked fields.docx");

// Передайте соответствующие параметры, чтобы преобразовать все поля ЕСЛИ, встречающиеся в документе (включая верхние и нижние колонтитулы), в текст.
doc.Range.Fields.Where(f => f.Type == FieldType.FieldIf).ToList().ForEach(f => f.Unlink());

// Сохраните документ с преобразованными полями на диск
doc.Save(dataDir + "WorkingWithFields.ConvertFieldsInDocument.docx");
```

## Заключение
Функция Aspose.Words for .NET ConvertFieldsInDocument — это мощный инструмент для преобразования связанных полей в документе Word в текст. 