---
title: Держите источник вместе
linktitle: Держите источник вместе
second_title: API обработки документов Aspose.Words
description: Узнайте, как использовать Aspose.Words для .NET для объединения и добавления документов Word, сохраняя при этом исходный контент вместе с целевым документом.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/keep-source-together/
---

Это руководство проведет вас через процесс использования функции Keep Source Together в Aspose.Words для .NET. Эта функция позволяет вам объединять и добавлять несколько документов Word, сохраняя при этом содержимое исходного документа вместе с содержимым целевого документа. 

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
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Шаг 3. Настройте исходный документ так, чтобы он отображался после содержимого целевого документа.

 Чтобы исходный документ отображался сразу после содержимого целевого документа, необходимо установить`SectionStart` свойство первого раздела в исходном документе на`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Шаг 4. Установите форматирование абзаца «Сохранить со следующим» для исходного документа

 Чтобы сохранить абзацы в исходном документе вместе, вы можете выполнить итерацию по каждому абзацу в документе и установить`KeepWithNext` собственность на`true`.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Шаг 5: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт.`ImportFormatMode.KeepSourceFormatting` Параметр обеспечивает сохранение исходного форматирования во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Шаг 6: Сохраните окончательный документ

Наконец, сохраните объединенный документ с включенной функцией «Сохранить исходный код вместе» с помощью`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

### Пример исходного кода для Keep Source Together с использованием Aspose.Words для .NET 

Вот полный исходный код функции «Сохранить исходный код вместе» на C# с использованием Aspose.Words для .NET:


```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Настройте исходный документ так, чтобы он отображался сразу после содержимого целевого документа.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		para.ParagraphFormat.KeepWithNext = true;
	}
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

Вот и все! Вы успешно внедрили функцию Keep Source Together с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенное содержимое с сохраненными вместе абзацами исходного документа.