---
title: 在替换处插入文档
linktitle: 在替换处插入文档
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 在替换时插入文档。
type: docs
weight: 10
url: /zh/net/clone-and-combine-documents/insert-document-at-replace/
---

在本教程中，我们将向您介绍如何使用 Aspose.Words for .NET 的“替换时插入文档”功能将一个文档插入到另一个文档中。按照以下步骤了解源代码并执行文档插入。

## 第 1 步：加载主文档

首先，指定文档的目录并将主文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 第 2 步：配置搜索和替换选项

现在我们将通过指定搜索方向和替换回调来配置查找和替换选项，以将一个文档插入另一个文档。就是这样：

```csharp
//配置搜索和替换选项。
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## 第三步：调用替换方法

我们现在将调用 replace 方法，使用配置的选项查找指定文本并将其替换为空字符串。就是这样：

```csharp
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

### 使用 Aspose.Words for .NET 在替换时插入文档的示例源代码

以下是替换 Aspose.Words for .NET 时插入文档功能的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

//设置查找和替换选项。
FindReplaceOptions options = new FindReplaceOptions
{
	Direction = FindReplaceDirection.Backward, 
	ReplacingCallback = new InsertDocumentAtReplaceHandler()
};

//调用替换方法。
mainDoc.Range.Replace(new Regex("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```