---
title: По разделам
linktitle: По разделам
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как разделить документ Word на отдельные разделы с помощью Aspose.Words для .NET с полным примером кода.
type: docs
weight: 10
url: /ru/net/split-document/by-sections/
---

В этом примере мы покажем вам, как разделить документ Word на отдельные разделы, используя функцию «По разделам» Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и получить отдельные документы для каждого раздела.

## Шаг 1: Загрузка документа

Для начала нам нужно указать каталог вашего документа и загрузить документ в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Шаг 2: Разделите документ на разделы

Теперь мы пройдемся по каждому разделу документа и разобьем документ на более мелкие части, раздел за разделом. Вот как это сделать:

```csharp
for (int i = 0; i < doc. Sections. Count; i++)
{
// Разделите документ на более мелкие части, в данном случае разделив его по разделам.
Section section = doc.Sections[i].Clone();

Document newDoc = new Document();
newDoc.Sections.Clear();

Section newSection = (Section) newDoc.ImportNode(section, true);
newDoc.Sections.Add(newSection);

// Сохраните каждый раздел как отдельный документ.
newDoc.Save(dataDir + $"SplitDocument.ParSections_{i}.docx");
}
```

### Пример исходного кода для разделов с использованием Aspose.Words для .NET

Вот полный исходный код функции «По разделам» Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	for (int i = 0; i < doc.Sections.Count; i++)
	{
		// Разделите документ на более мелкие части, в данном случае на разделы.
		Section section = doc.Sections[i].Clone();

		Document newDoc = new Document();
		newDoc.Sections.Clear();

		Section newSection = (Section) newDoc.ImportNode(section, true);
		newDoc.Sections.Add(newSection);

		// Сохраните каждый раздел как отдельный документ.
		newDoc.Save(dataDir + $"SplitDocument.BySections_{i}.docx");
	}

```

С помощью этого кода вы сможете разделить документ Word на отдельные разделы, используя Aspose.Words для .NET.

Теперь вы можете легко работать с конкретными разделами.

