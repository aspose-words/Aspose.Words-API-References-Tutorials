---
title: Присоединяйтесь к непрерывному
linktitle: Присоединяйтесь к непрерывному
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как непрерывно соединять два документа с сохранением форматирования с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/join-continuous/
---

В этом руководстве объясняется, как непрерывно соединять два документа с помощью Aspose.Words для .NET. Предоставленный исходный код демонстрирует, как добавить документ в конец другого документа, сохранив при этом исходное форматирование.

## Шаг 1: Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words for .NET. Вы можете загрузить его с официального веб-сайта Aspose или использовать менеджер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором находятся исходный и конечный документы.

## Шаг 2. Откройте исходный и конечный документы

 Откройте исходный и конечный документы с помощью`Document` конструктор класса. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Настройте начало непрерывного участка

 Чтобы исходный документ отображался сразу после содержимого целевого документа, установите`SectionStart` свойство первого раздела в исходном документе на`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Шаг 4: Добавьте исходный документ

 Добавьте исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт. Установите режим формата импорта на`ImportFormatMode.KeepSourceFormatting`чтобы сохранить исходные стили из исходного документа.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5: Сохраните измененный документ

 Наконец, сохраните измененный целевой документ, используя`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

На этом реализация непрерывного объединения двух документов с использованием Aspose.Words для .NET завершена.

### Пример исходного кода для непрерывного соединения с использованием Aspose.Words для .NET 

```csharp
	// Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Сделайте так, чтобы документ отображался сразу после содержимого целевого документа.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Добавьте исходный документ, используя оригинальные стили, найденные в исходном документе.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```