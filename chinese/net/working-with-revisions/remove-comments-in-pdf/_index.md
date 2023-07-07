---
title: 删除 PDF 文件中的注释
linktitle: 删除 PDF 文件中的注释
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 删除 PDF 文件中的注释。
type: docs
weight: 10
url: /zh/net/working-with-revisions/remove-comments-in-pdf/
---

在本分步指南中，我们将告诉您如何使用 Aspose.Words for .NET 删除 PDF 文件中的注释。我们将为您提供完整的源代码，并向您展示如何格式化 Markdown 输出。

## 第 1 步：加载文档

第一步是加载包含注释的文档。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：隐藏 PDF 中的注释

我们将配置布局选项以在生成 PDF 时隐藏注释。

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## 步骤 3：将文档另存为 PDF

最后，我们通过删除注释将文档保存为PDF格式。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## Markdown 输出格式

输出可以采用 Markdown 格式以提高可读性。例如 ：

```markdown
- Comments are hidden in the generated PDF.
```

### 使用 Aspose.Words for .NET 删除 Pdf 中的注释的示例源代码

以下是使用 Aspose.Words for .NET 删除 PDF 文件中注释的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");

//隐藏 PDF 中的注释。
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;

doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 从 PDF 文件中删除注释。通过使用适当的布局选项，我们能够在生成 PDF 时隐藏注释。 Aspose.Words for .NET 提供了极大的灵活性来操作 Word 文件并将其转换为不同的格式，包括 PDF。您现在可以应用这些知识，使用 Aspose.Words for .NET 删除您自己的 PDF 文件中的注释。

### 删除 pdf 文件中注释的常见问题解答

#### 问：如何在 Aspose.Words for .NET 中上传文档？

答：使用`Document`用于从文件加载文档的 Aspose.Words for .NET 类。您可以指定完整的文档路径。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### 问：如何隐藏使用 Aspose.Words for .NET 生成的 PDF 中的注释？

答：使用`CommentDisplayMode`的财产`LayoutOptions`对象来配置生成 PDF 时注释的显示方式。要隐藏评论，请将此属性设置为`CommentDisplayMode.Hide`.

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

#### 问：如何使用 Aspose.Words for .NET 将文档另存为 PDF？

答：使用`Save`的方法`Document`对象以 PDF 格式保存文档。指定 PDF 文件的完整路径。

```csharp
doc.Save("path/to/the/file.pdf");
```