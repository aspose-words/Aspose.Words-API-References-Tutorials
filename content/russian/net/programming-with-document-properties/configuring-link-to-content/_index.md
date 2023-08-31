---
title: Настройка ссылки на контент
linktitle: Настройка ссылки на контент
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по настройке ссылок на контент в документе с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-document-properties/configuring-link-to-content/
---

В этом руководстве мы познакомим вас с исходным кодом C# для настройки связи с контентом с помощью Aspose.Words для .NET. Эта функция позволяет вам ссылаться на определенное содержимое документа.

## Шаг 1: Настройка проекта

Для начала создайте новый проект C# в вашей любимой IDE. Убедитесь, что в вашем проекте есть ссылка на библиотеку Aspose.Words for .NET.

## Шаг 2. Создание документа и конструктора

На этом этапе мы создадим новый документ и инициализируем конструктор. Используйте следующий код:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Шаг 3. Создайте закладку

Теперь создадим закладку в документе. Используйте следующий код, чтобы создать закладку с текстом внутри:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

Этот код создает закладку под названием «MyBookmark» и добавляет внутрь текст.

## Шаг 4. Настройка ссылки на контент

Теперь настроим ссылку на контент, используя свойства документа. Используйте следующий код, чтобы добавить и получить ссылку на контент:

```csharp
// Получите список всех пользовательских свойств в документе.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Добавьте свойство, привязанное к содержимому.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

Этот код добавляет свойство, связанное с содержимым, под названием «Bookmark» с закладкой «MyBookmark». Затем он извлекает информацию о свойствах, связанных с контентом, такую как состояние ссылки, источник ссылки и значение свойства.

### Пример исходного кода для настройки ссылки на контент с использованием Aspose.Words для .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Получите список всех пользовательских свойств документа из файла.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Добавьте свойство «связано с содержимым».
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

Теперь вы узнали, как настроить ссылку на контент в документе с помощью Aspose.Words для .NET. Следуя пошаговому руководству, представленному в этом руководстве, вы сможете легко создавать и настраивать ссылки на определенный контент в своих собственных документах.