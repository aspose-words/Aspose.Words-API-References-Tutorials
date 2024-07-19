---
title: Сохраняйте нумерацию источников
linktitle: Сохраняйте нумерацию источников
second_title: API обработки документов Aspose.Words
description: Узнайте, как импортировать документы с сохранением форматирования с помощью Aspose.Words для .NET. Пошаговое руководство с примерами кода.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/keep-source-numbering/
---
## Введение

 При работе с Aspose.Words для .NET импорт документов из одного источника в другой с сохранением форматирования можно эффективно выполнить с помощью`NodeImporter` сорт. Это руководство проведет вас через весь процесс шаг за шагом.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:
- Visual Studio установлена на вашем компьютере.
-  Aspose.Words для .NET установлен. Если нет, загрузите его с[здесь](https://releases.aspose.com/words/net/).
- Базовые знания программирования на C# и .NET.

## Импортировать пространства имен

Сначала включите в свой проект необходимые пространства имен:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

## Шаг 1. Настройте свой проект

Начните с создания нового проекта C# в Visual Studio и установите Aspose.Words через диспетчер пакетов NuGet.

## Шаг 2. Инициализация документов
Создайте экземпляры источника (`srcDoc`) и пункт назначения (`dstDoc`) документы.

```csharp
// Путь к каталогу ваших документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Northwind traders.docx");
```

## Шаг 3. Настройте параметры импорта
Настройте параметры импорта, чтобы сохранить исходное форматирование, включая нумерованные абзацы.

```csharp
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepSourceFormatting,
	importFormatOptions);
```

## Шаг 4. Импортируйте абзацы
Перебирайте абзацы исходного документа и импортируйте их в целевой документ.

```csharp
ParagraphCollection srcParas = srcDoc.FirstSection.Body.Paragraphs;
foreach (Paragraph srcPara in srcParas)
{
    Node importedNode = importer.ImportNode(srcPara, false);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}
```

## Шаг 5: Сохраните документ
Сохраните объединенный документ в нужном месте.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceNumbering.docx");
```

## Заключение

 В заключение, использование Aspose.Words для .NET для импорта документов с сохранением форматирования очень просто с помощью`NodeImporter` сорт. Этот метод гарантирует, что ваши документы сохранят свой первоначальный вид и структуру.

## Часто задаваемые вопросы

### Могу ли я импортировать документы с разными стилями форматирования?
 Да,`NodeImporter` Класс поддерживает импорт документов с различными стилями форматирования.

### Что делать, если мои документы содержат сложные таблицы и изображения?
Aspose.Words for .NET обрабатывает сложные структуры, такие как таблицы и изображения, во время операций импорта.

### Совместим ли Aspose.Words со всеми версиями .NET?
Aspose.Words поддерживает версии .NET Framework и .NET Core для бесшовной интеграции.

### Как устранить ошибки при импорте документов?
Используйте блоки try-catch для обработки исключений, которые могут возникнуть в процессе импорта.

### Где я могу найти более подробную документацию по Aspose.Words для .NET?
 Посетить[документация](https://reference.aspose.com/words/net/) подробные руководства и ссылки на API.
