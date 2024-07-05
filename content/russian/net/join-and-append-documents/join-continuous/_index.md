---
title: Присоединяйтесь к непрерывному
linktitle: Присоединяйтесь к непрерывному
second_title: API обработки документов Aspose.Words
description: Узнайте, как непрерывно объединять два документа, сохраняя форматирование, с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/join-continuous/
---

В этом руководстве объясняется, как непрерывно объединять два документа с помощью Aspose.Words для .NET. Предоставленный исходный код демонстрирует, как добавить документ в конец другого документа, сохраняя исходное форматирование.

## Шаг 1. Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

-  Установлена библиотека Aspose.Words для .NET. Вы можете скачать его с[Aspose.Releases]https://releases.aspose.com/words/net/ или используйте менеджер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором расположены исходные и целевые документы.

## Шаг 2. Откройте исходный и целевой документы.

 Откройте исходный и целевой документы с помощью`Document` конструктор класса. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Настройте непрерывный запуск раздела

Чтобы исходный документ отображался сразу после содержимого целевого документа, установите параметр`SectionStart` свойство первого раздела исходного документа на`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Шаг 4. Добавьте исходный документ

 Добавьте исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт. Установите режим формата импорта на`ImportFormatMode.KeepSourceFormatting` чтобы сохранить исходные стили из исходного документа.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5. Сохраните измененный документ.

Наконец, сохраните измененный целевой документ, используя команду`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```

На этом реализация непрерывного объединения двух документов с помощью Aspose.Words для .NET завершена.

### Пример исходного кода для непрерывного соединения с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Сделайте так, чтобы документ отображался сразу после содержимого целевого документа.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Добавьте исходный документ, используя исходные стили, найденные в исходном документе.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinContinuous.docx");
```