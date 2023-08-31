---
title: Использовать целевые стили
linktitle: Использовать целевые стили
second_title: API обработки документов Aspose.Words
description: Узнайте, как объединять и добавлять документы Word при применении стилей целевого документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/use-destination-styles/
---

Это руководство проведет вас через процесс использования функции «Использовать целевые стили» в Aspose.Words for .NET. Эта функция позволяет объединять и добавлять документы Word, применяя стили целевого документа.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET установлен. Вы можете скачать его с веб-сайта Aspose или установить через NuGet.
2. Visual Studio или любая другая среда разработки C#.

## Шаг 1. Инициализируйте каталоги документов

 Во-первых, вам нужно установить путь к каталогу вашего документа. Измените значение параметра`dataDir`переменная пути, по которому расположены ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходные и целевые документы

 Далее вам необходимо загрузить исходные и целевые документы с помощью Aspose.Words.`Document` сорт. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Добавьте исходный документ с целевыми стилями

 Чтобы добавить исходный документ к целевому документу при применении стилей целевого документа, вы можете использовать команду`AppendDocument` метод`Document` класс с`ImportFormatMode.UseDestinationStyles` параметр.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Шаг 4. Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией «Использовать целевые стили», используя`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

### Пример исходного кода для использования стилей назначения с использованием Aspose.Words для .NET

Вот полный исходный код функции «Использовать целевые стили» на C# с использованием Aspose.Words для .NET:

```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Добавьте исходный документ, используя стили целевого документа.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UseDestinationStyles.docx");
```

Вот и все! Вы успешно реализовали функцию «Использовать целевые стили» с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенное содержимое с примененными стилями целевого документа.