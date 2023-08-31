---
title: Игнорировать верхний колонтитул
linktitle: Игнорировать верхний колонтитул
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить документ, игнорируя содержимое верхнего и нижнего колонтитула, с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/ignore-header-footer/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для добавления документа, игнорируя содержимое верхнего и нижнего колонтитула. Предоставленный исходный код демонстрирует, как настроить параметры формата импорта, чтобы исключить верхний и нижний колонтитулы во время процесса добавления.

## Шаг 1. Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words для .NET. Вы можете скачать его с[Aspose.Releases]https://releases.aspose.com/words/net/ или используйте менеджер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором расположены исходные и целевые документы.

## Шаг 2. Откройте исходный и целевой документы.

 Откройте исходный и целевой документы с помощью`Document` конструктор класса. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDocument = new Document(dataDir + "Document source.docx");
Document dstDocument = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Настройте параметры формата импорта

 Создайте экземпляр`ImportFormatOptions`класс и установите`IgnoreHeaderFooter` собственность`false`. Это гарантирует, что содержимое верхнего и нижнего колонтитула будет включено в процесс добавления.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
```

## Шаг 4. Добавьте исходный документ в целевой документ.

 Использовать`AppendDocument`метод целевого документа для добавления исходного документа. Проходить`ImportFormatMode.KeepSourceFormatting` в качестве второго параметра и параметры формата импорта в качестве третьего параметра.

```csharp
dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
```

## Шаг 5. Сохраните целевой документ.

 Наконец, сохраните измененный целевой документ, используя команду`Save` метод`Document` объект.

```csharp
dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```

На этом завершается реализация добавления документа с игнорированием содержимого верхнего и нижнего колонтитула с использованием Aspose.Words для .NET.

### Пример исходного кода для «Игнорировать нижний колонтитул» с использованием Aspose.Words для .NET 

```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDocument = new Document(dataDir + "Document source.docx");
	Document dstDocument = new Document(dataDir + "Northwind traders.docx");
	ImportFormatOptions importFormatOptions = new ImportFormatOptions { IgnoreHeaderFooter = false };
	dstDocument.AppendDocument(srcDocument, ImportFormatMode.KeepSourceFormatting, importFormatOptions);
	dstDocument.Save(dataDir + "JoinAndAppendDocuments.IgnoreHeaderFooter.docx");
```