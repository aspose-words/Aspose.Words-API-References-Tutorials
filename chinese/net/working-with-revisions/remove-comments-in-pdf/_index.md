---
title: 删除 PDF 中的注释
linktitle: 删除 PDF 中的注释
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 删除 PDF 文件中的注释。
type: docs
weight: 10
url: /zh/net/working-with-revisions/remove-comments-in-pdf/
---

在本分步指南中，我们将告诉您如何使用 Aspose.Words for .NET 删除 PDF 文件中的注释。我们将为您提供完整的源代码，并向您展示如何格式化降价输出。

## 第 1 步：装入文档

第一步是加载包含评论的文档。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：隐藏 PDF 中的评论

我们将配置布局选项以在生成 PDF 时隐藏注释。

```csharp
doc.LayoutOptions.CommentDisplayMode = CommentDisplayMode.Hide;
```

## 第 3 步：将文档另存为 PDF

最后，我们将通过删除注释将文档保存为 PDF 格式。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.RemoveCommentsInPdf.pdf");
```

## 降价输出格式

可以将输出格式化为 markdown 以提高可读性。例如 ：

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