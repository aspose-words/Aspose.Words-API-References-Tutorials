---
title: Показать скрыть закладки в документе Word
linktitle: Показать скрыть закладки в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как показать или скрыть определенную закладку в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/programming-with-bookmarks/show-hide-bookmarks/
---

В этой статье мы рассмотрим приведенный выше исходный код C#, чтобы понять, как использовать функцию «Показать скрыть закладки» в библиотеке Aspose.Words для .NET. Эта функция позволяет показать или скрыть определенную закладку в документе Word.

## Предварительные условия

- Базовые знания языка C#.
- Среда разработки .NET с установленной библиотекой Aspose.Words.

## Шаг 1: Загрузка документа

 Мы используем`Document` класс для загрузки существующего документа из файла:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Шаг 2. Показать или скрыть определенную закладку

 Мы используем`ShowHideBookmarkedContent` функция, позволяющая показать или скрыть определенную закладку в документе. Эта функция принимает в качестве параметров документ, имя закладки и логическое значение, указывающее, показывать или скрывать закладку:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Шаг 3. Сохранение измененного документа.

 Мы используем`Save` метод сохранения измененного документа в файл:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Пример исходного кода для «Показать скрытые закладки» с использованием Aspose.Words для .NET

Вот полный пример исходного кода, демонстрирующий отображение или скрытие определенной закладки с помощью Aspose.Words для .NET:

```csharp

	// Путь к каталогу документов.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### Исходный код ShowHideBookmarkedContent

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            // {IF "{MARGEFIELD bookmark}" = "true" "" ""}
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
        }
		
```
## Заключение

В этой статье мы изучили исходный код C#, чтобы понять, как использовать функцию «Показать скрытые закладки» в Aspose.Words для .NET. Мы следовали пошаговому руководству, чтобы показать или скрыть определенную закладку в документе.

### Часто задаваемые вопросы по показу скрытых закладок в документе Word

#### Вопрос: Могу ли я показать или скрыть несколько закладок в одном документе?

О: Да, вы можете показать или скрыть несколько закладок в одном документе, повторив шаги 2 и 3 для каждой закладки, которую вы хотите обработать.

#### Вопрос: Работает ли предоставленный код с другими форматами документов Word, такими как .doc или .docm?

О: Да, предоставленный код работает с различными форматами документов Word, поддерживаемыми Aspose.Words, такими как .doc и .docm. Просто обязательно используйте правильное имя файла и путь при загрузке и сохранении документа.

#### Вопрос: Как мне снова показать скрытую закладку?

 О: Чтобы снова показать скрытую закладку, нужно использовать ту же`ShowHideBookmarkedContent` функция, передающая значение`true` для логического параметра, указывающего, показывать или скрывать закладку.

#### Вопрос: Могу ли я использовать условия для отображения или скрытия закладок на основе значений поля слияния в документе?

 О: Да, вы можете использовать условия и значения полей слияния, чтобы определить, следует ли отображать или скрывать закладку. Вы можете настроить код`ShowHideBookmarkedContent` Функция учета соответствующих условий и значений.

#### Вопрос: Как удалить закладку в документе Word с помощью Aspose.Words for .NET?

 О: Чтобы удалить закладку в документе Word с помощью Aspose.Words for .NET, вы можете использовать`RemoveBookmarks` метод`Document` сорт. Вот пример кода:

```csharp
doc.RemoveBookmarks("BookmarkName");
```