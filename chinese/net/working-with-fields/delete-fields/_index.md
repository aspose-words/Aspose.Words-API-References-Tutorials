---
title: 删除字段
linktitle: 删除字段
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 删除 Word 文档中合并字段的分步指南。
type: docs
weight: 10
url: /zh/net/working-with-fields/delete-fields/
---

解释如何使用 Aspose 中的“删除字段”功能。我们在下面为 .NET 创建了一个分步指南。 

重要的是要密切关注每个步骤以达到预期的结果。 

## 第 1 步：创建新文档

在此代码片段中，我们首先使用以下行创建一个新的空文档： 

```csharp
Document doc = new Document();
```

## 第 2 步：删除合并字段

要删除文档中存在的所有合并字段，我们使用`DeleteFields()`功能。 

如果您希望仅保留静态内容并删除任何合并信息，这将特别有用。 

### 使用 Aspose.Words for .NET 删除字段的源代码示例

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载现有文档。
Document doc = new Document(dataDir + "YourDocument.docx");

//删除合并字段。
doc.MailMerge.DeleteFields();

//保存修改后的文档。
doc.Save(dataDir + "YourDocument_WithoutFields.docx");
```

在我们的示例中，我们首先在调用之前加载现有文档`DeleteFields()`.最后，我们用新文件名保存修改后的文档。 

为了使用 Aspose.Words for .NET 的“删除字段”功能有效地从文档中删除合并字段，请参考此示例。 

永远记得用您的特定目录路径替换“您的文档目录”。 

我们关于通过 Aspose.Words for .NET 实现“删除字段”功能的指南就此结束。