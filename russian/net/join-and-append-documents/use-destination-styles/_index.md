---
title: Использовать целевые стили
linktitle: Использовать целевые стили
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как объединять и добавлять документы Word, применяя стили целевого документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/use-destination-styles/
---

Это руководство проведет вас через процесс использования функции «Использовать целевые стили» в Aspose.Words для .NET. Эта функция позволяет объединять и добавлять документы Word, применяя стили целевого документа.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET установлен. Вы можете загрузить его с веб-сайта Aspose или установить через NuGet.
2. Visual Studio или любая другая среда разработки C#.

## Шаг 1: Инициализируйте каталоги документов

 Во-первых, вам нужно указать путь к папке с документами. Измените значение параметра`dataDir` переменная на путь, где находятся ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходный и целевой документы

 Далее вам нужно загрузить исходный и конечный документы с помощью Aspose.Words.`Document` сорт. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Добавьте к исходному документу целевые стили

 Чтобы добавить исходный документ к целевому документу, применяя стили целевого документа, вы можете использовать`AppendDocument` метод`Document` класс с`ImportFormatMode.UseDestinationStyles` параметр.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Шаг 4: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией «Использовать целевые стили».`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Пример исходного кода для использования стилей назначения с использованием Aspose.Words для .NET

Вот полный исходный код функции «Использовать стили назначения» в C# с использованием Aspose.Words для .NET:

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Добавьте исходный документ, используя стили целевого документа.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Вот и все! Вы успешно реализовали функцию «Использовать целевые стили» с помощью Aspose.Words для .NET. Конечный документ будет содержать объединенное содержимое с примененными стилями целевого документа.