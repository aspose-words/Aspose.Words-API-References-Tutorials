---
title: Присоединяйтесь к новой странице
linktitle: Присоединяйтесь к новой странице
second_title: API обработки документов Aspose.Words
description: Узнайте, как объединить два документа на новой странице, сохранив форматирование, с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/join-new-page/
---

В этом руководстве объясняется, как объединить два документа на новой странице с помощью Aspose.Words для .NET. Предоставленный исходный код демонстрирует, как добавить документ в конец другого документа, начиная добавленный документ на новой странице.

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

## Шаг 3. Настройте начало нового раздела страницы.

Чтобы начать добавленный документ на новой странице, установите`SectionStart` свойство первого раздела исходного документа на`SectionStart.NewPage`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
```

## Шаг 4. Добавьте исходный документ

Добавьте исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт. Установите режим формата импорта на`ImportFormatMode.KeepSourceFormatting` чтобы сохранить исходные стили из исходного документа.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 5. Сохраните измененный документ.

 Наконец, сохраните измененный целевой документ, используя команду`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```

На этом реализация объединения двух документов на новой странице с помощью Aspose.Words для .NET завершена.

### Пример исходного кода для присоединения к новой странице с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Northwind traders.docx");
	// Установите добавленный документ для начала на новой странице.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.NewPage;
	// Добавьте исходный документ, используя исходные стили, найденные в исходном документе.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.JoinNewPage.docx");
```