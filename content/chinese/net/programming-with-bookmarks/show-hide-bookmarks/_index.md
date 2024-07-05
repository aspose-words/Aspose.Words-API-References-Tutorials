---
title: 在 Word 文档中显示隐藏书签
linktitle: 在 Word 文档中显示隐藏书签
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文档中显示或隐藏特定书签。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/show-hide-bookmarks/
---

在本文中，我们将探索上面的 C# 源代码，以了解如何使用 Aspose.Words for .NET 库中的“显示隐藏书签”功能。此功能允许您在 Word 文档中显示或隐藏特定书签。

## 先决条件

- C# 语言的基本知识。
- 安装了 Aspose.Words 库的.NET 开发环境。

## 步骤 1：加载文档

我们使用`Document`类从文件加载现有文档：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## 第 2 步：显示或隐藏特定书签

我们使用`ShowHideBookmarkedContent`函数用于显示或隐藏文档中的特定书签。此函数将文档、书签名称和布尔值作为参数，以指示是否显示或隐藏书签：

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## 步骤 3：保存修改后的文档

我们使用`Save`将修改后的文档保存到文件的方法：

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### 使用 Aspose.Words for .NET 显示隐藏书签的示例源代码

以下是完整的示例源代码，演示如何使用 Aspose.Words for .NET 显示或隐藏特定书签：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedContent 源代码

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
            Bookmark bm = doc.Range.Bookmarks[bookmarkName];

            DocumentBuilder builder = new DocumentBuilder(doc);
            builder.MoveToDocumentEnd();

            //{IF "{MERGEFIELD 书签}" = "true" "" ""}
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
## 结论

在本文中，我们探索了 C# 源代码，以了解如何使用 Aspose.Words for .NET 的“显示隐藏书签”功能。我们按照分步指南显示或隐藏文档中的特定书签。

### Word 文档中显示隐藏书签的常见问题解答

#### 问：我可以在同一文档中显示或隐藏多个书签吗？

答：是的，您可以通过对每个要处理的书签重复步骤 2 和 3 来显示或隐藏同一文档中的多个书签。

#### 问：提供的代码是否适用于其他 Word 文档格式，例如 .doc 或 .docm？

答：是的，提供的代码适用于 Aspose.Words 支持的各种 Word 文档格式，例如 .doc 和 .docm。只需确保在加载和保存文档时使用正确的文件名和路径即可。

#### 问：如何再次显示隐藏的书签？

答：要再次显示隐藏的书签，您需要使用相同的`ShowHideBookmarkedContent`函数传递值`true`用于指示是否显示或隐藏书签的布尔参数。

#### 问：我可以使用条件根据文档中的合并字段值来显示或隐藏书签吗？

答：是的，您可以使用条件和合并字段值来确定书签是否应显示或隐藏。您可以自定义`ShowHideBookmarkedContent`函数来考虑适当的条件和值。

#### 问：如何使用 Aspose.Words for .NET 删除 Word 文档中的书签？

答：要使用 Aspose.Words for .NET 删除 Word 文档中的书签，您可以使用`RemoveBookmarks`方法`Document`类。以下是示例代码：

```csharp
doc.RemoveBookmarks("BookmarkName");
```