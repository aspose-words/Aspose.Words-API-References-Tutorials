---
title: Добавить текст с закладками в документ Word
linktitle: Добавить текст с закладками в документ Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как добавить текст из закладки в документ Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/append-bookmarked-text/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Добавить текст с закладками» в библиотеке Aspose.Words для .NET. Эта функция позволяет добавлять текст, содержащийся в определенной закладке документа Word, в другой документ.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: получение абзацев из закладки

 Прежде чем мы начнем добавлять текст закладки, нам нужно получить абзацы, содержащие начало и конец закладки. Это можно сделать, обратившись к`BookmarkStart` и`BookmarkEnd` свойства закладки:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

## Шаг 2: проверьте родительские абзацы

Мы проверяем, имеют ли начальный и конечный абзацы действительные родители, то есть действительно ли они принадлежат абзацу. Если нет, мы генерируем исключение:

```csharp
if (startPara == null || endPara == null)
throw new InvalidOperationException(
"The parent of the beginning or the end of the bookmark is not a paragrap

hey, this situation can't be handled yet.");
```

## Шаг 3: проверьте родителей абзацев

Мы проверяем, имеют ли начальный и конечный абзацы один и тот же родитель. Если нет, это означает, что абзацы не содержатся в одном и том же разделе или документе, и мы выбрасываем исключение:

```csharp
if (startPara.ParentNode != endPara.ParentNode)
throw new InvalidOperationException(
"Beginning and ending paragraphs have different parents, this situation cannot be handled yet.");
```

## Шаг 4: Скопируйте абзацы

Мы перебираем узлы (абзацы) от начального абзаца до конечного абзаца. Для каждого узла мы создаем копию и импортируем ее в контекст целевого документа:

```csharp
Node endNode = endPara.NextSibling;

for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
{
Node newNode = importer.ImportNode(curNode, true);

dstNode.AppendChild(newNode);
}
```

### Пример исходного кода для добавления текста в закладки с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий добавление текста из закладки с помощью Aspose.Words для .NET:

```csharp

	// Это абзац, который содержит начало закладки.
	Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;

	// Это абзац, который содержит конец закладки.
	Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;

	if (startPara == null || endPara == null)
		throw new InvalidOperationException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");

	// Ограничимся достаточно простым сценарием.
	if (startPara.ParentNode != endPara.ParentNode)
		throw new InvalidOperationException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");

	// Мы хотим скопировать все абзацы от начального абзаца до (включительно) конечного абзаца,
	// поэтому узел, на котором мы останавливаемся, находится после последнего абзаца.
	Node endNode = endPara.NextSibling;

	for (Node curNode = startPara; curNode != endNode; curNode = curNode.NextSibling)
	{
		// Это создает копию текущего узла и импортирует его (делает действительным) в контексте
		// документа назначения. Импорт означает правильную настройку стилей и идентификаторов списков.
		Node newNode = importer.ImportNode(curNode, true);

		dstNode.AppendChild(newNode);
	}

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию Append Bookmarked Text в Aspose.Words для .NET. Мы выполнили пошаговое руководство по получению абзацев из закладки, проверке родителей и копированию абзацев в другой документ.

### Часто задаваемые вопросы по добавлению текста с закладками в документ Word

#### Q1: Каковы предварительные условия для использования функции «Добавить текст с закладками» в Aspose.Words для .NET?

О: Чтобы использовать функцию "Добавить текст с закладками" в Aspose.Words для .NET, вам необходимо иметь базовые знания языка C#. Вам также потребуется среда разработки .NET с установленной библиотекой Aspose.Words.

#### Q2: Как получить абзацы, содержащие начало и конец закладки в документе Word?

 A: Чтобы получить абзацы, содержащие начало и конец закладки в документе Word, вы можете получить доступ к`BookmarkStart` и`BookmarkEnd` свойства закладки. Вот пример кода:

```csharp
Paragraph startPara = (Paragraph) srcBookmark.BookmarkStart.ParentNode;
Paragraph endPara = (Paragraph) srcBookmark.BookmarkEnd.ParentNode;
```

#### Q3: Что произойдет, если начальный и конечный абзацы не имеют допустимых родителей?

О: Если начальный и конечный абзацы не имеют допустимых родителей, т.е. они на самом деле не являются абзацами, будет выдано исключение. Эта ситуация не может управляться в настоящее время.
