---
title: 在替换处插入文档
linktitle: 在替换处插入文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 插入替换文档。
type: docs
weight: 10
url: /zh/net/clone-and-combine-documents/insert-document-at-replace/
---
在本教程中，我们将引导您了解如何使用 Aspose.Words for .NET 的“替换时插入文档”功能在替换时将文档插入到另一个文档中。请按照以下步骤了解源代码并执行文档插入。

## 第 1 步：加载主文档

首先，指定文档的目录并将主文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 步骤 2：配置搜索和替换选项

现在，我们将通过指定搜索方向和替换回调来配置查找和替换选项，以将一个文档插入另一个文档。就是这样：

```csharp
//配置搜索和替换选项。
FindReplaceOptions options = new FindReplaceOptions
{
Direction = FindReplaceDirection.Backward,
ReplacingCallback = new InsertDocumentAtReplaceHandler()
};
```

## 第三步：调用替换方法

现在，我们将使用配置的选项调用替换方法来查找指定文本并将其替换为空字符串。就是这样：

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

## 结论

在本教程中，我们探讨了如何使用 Aspose.Words for .NET 的“替换时插入文档”功能在替换期间将文档插入到另一个文档中。通过配置查找和替换选项并提供必要的数据，您可以通过用其他文档模板或部分的内容替换特定占位符来动态组合文档。 Aspose.Words for .NET 提供了一种强大而灵活的方法来管理复杂的文档操作任务，使其成为自动化文档创建和内容插入场景的宝贵工具。

### 常见问题解答

#### 问：替换时将一个文档插入另一个文档的目的是什么？

答：在替换过程中将一个文档插入到另一个文档中，您可以使用单独文档的内容动态替换特定占位符。当您想要通过将各种预定义文档模板或部分组合到特定占位符中来组装更大的文档时，此功能特别有用。

#### 问：如何使用 Aspose.Words for .NET 在替换过程中将文档插入到另一个文档中？

答：要使用 Aspose.Words for .NET 在替换过程中将文档插入到另一个文档中，请按照下列步骤操作：
1. 将包含占位符的主文档加载到 Document 对象中。
2. 配置查找和替换选项，包括搜索方向和替换回调以处理文档插入。
3. 使用配置的选项，使用适当的搜索模式调用替换方法，将占位符替换为空字符串。

#### 问：我可以自定义替换期间的插入行为吗？

答：是的，您可以通过实现自定义 ReplacingCallback 来自定义替换期间的插入行为。通过继承IReplacingCallback接口，您可以在替换占位符时根据您的具体需求控制文档的插入和合并方式。

#### 问：我可以用不同的文档替换多个占位符吗？

答：是的，您可以通过为每个占位符指定适当的搜索模式并提供要插入的相应文档，将多个占位符替换为不同的文档。