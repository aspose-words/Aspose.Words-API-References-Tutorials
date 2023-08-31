---
title: Заголовки ссылок Нижние колонтитулы
linktitle: Заголовки ссылок Нижние колонтитулы
second_title: API обработки документов Aspose.Words
description: Узнайте, как связывать верхние и нижние колонтитулы при присоединении и добавлении документов Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/link-headers-footers/
---

Это руководство проведет вас через процесс использования функции Link Headers Footers в Aspose.Words для .NET. Эта функция позволяет вам объединять и добавлять несколько документов Word, связывая верхние и нижние колонтитулы исходного документа с предыдущим разделом в целевом документе.

## Предпосылки

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET установлен. Вы можете загрузить его с веб-сайта Aspose или установить через NuGet.
2. Visual Studio или любая другая среда разработки C#.

## Шаг 1: Инициализируйте каталоги документов

 Во-первых, вам нужно указать путь к папке с документами. Измените значение параметра`dataDir`переменная на путь, где находятся ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходный и целевой документы

 Далее вам нужно загрузить исходный и конечный документы с помощью Aspose.Words.`Document` сорт. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Установите добавленный документ для отображения на новой странице

 Чтобы содержимое исходного документа отображалось на новой странице целевого документа, необходимо установить`SectionStart` свойство первого раздела в исходном документе на`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Шаг 4. Свяжите верхние и нижние колонтитулы с предыдущим разделом

 Чтобы связать верхние и нижние колонтитулы исходного документа с предыдущим разделом целевого документа, вы можете использовать`LinkToPrevious` метод`HeadersFooters` коллекция. Проходя мимо`true` в качестве параметра вы переопределяете любые существующие верхние или нижние колонтитулы в исходном документе.

```csharp
srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
```

## Шаг 5: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр обеспечивает сохранение исходного форматирования во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 6: Сохраните окончательный документ

 Наконец, сохраните объединенный документ со связанными верхними и нижними колонтитулами, используя`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

### Пример исходного кода для нижних колонтитулов заголовков ссылок с использованием Aspose.Words для .NET 

Вот полный исходный код функции «Связать заголовки и нижние колонтитулы» на C# с использованием Aspose.Words для .NET:


```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Установите добавленный документ, чтобы он отображался на новой странице.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Свяжите верхние и нижние колонтитулы в исходном документе с предыдущим разделом.
	// Это переопределит любые верхние или нижние колонтитулы, уже найденные в исходном документе.
	srcDoc.FirstSection.HeadersFooters.LinkToPrevious(true);
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.LinkHeadersFooters.docx");
```

Вот и все! Вы успешно внедрили функцию Link Headers Footers с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенное содержимое с верхними и нижними колонтитулами из исходного документа, связанного с предыдущим разделом в целевом документе.