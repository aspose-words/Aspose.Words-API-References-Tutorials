---
title: Отсоединить заголовки и нижние колонтитулы
linktitle: Отсоединить заголовки и нижние колонтитулы
second_title: API обработки документов Aspose.Words
description: Узнайте, как объединять и добавлять документы Word, отсоединяя верхние и нижние колонтитулы, с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/unlink-headers-footers/
---

Это руководство проведет вас через процесс использования функции «Отсоединить верхние и нижние колонтитулы» в Aspose.Words для .NET. Эта функция позволяет объединять и добавлять документы Word, отсоединяя верхние и нижние колонтитулы от исходного документа.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET установлен. Вы можете скачать его с веб-сайта Aspose или установить через NuGet.
2. Visual Studio или любая другая среда разработки C#.

## Шаг 1. Инициализируйте каталоги документов

 Во-первых, вам нужно установить путь к каталогу вашего документа. Измените значение параметра`dataDir` переменная пути, по которому расположены ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходные и целевые документы

 Далее вам необходимо загрузить исходные и целевые документы с помощью Aspose.Words.`Document` сорт. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Отсоедините верхние и нижние колонтитулы в исходном документе

 Чтобы отсоединить верхние и нижние колонтитулы исходного документа от продолжения верхних и нижних колонтитулов целевого документа, необходимо установить параметр`LinkToPrevious` собственность`HeadersFooters` коллекцию в первом разделе исходного документа, чтобы`false`.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
```

## Шаг 4. Добавьте исходный документ в целевой документ

 Теперь вы можете добавить исходный документ к целевому документу, используя команду`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр гарантирует, что исходное форматирование сохраняется во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5. Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией «Отсоединить колонтитулы», используя`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

### Пример исходного кода для отключения заголовков и нижних колонтитулов с использованием Aspose.Words для .NET

Вот полный исходный код функции «Отсоединить верхние и нижние колонтитулы» на C# с использованием Aspose.Words для .NET:

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Чтобы остановить это, отсоедините верхние и нижние колонтитулы в исходном документе.
	// от продолжения верхних и нижних колонтитулов целевого документа.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(false);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.UnlinkHeadersFooters.docx");
```

Вот и все! Вы успешно реализовали функцию «Отсоединить верхние и нижние колонтитулы», используя Aspose.Words для .NET. Окончательный документ будет содержать объединенное содержимое с верхними и нижними колонтитулами исходного документа, не связанными с целевым документом.