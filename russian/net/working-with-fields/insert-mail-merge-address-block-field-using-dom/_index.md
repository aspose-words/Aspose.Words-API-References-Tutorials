---
title: Вставьте поле блока адреса для слияния с помощью DOM
linktitle: Вставьте поле блока адреса для слияния с помощью DOM
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставить поле блока адреса слияния в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fields/insert-mail-merge-address-block-field-using-dom/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используется функция «Вставить поле блока адреса слияния» в Aspose.Words для .NET. Обязательно внимательно следуйте каждому шагу, чтобы получить желаемые результаты.

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

## Шаг 3: Перемещение курсора к абзацу

 Мы используем DocumentBuilder`MoveTo()` метод, чтобы переместить курсор в абзац, где мы хотим вставить поле блока адреса слияния.

```csharp
Paragraph para = (Paragraph)doc.GetChildNodes(NodeType.Paragraph, true)[0];
builder. MoveTo(para);
```

## Шаг 4. Вставка поля блока адреса для слияния

 Мы используем DocumentBuilder`InsertField()` способ вставки поля блока адреса слияния в абзац.

```csharp
FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, false);
```

Затем мы настраиваем свойства поля блока адресов, указав соответствующие параметры, такие как включение названия страны/региона, форматирование адреса в соответствии со страной/регионом, исключение названий страны/региона, формат имени и адреса и идентификатор языка.

```csharp
field.IncludeCountryOrRegionName = "1";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "Test2";
field.NameAndAddressFormat = "Test3";
field.LanguageId = "Test 4";
```

 Наконец, мы вызываем`Update()` способ обновления поля.

```csharp
field. Update();
```

### Пример исходного кода для вставки поля блока адреса слияния с помощью Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Paragraph para = (Paragraph) doc.GetChildNodes(NodeType.Paragraph, true)[0];

builder. MoveTo(para);

// Мы хотим вставить блок адреса слияния следующим образом:
// {ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }

FieldAddressBlock field = (FieldAddressBlock) builder.InsertField(FieldType.FieldAddressBlock, false);

// {АДРЕСБЛОК \\c 1"}
field.IncludeCountryOrRegionName = "1";

// {АДРЕСБЛОК \\c 1 \\d"}
field.FormatAddressOnCountryOrRegion = true;

// {АДРЕСБЛОК \\c 1 \\d \\e Test2 }
field.ExcludedCountryOrRegionName = "Test2";

// {ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 }
field.NameAndAddressFormat = "Test3";

// {ADDRESSBLOCK \\c 1 \\d \\e Test2 \\f Test3 \\l \"Test 4\" }
field.LanguageId = "Test 4";

field. Update();

doc.Save(ArtifactsDir + "WorkingWithFields.InsertMailMergeAddressBlockFieldUsingDOM.docx");
```
