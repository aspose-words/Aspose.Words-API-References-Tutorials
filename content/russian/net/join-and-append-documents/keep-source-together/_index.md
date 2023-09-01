---
title: Храните исходный код вместе
linktitle: Храните исходный код вместе
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать Aspose.Words для .NET для объединения и добавления документов Word, сохраняя при этом исходное содержимое вместе с целевым документом.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/keep-source-together/
---

Это руководство проведет вас через процесс использования функции Keep Source Together в Aspose.Words for .NET. Эта функция позволяет объединять и добавлять несколько документов Word, сохраняя при этом содержимое исходного документа вместе с содержимым целевого документа. 

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

 Далее вам необходимо загрузить исходные и целевые документы с помощью Aspose.Words.`Document` сорт. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Шаг 3. Установите исходный документ так, чтобы он отображался после содержимого целевого документа.

 Чтобы гарантировать, что исходный документ появится сразу после содержимого целевого документа, вам необходимо установить параметр`SectionStart` свойство первого раздела исходного документа на`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Шаг 4. Установите форматирование абзаца «Сохранить дальше» для исходного документа.

 Чтобы сохранить абзацы в исходном документе вместе, вы можете перебрать каждый абзац в документе и установить`KeepWithNext` собственность`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Шаг 5. Добавьте исходный документ в целевой документ

 Теперь вы можете добавить исходный документ к целевому документу, используя команду`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр гарантирует, что исходное форматирование сохраняется во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 6: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией «Сохранить исходный код» с помощью`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Пример исходного кода для Keep Source Together с использованием Aspose.Words для .NET 

Вот полный исходный код функции «Сохранить исходный код вместе» на C# с использованием Aspose.Words для .NET:


```csharp
	// Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Установите исходный документ так, чтобы он отображался сразу после содержимого целевого документа.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Вот и все! Вы успешно реализовали функцию «Сохранить исходный код вместе», используя Aspose.Words для .NET. Окончательный документ будет содержать объединенное содержимое, при этом абзацы исходного документа будут сохранены вместе.