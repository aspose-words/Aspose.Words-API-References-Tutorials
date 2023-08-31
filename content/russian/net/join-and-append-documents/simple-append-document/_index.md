---
title: Простое добавление документа
linktitle: Простое добавление документа
second_title: API обработки документов Aspose.Words
description: Узнайте, как объединять и добавлять документы Word с сохраненным форматированием с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/simple-append-document/
---

Это руководство проведет вас через процесс использования функции простого добавления документа в Aspose.Words для .NET. Эта функция позволяет объединять и добавлять документы Word без дополнительных опций.

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

## Шаг 3. Добавьте исходный документ в целевой документ

 Теперь вы можете добавить исходный документ к целевому документу, используя команду`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр гарантирует, что исходное форматирование сохраняется во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 4. Сохраните окончательный документ

 Наконец, сохраните объединенный документ с помощью функции «Простое добавление документа», используя кнопку`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

### Пример исходного кода для простого добавления документа с использованием Aspose.Words для .NET

Вот полный исходный код функции «Простое добавление документа» на C# с использованием Aspose.Words для .NET:

```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Добавьте исходный документ к целевому документу, не используя дополнительных параметров.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.SimpleAppendDocument.docx");
```

Вот и все! Вы успешно реализовали функцию простого добавления документа с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенное содержимое с сохранением исходного форматирования.