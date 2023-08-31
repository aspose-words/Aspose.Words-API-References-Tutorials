---
title: Перезапустить нумерацию страниц
linktitle: Перезапустить нумерацию страниц
second_title: API обработки документов Aspose.Words
description: Узнайте, как перезапустить нумерацию страниц при объединении и добавлении документов Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/restart-page-numbering/
---

Это руководство проведет вас через процесс использования функции «Перезапустить нумерацию страниц» в Aspose.Words для .NET. Эта функция позволяет объединять и добавлять документы Word при перезапуске нумерации страниц в исходном документе.

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

## Шаг 3. Установите исходный документ для перезапуска нумерации страниц

 Чтобы перезапустить нумерацию страниц в исходном документе, необходимо установить`SectionStart` свойство первого раздела в исходном документе на`SectionStart.NewPage` и установите`RestartPageNumbering` собственность на`true`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
```

## Шаг 4: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр обеспечивает сохранение исходного форматирования во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией «Перезапустить нумерацию страниц».`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

### Пример исходного кода для перезапуска нумерации страниц с использованием Aspose.Words для .NET

Вот полный исходный код функции «Перезапустить нумерацию страниц» на C# с использованием Aspose.Words для .NET:
 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	srcDoc.FirstSection.PageSetup.RestartPageNumbering = true;
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.RestartPageNumbering.docx");
```

Вот и все! Вы успешно реализовали функцию «Перезапустить нумерацию страниц» с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенный контент с нумерацией страниц в исходном документе.