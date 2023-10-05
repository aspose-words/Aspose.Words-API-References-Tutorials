---
title: Добавить с параметрами формата импорта
linktitle: Добавить с параметрами формата импорта
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить документ с параметрами формата импорта с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/append-with-import-format-options/
---

В этом руководстве объясняется, как использовать Aspose.Words для .NET для добавления содержимого одного документа в другой с параметрами формата импорта. Предоставленный исходный код демонстрирует, как открыть исходный и целевой документы, указать параметры формата импорта и добавить исходный документ к целевому документу.

## Шаг 1. Настройте проект

Убедитесь, что у вас есть следующие предварительные условия:

-  Установлена библиотека Aspose.Words для .NET. Вы можете скачать его с[Aspose.Releases]https://releases.aspose.com/words/net/ или используйте менеджер пакетов NuGet для его установки.
- Путь к каталогу документов, в котором расположены исходные и целевые документы.

## Шаг 2. Откройте исходный и целевой документы.

 Откройте исходный и целевой документы с помощью`Document` конструктор класса. Заменять`"YOUR DOCUMENT DIRECTORY"` с фактическим путем к каталогу вашего документа.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source with list.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Шаг 3. Укажите параметры формата импорта

 Создайте экземпляр`ImportFormatOptions` class для указания параметров формата импорта. В этом примере мы используем`KeepSourceNumbering` Свойство, гарантирующее использование нумерации из исходного документа в случае конфликтов с целевым документом.

```csharp
ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
```

## Шаг 4. Добавьте исходный документ в целевой документ.

 Использовать`AppendDocument` метод целевого документа для добавления исходного документа. Проходить`ImportFormatMode.UseDestinationStyles` в качестве второго параметра для использования стилей и форматирования целевого документа.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);
```

## Шаг 5. Сохраните целевой документ.

 Наконец, сохраните измененный целевой документ, используя команду`Save` метод`Document` объект.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.AppendWithImportFormatOptions.docx");
```

На этом реализация добавления к документу параметров формата импорта с использованием Aspose.Words для .NET завершена.

### Пример исходного кода для добавления с параметрами формата импорта с использованием Aspose.Words для .NET 

```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source with list.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Укажите, что если нумерация в исходном и целевом документах противоречит,
	//тогда будет использована нумерация из исходного документа.
	ImportFormatOptions options = new ImportFormatOptions { KeepSourceNumbering = true };
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, options);

```