---
title: 克隆文档
linktitle: 克隆文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 克隆 Word 文档。
type: docs
weight: 10
url: /zh/net/clone-and-combine-documents/cloning-document/
---

在本教程中，我们将告诉您如何使用 Aspose.Words for .NET 的克隆功能来克隆 Word 文档。请按照以下步骤了解源代码并创建现有文档的精确副本。

## 第 1 步：加载文档

首先，指定文档目录并将现有文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## 第 2 步：克隆文档

现在我们将克隆该文档，创建它的精确副本。就是这样：

```csharp
Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.ClonageDocument.docx");
```

### 使用 Aspose.Words for .NET 克隆文档的示例源代码

以下是 .NET 的 Aspose.Words 文档克隆功能的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";            
Document doc = new Document(MyDir + "Document.docx");

Document clone = doc.Clone();
clone.Save(dataDir + "CloneAndCombineDocuments.CloningDocument.docx");
```

通过此代码，您将能够使用 Aspose.Words for .NET 克隆 Word 文档。文档的精确副本将以新文件名保存。

