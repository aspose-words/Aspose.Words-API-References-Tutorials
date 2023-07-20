---
title: Добавить с параметрами формата импорта
linktitle: Добавить с параметрами формата импорта
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить в документ параметры формата импорта с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/append-with-import-format-options/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для добавления содержимого одного документа в другой с параметрами формата импорта. В предоставленном исходном коде показано, как открыть исходный и целевой документы, указать параметры формата импорта и добавить исходный документ к целевому документу.

## Шаг 1: Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

- Установлена библиотека Aspose.Words for .NET. Вы можете скачать его с[Aspose.Releases]https://releases.aspose.com/words/net/ или используйте диспетчер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором находятся исходный и конечный документы.

## Шаг 2. Откройте исходный и конечный документы

 Откройте исходный и конечный документы с помощью`Document` конструктор класса. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к вашему каталогу документов.

```csharp
// Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Шаг 3. Укажите параметры формата импорта.

 Создайте экземпляр`ImportFormatOptions` класс, чтобы указать параметры формата импорта. В этом примере мы используем`KeepSourceNumbering` свойство, чтобы обеспечить использование нумерации из исходного документа в случае возникновения конфликтов с целевым документом.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Шаг 4. Добавьте исходный документ к целевому документу.

 Использовать`AppendDocument`метод целевого документа для добавления исходного документа. Проходить`ImportFormatMode.UseDestinationStyles` в качестве второго параметра для использования стилей и форматирования целевого документа.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Шаг 5: Сохраните целевой документ

 Наконец, сохраните измененный целевой документ, используя`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

На этом реализация добавления документа с параметрами формата импорта с помощью Aspose.Words for .NET завершена.

### Пример исходного кода для добавления с параметрами формата импорта с использованием Aspose.Words для .NET 

```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Укажите, что если нумерация в исходном и целевом документах конфликтует,
	// тогда будет использоваться нумерация из исходного документа.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```