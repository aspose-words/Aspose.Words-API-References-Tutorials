---
title: Показать Скрыть закладки
linktitle: Показать Скрыть закладки
second_title: Справочник по API Aspose.Words для .NET
description: Узнайте, как отображать или скрывать содержимое закладок с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/show-hide-bookmarked-content/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Показать скрытый закладной контент» в библиотеке Aspose.Words для .NET. Эта функция позволяет отображать или скрывать содержимое закладки в зависимости от определенного условия при объединении данных.

## Предпосылки

- Базовые знания языка С#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Получение закладки

 Мы используем`Bookmarks` свойство диапазона документа, чтобы получить конкретную закладку, на которой мы хотим показать или скрыть содержимое:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Шаг 2. Вставка полей слияния

 Мы используем конструктор документов`DocumentBuilder` чтобы вставить необходимые поля слияния. Эти поля слияния будут устанавливать условие для отображения или скрытия содержимого закладки в зависимости от значения параметра`showHide` переменная:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Шаг 3. Перемещение содержимого закладок

Перебираем содержимое закладки и перемещаем ее так, чтобы она появилась

isse перед закладкой. Это будет контролировать отображение или скрытие контента на основе указанного условия:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Шаг 4. Перемещение остального содержимого закладки

Мы перемещаем остальную часть содержимого закладки после закладки, используя конечный узел закладки в качестве точки вставки:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Шаг 5: Выполнение слияния

 Мы используем`Execute` метод документа`s `MailMerge` object to execute the merge using the bookmark name and the value of the `переменная showHide`:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Пример исходного кода для отображения содержимого с закладками с помощью Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий отображение или скрытие содержимого закладок с помощью Aspose.Words для .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD bookmark}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию Show Hide Bookmarked Content в Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы показать или скрыть содержимое закладки в зависимости от определенного условия при объединении данных.