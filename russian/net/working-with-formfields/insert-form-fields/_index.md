---
title: Вставить поля формы
linktitle: Вставить поля формы
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как вставлять раскрывающиеся поля формы в документы Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-formfields/insert-form-fields/
---

В этом пошаговом руководстве мы расскажем вам, как вставить поля формы, в частности раскрывающееся поле формы, в документ Word с помощью Aspose.Words для .NET. Мы объясним предоставленный исходный код C# и покажем вам, как реализовать его в ваших собственных проектах.

Для начала убедитесь, что Aspose.Words for .NET установлен и настроен в вашей среде разработки. Если вы этого не сделали, скачайте и установите библиотеку с официального сайта.

## Шаг 1: Инициализация объектов Document и DocumentBuilder

 Сначала инициализируйте`Document` и`DocumentBuilder` объекты:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 2. Вставка поля раскрывающейся формы

 Далее укажите параметры поля выпадающей формы и вставьте его в документ с помощью кнопки`InsertComboBox` метод`DocumentBuilder`объект. В этом примере мы вставляем раскрывающееся поле формы с именем «DropDown» с тремя параметрами: «Один», «Два» и «Три»:

```csharp
string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);
```

## Шаг 3: Сохранение документа

Наконец, сохраните документ:

```csharp
doc.Save("OutputDocument.docx");
```

Вот и все! Вы успешно вставили раскрывающееся поле формы в документ Word с помощью Aspose.Words для .NET.

### Пример исходного кода для вставки полей формы с использованием Aspose.Words для .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

string[] items = { "One", "Two", "Three" };
builder.InsertComboBox("DropDown", items, 0);

doc.Save("OutputDocument.docx");
```

Не стесняйтесь использовать этот код в своих проектах и модифицировать его в соответствии с вашими конкретными требованиями.