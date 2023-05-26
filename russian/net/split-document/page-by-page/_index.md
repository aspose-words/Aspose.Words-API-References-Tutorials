---
title: Постранично
linktitle: Постранично
second_title: Справочник по API Aspose.Words для .NET
description: Пошаговое руководство по объяснению исходного кода C# функции Aspose.Words Page by Page для .NET
type: docs
weight: 10
url: /ru/net/split-document/page-by-page/
---

В этом руководстве мы расскажем, как разделить документ Word на отдельные страницы с помощью функции «Постранично» в Aspose.Words для .NET. Выполните следующие шаги, чтобы понять исходный код и получить отдельные документы для каждой страницы.

## Шаг 1: Загрузка документа

Для начала укажите каталог для вашего документа и загрузите документ в объект Document. Вот как:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Шаг 2: Разделите документ по страницам

Теперь мы пройдемся по каждой странице документа и разобьем документ на отдельные страницы. Вот как:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Сохраняйте каждую страницу как отдельный документ.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

## Шаг 3. Объедините документы

Если у вас есть отдельные документы для каждой страницы, вы можете объединить их, если это необходимо. Вот как:

```csharp
MergeDocuments();
```

### Пример исходного кода для страницы за страницей с использованием Aspose.Words для .NET

Вот полный исходный код функции «Страница за страницей» Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	int pageCount = doc.PageCount;

	for (int page = 0; page < pageCount; page++)
	{
		// Сохраняйте каждую страницу как отдельный документ.
		Document extractedPage = doc.ExtractPages(page, 1);
		extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
	}
	

	MergeDocuments();

```

С помощью этого кода вы сможете разбить документ Word на отдельные страницы, используя Aspose.Words для .NET. При необходимости вы также можете объединить отдельные документы.

