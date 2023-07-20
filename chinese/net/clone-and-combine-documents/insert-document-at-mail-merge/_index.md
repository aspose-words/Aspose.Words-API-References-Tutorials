---
title: 在邮件合并中插入文档
linktitle: 在邮件合并中插入文档
second_title: Aspose.Words 文档处理 API
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


## 结论

在本教程中，我们探讨了如何使用 Aspose.Words for .NET 的“邮件合并期间插入文档”功能在邮件合并期间将文档插入到另一个文档中。通过配置邮件合并并提供必要的数据，您可以通过合并各种文档模板或部分来动态组合文档。 Aspose.Words for .NET 提供了一种灵活而强大的方法来管理复杂的文档生成场景，使其成为自动化文档创建和操作任务的宝贵工具。

### 常见问题解答

#### 问：邮件合并时将一个文档插入另一个文档的目的是什么？

答：在邮件合并过程中将一个文档插入到另一个文档中，您可以根据合并过程中提供的数据动态组合不同的文档模板或部分。当您想要通过将各种预定义模板或部分合并到最终文档中来组装复杂文档时，此功能特别有用。

#### 问：如何在邮件合并过程中使用 Aspose.Words for .NET 将文档插入到另一个文档中？

答：要在邮件合并过程中使用 Aspose.Words for .NET 将文档插入到另一个文档中，请按照下列步骤操作：
1. 将作为基础的主文档加载到 Document 对象中。
2. 配置邮件合并并指定字段合并回调来处理文档插入。
3. 使用合并字段的名称和相应的数据（要插入的文档的路径）运行邮件合并。

#### 问：如何自定义邮件合并期间的插入行为？

答：要自定义邮件合并期间的插入行为，您可以通过继承 IFieldMergingCallback 接口来实现自定义 FieldMergingCallback。这使您可以根据您的具体要求控制文档的插入和合并方式。

#### 问：邮件合并时可以插入多个文档吗？

答：是的，您可以通过为每个合并字段提供适当的数据，在邮件合并期间插入多个文档。对于每个需要文档插入的合并字段，指定相应文档的路径作为数据。


