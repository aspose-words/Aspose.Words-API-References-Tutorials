---
title: Добавить текст с закладкой в документ Word
linktitle: Добавить текст с закладкой в документ Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить текст из закладки в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/append-bookmarked-text/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Добавить текст с закладками» в библиотеке Aspose.Words для .NET. Эта функция позволяет добавлять текст, содержащийся в определенной закладке документа Word, в другой документ.

## Предварительные условия

- Базовые знания языка C#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1. Получение абзацев из закладки

 Прежде чем мы начнем добавлять текст закладки, нам нужно получить абзацы, содержащие начало и конец закладки. Это можно сделать, обратившись к`BookmarkStart` и`BookmarkEnd` свойства закладки:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Шаг 2. Проверьте родительские абзацы

Мы проверяем, имеют ли начальный и конечный абзацы допустимые родители, то есть действительно ли они принадлежат абзацу. Если нет, мы генерируем исключение:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Шаг 3. Проверьте родительские элементы абзацев

Мы проверяем, имеют ли начальный и конечный абзацы одного и того же родителя. Если нет, это означает, что абзацы не содержатся в одном разделе или документе, и мы выдаем исключение:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Шаг 4. Скопируйте абзацы

Мы перебираем узлы (абзацы) от начального абзаца до конечного абзаца. Для каждого узла мы создаем копию и импортируем ее в контекст целевого документа:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Пример исходного кода для добавления текста с закладками с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий добавление текста из закладки с помощью Aspose.Words для .NET:

```csharp

	// Это абзац, содержащий начало закладки.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Это абзац, содержащий конец закладки.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Ограничимся достаточно простым сценарием.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Мы хотим скопировать все абзацы от начального до конечного абзаца (включительно).
	// Следовательно, узел, на котором мы останавливаемся, находится после конечного абзаца.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		//Это создает копию текущего узла и импортирует ее (делает ее допустимой) в контексте.
		// документа назначения. Импорт означает правильную настройку стилей и идентификаторов списков.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию добавления текста с закладками в Aspose.Words для .NET. Мы следовали пошаговому руководству по получению абзацев из закладки, проверке родительских элементов и копированию абзацев в другой документ.

### Часто задаваемые вопросы по добавлению текста с закладками в документ Word

#### Вопрос 1: Каковы необходимые условия для использования функции «Добавить текст с закладками» в Aspose.Words для .NET?

О: Чтобы использовать функцию «Добавить текст с закладками» в Aspose.Words for .NET, вам необходимо иметь базовые знания языка C#. Вам также потребуется среда разработки .NET с установленной библиотекой Aspose.Words.

#### Вопрос 2. Как получить абзацы, содержащие начало и конец закладки в документе Word?

О: Чтобы получить абзацы, содержащие начало и конец закладки в документе Word, вы можете получить доступ к`BookmarkStart` и`BookmarkEnd` свойства закладки. Вот пример кода:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Вопрос 3. Что произойдет, если у начального и конечного абзацев нет допустимых родительских элементов?

О: Если начальный и конечный абзацы не имеют допустимых родительских элементов, то есть на самом деле они не являются абзацами, будет выдано исключение. В настоящее время эту ситуацию невозможно контролировать.
