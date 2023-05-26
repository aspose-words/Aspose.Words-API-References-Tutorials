---
title: Вставить поле с помощью конструктора полей
linktitle: Вставить поле с помощью конструктора полей
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять настраиваемые поля в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-field-using-field-builder/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используется функция «Вставить поле с помощью FieldBuilder» Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

## Шаг 1: Настройка каталога документов

В предоставленном коде необходимо указать директорию ваших документов. Замените значение «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь к каталогу ваших документов.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Создание документа

Начнем с создания нового документа.

```csharp
Document doc = new Document();
```

## Шаг 3: Создание поля IF с помощью FieldBuilder

Мы используем класс FieldBuilder для создания поля IF с двумя вложенными полями MERGEFIELD. В этом примере поле ЕСЛИ отображает имя и фамилию в зависимости от условия.

```csharp
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));
```

## Шаг 4: Вставка поля ЕСЛИ в документ

 Мы используем`BuildAndInsert()` метод для создания и вставки поля ЕСЛИ в определенное место в документе.

```csharp
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();
```

### Пример исходного кода для вставки поля с помощью FieldBuilder с Aspose.Words для .NET

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Создание документа.
Document doc = new Document();

// Построение поля IF с помощью FieldBuilder.
FieldBuilder fieldBuilder = new FieldBuilder(FieldType.FieldIf)
     .AddArgument("left expression")
     .AddArgument("=")
     .AddArgument("right expression")
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Firstname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("firstname")))
     .AddArgument(
         new FieldArgumentBuilder()
             .AddText("Lastname: ")
             .AddField(new FieldBuilder(FieldType.FieldMergeField).AddArgument("lastname")));

// Вставьте поле ЕСЛИ в документ.
Field field = fieldBuilder.BuildAndInsert(doc.FirstSection.Body.FirstParagraph);
field. Update();

doc.Save(dataDir + "InsertFieldWithFieldBuilder.docx");
```

В этом примере мы создали новый документ, построили поле ЕСЛИ с вложенными полями MERGEFIELD, а затем вставили это поле в документ в указанном месте. Затем документ сохраняется с определенным именем файла.
