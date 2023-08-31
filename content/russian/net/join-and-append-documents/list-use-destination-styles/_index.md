---
title: Получение списка стилей назначения использования
linktitle: Получение списка стилей назначения использования
second_title: API обработки документов Aspose.Words
description: Узнайте, как объединять и добавлять документы Word, сохраняя при этом стили списка целевых документов, используя Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/join-and-append-documents/list-use-destination-styles/
---

Это руководство проведет вас через процесс использования функции List Use Destination Styles в Aspose.Words for .NET. Эта функция позволяет объединять и добавлять документы Word, используя стили списка целевого документа.

## Предварительные условия

Прежде чем начать, убедитесь, что у вас есть следующее:

1. Aspose.Words для .NET установлен. Вы можете скачать его с веб-сайта Aspose или установить через NuGet.
2. Visual Studio или любая другая среда разработки C#.

## Шаг 1. Инициализируйте каталоги документов

 Во-первых, вам нужно установить путь к каталогу вашего документа. Измените значение параметра`dataDir`переменная пути, по которому расположены ваши документы.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Шаг 2. Загрузите исходные и целевые документы

 Далее вам необходимо загрузить исходные и целевые документы с помощью Aspose.Words.`Document` сорт. Обновите имена файлов в`Document` конструктор в соответствии с именами ваших документов.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Шаг 3. Установите для исходного документа продолжение после целевого документа

 Чтобы гарантировать, что содержимое исходного документа продолжится после окончания целевого документа, вам необходимо установить параметр`SectionStart` свойство первого раздела исходного документа на`SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Шаг 4. Обработка форматирования списка

Чтобы справиться с форматированием списка, вы будете перебирать каждый абзац исходного документа и проверять, является ли он элементом списка. Если это так, вы сравните идентификатор списка с существующими списками в целевом документе. Если список с таким же идентификатором существует, вы создадите копию списка в исходном документе и обновите формат списка абзаца, чтобы использовать скопированный список.

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

## Шаг 5. Добавьте исходный документ в целевой документ

 Теперь вы можете добавить исходный документ к целевому документу, используя команду`AppendDocument` метод`Document` сорт.`ImportFormatMode.UseDestinationStyles` Параметр гарантирует, что стили списка целевого документа будут использоваться во время операции добавления.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Шаг 6: Сохраните окончательный документ

 Наконец, сохраните объединенный документ с включенной функцией «Использовать список стилей назначения», используя`Save` метод`Document` сорт.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Пример исходного кода для использования стилей назначения списка с использованием Aspose.Words для .NET 

Вот полный исходный код функции «Список использования целевых стилей» на C# с использованием Aspose.Words для .NET:


```csharp
	//Путь к каталогу ваших документов
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	//Настройте исходный документ так, чтобы он продолжался сразу после окончания целевого документа.
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
				// Недавно скопированный список для этого идентификатора уже существует. Получите сохраненный список,
				// и используйте его в текущем абзаце.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Добавьте копию этого списка в документ и сохраните его для дальнейшего использования.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Установите список этого абзаца в скопированный список.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Добавьте исходный документ в конец целевого документа.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

Вот и все! Вы успешно реализовали функцию использования стилей назначения списка с помощью Aspose.Words для .NET. Окончательный документ будет содержать объединенное содержимое со стилями списка из целевого документа.