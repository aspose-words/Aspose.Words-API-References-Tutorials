---
title: Список использования целевых стилей
linktitle: Список использования целевых стилей
second_title: API обработки документов Aspose.Words
description: Узнайте, как объединять и добавлять документы Word, сохраняя при этом стили списка целевого документа, используя Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/list-use-destination-styles/
---

Это руководство проведет вас через процесс использования функции «Список использования стилей назначения» в Aspose.Words для .NET. Эта функция позволяет объединять и добавлять документы Word, используя стили списка целевого документа.

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

## Шаг 3. Установите исходный документ для продолжения после целевого документа

 Чтобы содержимое исходного документа продолжалось после окончания целевого документа, необходимо установить`SectionStart` свойство первого раздела в исходном документе на`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Шаг 4. Обработайте форматирование списка

Чтобы справиться с форматированием списка, вы будете перебирать каждый абзац в исходном документе и проверять, является ли он элементом списка. Если это так, вы сравните идентификатор списка с существующими списками в целевом документе. Если список с таким же идентификатором существует, вы создадите копию списка в исходном документе и обновите формат списка абзаца, чтобы использовать скопированный список.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Шаг 5: добавьте исходный документ к целевому документу

 Теперь вы можете добавить исходный документ к целевому документу, используя`AppendDocument` метод`Document` сорт.`ImportFormatMode.UseDestinationStyles` Параметр обеспечивает использование стилей списка целевого документа во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Шаг 6: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией List Use Destination Styles с помощью`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Пример исходного кода для списка использования стилей назначения с использованием Aspose.Words для .NET 

Вот полный исходный код функции «Список использования стилей назначения» на C# с использованием Aspose.Words для .NET:


```csharp
	//Путь к вашему каталогу документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//Установите исходный документ, чтобы он продолжался сразу после окончания целевого документа.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Следите за созданными списками.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Проверьте, содержит ли целевой документ список с этим идентификатором. Если да, то это может
			//заставить два списка работать вместе. Вместо этого создайте копию списка в исходном документе.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// Новый скопированный список уже существует для этого идентификатора, извлеките сохраненный список,
				// и используйте его в текущем абзаце.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Добавьте копию этого списка в документ и сохраните ее для дальнейшего использования.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Установите список этого абзаца в скопированный список.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Добавить исходный документ в конец целевого документа.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Вот и все! Вы успешно внедрили функцию «Список использования целевых стилей» с помощью Aspose.Words для .NET. Конечный документ будет содержать объединенное содержимое со стилями списка из целевого документа.