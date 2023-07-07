---
title: 在邮件合并中插入文档
linktitle: 在邮件合并中插入文档
second_title: Aspose.Words for .NET API 参考
description: 了解如何在邮件合并期间使用 Aspose.Words for .NET 将文档插入到另一个文档中。
type: docs
weight: 10
url: /zh/net/clone-and-combine-documents/insert-document-at-mail-merge/
---

在本教程中，我们将引导您了解如何使用 Aspose.Words for .NET 的“邮件合并期间插入文档”功能在邮件合并期间将文档插入到另一个文档中。请按照以下步骤了解源代码并执行文档插入。

## 第 1 步：加载主文档

首先，指定文档的目录并将主文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insert 1.docx");
```

## 步骤 2：配置邮件合并

现在让我们配置邮件合并并指定字段合并回调以将一个文档插入另一个文档。就是这样：

```csharp
mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
```

## 第 3 步：运行邮件合并

我们将通过提供合并字段的名称和相应的数据来运行邮件合并。就是这样：

```csharp
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });
mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

### 使用 Aspose.Words for .NET 在邮件合并中插入文档的示例源代码

以下是 Aspose.Words for .NET 的“在邮件合并中插入文档”功能的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document mainDoc = new Document(MyDir + "Document insertion 1.docx");

mainDoc.MailMerge.FieldMergingCallback = new InsertDocumentAtMailMergeHandler();
//主文档中有一个名为“Document_1”的合并字段。
//该字段的相应数据包含文档的完全限定路径。
//应该将其插入到该字段中。
mainDoc.MailMerge.Execute(new[] { "Document_1" }, new object[] { MyDir + "Document insertion 2.docx" });

mainDoc.Save(dataDir + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

通过此代码，您将能够在邮件合并期间使用 Aspose.Words for .NET 将一个文档插入到另一个文档中。生成的文档将以新名称保存



