---
title: Вставить поле формы со списком
linktitle: Вставить поле формы со списком
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять поля формы со списком в документы Word с помощью Aspose.Words для .NET. Пошаговое руководство.
type: docs
weight: 10
url: /ru/net/add-content-using-documentbuilder/insert-combo-box-form-field/
---

В этом подробном примере вы узнаете, как вставить поле формы со списком в документ Word с помощью Aspose.Words для .NET. Мы проведем вас через весь процесс и предоставим необходимые фрагменты кода C#. К концу этого руководства вы сможете добавлять поля форм со списком с настраиваемыми свойствами в свои документы.

## Предпосылки
Прежде чем мы начнем, убедитесь, что у вас есть следующие предварительные условия:
- В вашей системе установлена библиотека Aspose.Words for .NET.

## Шаг 1: Создайте новый документ и DocumentBuilder
Для начала создайте новый документ с помощью класса Document и инициализируйте объект DocumentBuilder:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Определите элементы поля со списком
Затем определите массив элементов для поля формы со списком:

```csharp
string[] items = { "One", "Two", "Three" };
```

## Шаг 3. Вставьте поле формы со списком
Используйте метод InsertComboBox класса DocumentBuilder, чтобы вставить поле формы поля со списком. Укажите имя, массив элементов и выбранный индекс в качестве параметров:

```csharp
builder.InsertComboBox("DropDown", items, 0);
```

## Шаг 4: Сохраните документ
После вставки поля формы со списком сохраните документ в файл с помощью метода Save класса Document:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

### Пример исходного кода для вставки поля формы со списком с использованием Aspose.Words для .NET
Вот полный исходный код для вставки поля формы со списком с помощью Aspose.Words для .NET:

```csharp
string[] items = { "One", "Two", "Three" };

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertComboBox("DropDown", items, 0);

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
```

Не забудьте настроить код в соответствии с вашими конкретными требованиями и добавить в него дополнительные функции по мере необходимости.

## Заключение
Поздравляем! Вы успешно научились вставлять поле формы со списком в документ Word с помощью Aspose.Words для .NET. Следуя пошаговому руководству и используя предоставленный исходный код, теперь вы можете дополнить свои документы интерактивными полями формы со списком.
