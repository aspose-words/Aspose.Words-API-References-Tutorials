---
title: Вставить документ при замене
linktitle: Вставить документ при замене
second_title: API обработки документов Aspose.Words
description: Узнайте, как легко вставить один документ Word в другой с помощью Aspose.Words for .NET, с помощью нашего подробного пошагового руководства. Идеально подходит для разработчиков, стремящихся оптимизировать обработку документов.
type: docs
weight: 10
url: /ru/net/clone-and-combine-documents/insert-document-at-replace/
---
## Введение

Привет, мастера документации! Вы когда-нибудь погружались в код, пытаясь понять, как легко вставить один документ Word в другой? Не бойтесь, сегодня мы погрузимся в мир Aspose.Words for .NET, чтобы упростить эту задачу. Мы рассмотрим подробное пошаговое руководство о том, как использовать эту мощную библиотеку для вставки документов в определенные точки во время операции поиска и замены. Готовы стать мастером Aspose.Words? Давайте начнем!

## Предварительные условия

Прежде чем мы перейдем к коду, вам необходимо кое-что предусмотреть:

-  Visual Studio: убедитесь, что на вашем компьютере установлена Visual Studio. Если у вас его еще нет, вы можете скачать его с[здесь](https://visualstudio.microsoft.com/).
-  Aspose.Words для .NET: вам понадобится библиотека Aspose.Words. Вы можете получить его из[Веб-сайт Aspose](https://releases.aspose.com/words/net/).
- Базовые знания C#. Базовое понимание C# и .NET поможет вам следовать этому руководству.

Ладно, разобравшись с этим, давайте запачкаем руки кодом!

## Импортировать пространства имен

Прежде всего, нам нужно импортировать необходимые пространства имен для работы с Aspose.Words. Это похоже на сбор всех ваших инструментов перед началом проекта. Добавьте эти директивы using в начало вашего файла C#:

```csharp
using System;
using System.Text.RegularExpressions;
using Aspose.Words;
using Aspose.Words.Replacing;
using Aspose.Words.Tables;
```

Теперь, когда у нас есть необходимые предпосылки, давайте разобьем процесс на небольшие этапы. Каждый шаг имеет решающее значение и приближает нас к нашей цели.

## Шаг 1. Настройка каталога документов

Во-первых, нам нужно указать каталог, в котором хранятся наши документы. Это похоже на подготовку сцены перед большим представлением.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

 Заменять`"YOUR DOCUMENT DIRECTORY"` с путем к вашему каталогу. Здесь ваши документы будут жить и дышать.

## Шаг 2. Загрузите основной документ

Далее загружаем основной документ, в который хотим вставить еще один документ. Думайте об этом как о нашей основной сцене, на которой будут происходить все действия.

```csharp
Document mainDoc = new Document(dataDir + "Document insertion 1.docx");
```

Этот код загружает основной документ из указанного каталога.

## Шаг 3. Установите параметры поиска и замены

Чтобы найти конкретное место, куда мы хотим вставить наш документ, мы используем функцию поиска и замены. Это похоже на использование карты для поиска точного места для нашего нового дополнения.

```csharp
FindReplaceOptions options = new FindReplaceOptions
{
    Direction = FindReplaceDirection.Backward,
    ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

Здесь мы устанавливаем обратное направление и указываем собственный обработчик обратного вызова, который мы определим далее.

## Шаг 4. Выполните операцию замены

Теперь мы говорим нашему основному документу искать определенный текст-заполнитель и ничем его не заменять, используя при этом наш собственный обратный вызов для вставки другого документа.

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

Этот код выполняет операцию поиска и замены, а затем сохраняет обновленный документ.

## Шаг 5. Создайте собственный обработчик обратного вызова с заменой

Наш собственный обработчик обратного вызова — это то место, где происходит волшебство. Этот обработчик будет определять, как будет выполняться вставка документа во время операции поиска и замены.

```csharp
private class InsertDocumentAtReplaceHandler : IReplacingCallback
{
    ReplaceAction IReplacingCallback.Replacing(ReplacingArgs args)
    {
        Document subDoc = new Document(dataDir + "Document insertion 2.docx");

        // Вставьте документ после абзаца, содержащего совпадающий текст.
        Paragraph para = (Paragraph)args.MatchNode.ParentNode;
        InsertDocument(para, subDoc);

        // Удалите абзац с совпадающим текстом.
        para.Remove();
        return ReplaceAction.Skip;
    }
}
```

Здесь мы загружаем документ, который нужно вставить, а затем вызываем вспомогательный метод для выполнения вставки.

## Шаг 6. Определите метод вставки документа

Последняя часть нашей головоломки — это метод, который фактически вставляет документ в указанное место.

```csharp
private static void InsertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.NodeType == NodeType.Paragraph || insertionDestination.NodeType == NodeType.Table)
	{
		CompositeNode destinationParent = insertionDestination.ParentNode;

		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.Document, ImportFormatMode.KeepSourceFormatting);

		// Пройдите по всем узлам уровня блока в теле раздела,
		// затем клонируйте и вставьте каждый узел, который не является последним пустым абзацем раздела.
		foreach (Section srcSection in docToInsert.Sections.OfType<Section>())
		foreach (Node srcNode in srcSection.Body)
		{
			if (srcNode.NodeType == NodeType.Paragraph)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.IsEndOfSection && !para.HasChildNodes)
					continue;
			}

			Node newNode = importer.ImportNode(srcNode, true);

			destinationParent.InsertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new ArgumentException("The destination node should be either a paragraph or table.");
	}
}
```

Этот метод обеспечивает импорт узлов из вставляемого документа и размещение их в нужном месте основного документа.

## Заключение

И вот оно! Подробное руководство по вставке одного документа в другой с помощью Aspose.Words for .NET. Выполнив эти шаги, вы сможете легко автоматизировать задачи сборки и обработки документов. Независимо от того, создаете ли вы систему управления документами или просто хотите оптимизировать рабочий процесс обработки документов, Aspose.Words — ваш верный помощник.

## Часто задаваемые вопросы

### Что такое Aspose.Words для .NET?
Aspose.Words for .NET — это мощная библиотека для программного управления документами Word. Он позволяет вам с легкостью создавать, изменять, конвертировать и обрабатывать документы Word.

### Могу ли я вставить несколько документов одновременно?
Да, вы можете изменить обработчик обратного вызова для обработки нескольких вставок, перебирая коллекцию документов.

### Доступна ли бесплатная пробная версия?
 Абсолютно! Вы можете скачать бесплатную пробную версию с[здесь](https://releases.aspose.com/).

### Как мне получить поддержку Aspose.Words?
Вы можете получить поддержку, посетив[Форум Aspose.Words](https://forum.aspose.com/c/words/8).

### Можно ли сохранить форматирование вставленного документа?
 Да,`NodeImporter` Класс позволяет указать, как обрабатывается форматирование при импорте узлов из одного документа в другой.