---
title: Заголовки ссылок, нижние колонтитулы
linktitle: Заголовки ссылок, нижние колонтитулы
second_title: API обработки документов Aspose.Words
description: Узнайте, как связывать верхние и нижние колонтитулы при объединении и добавлении документов Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/link-headers-footers/
---

Это руководство проведет вас через процесс использования функции нижних колонтитулов ссылок в Aspose.Words для .NET. Эта функция позволяет объединять и добавлять несколько документов Word, связывая при этом верхние и нижние колонтитулы исходного документа с предыдущим разделом целевого документа.

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

Далее вам необходимо загрузить исходные и целевые документы с помощью Aspose.Words.`Document` класс. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Настройте добавленный документ для отображения на новой странице.

 Чтобы содержимое исходного документа отображалось на новой странице целевого документа, необходимо установить параметр`SectionStart` свойство первого раздела исходного документа на`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Шаг 4. Свяжите верхние и нижние колонтитулы с предыдущим разделом

 Чтобы связать верхние и нижние колонтитулы исходного документа с предыдущим разделом целевого документа, вы можете использовать команду`LinkToPrevious` метод`HeadersFooters` коллекция. Проходя мимо`true` В качестве параметра вы переопределяете любые существующие верхние и нижние колонтитулы в исходном документе.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Шаг 5. Добавьте исходный документ в целевой документ

 Теперь вы можете добавить исходный документ к целевому документу, используя команду`AppendDocument` метод`Document` класс.`ImportFormatMode.KeepSourceFormatting` Параметр гарантирует, что исходное форматирование сохраняется во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 6: Сохраните окончательный документ

 Наконец, сохраните объединенный документ со связанными верхними и нижними колонтитулами, используя команду`Save` метод`Document` класс.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Пример исходного кода для нижних колонтитулов заголовков ссылок с использованием Aspose.Words для .NET 

Вот полный исходный код функции «Нижние колонтитулы заголовков ссылок» на C# с использованием Aspose.Words для .NET:


```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Настройте добавленный документ на новую страницу.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Свяжите верхние и нижние колонтитулы исходного документа с предыдущим разделом.
	// Это переопределит все верхние и нижние колонтитулы, уже найденные в исходном документе.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Вот и все! Вы успешно реализовали функцию нижних колонтитулов заголовков ссылок с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенное содержимое с верхними и нижними колонтитулами исходного документа, связанными с предыдущим разделом целевого документа.