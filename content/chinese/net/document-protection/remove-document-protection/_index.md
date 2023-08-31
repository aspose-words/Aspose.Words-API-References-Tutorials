---
title: 删除Word文档中的文档保护
linktitle: 删除Word文档中的文档保护
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 删除 Word 文档中的保护。
type: docs
weight: 10
url: /zh/net/document-protection/remove-document-protection/
---
在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的取消保护文档功能的步骤。此功能允许您删除 Word 文档中的保护，以便可以对其进行进一步编辑。请按照以下步骤操作：

## 第 1 步：创建文档并添加内容

首先创建 Document 类的实例和 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：向文档添加内容

使用 DocumentBuilder 对象向文档添加内容：

```csharp
builder.Writeln("Text added to a document.");
```

## 步骤 3：取消文档保护

要取消对文档的保护，可以使用 Document 对象的 Unprotect() 方法。您可以选择取消保护而不使用密码或使用正确的密码。删除无密码保护：

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

请务必将“newPassword”替换为正确的文档密码。

## 步骤 4：保存不加保护的文档

最后，使用 Document 对象的 Save() 方法保存不受保护的文档：

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

请务必指定正确的路径和文件名，以不受保护地保存文档。

### 使用 Aspose.Words for .NET 删除文档保护的示例源代码

以下是使用 Aspose.Words for .NET 取消文档保护的完整源代码：

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

//可以在不使用密码或使用正确密码的情况下删除文档的保护。
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

通过执行以下步骤，您可以使用 Aspose.Words for .NET 轻松删除 Word 文档的保护。

## 结论

在本教程中，我们探讨了如何使用 Aspose.Words for .NET 删除 Word 文档中的文档保护。通过按照提供的步骤操作，您可以轻松取消对文档的保护并使其可用于进一步编辑。 Aspose.Words for .NET 提供了强大的 API，允许您操作文档保护设置并自定义 Word 文档的安全级别。删除文档保护使您可以根据需要灵活地修改文档内容和格式。

### 关于删除 Word 文档中的文档保护的常见问题解答

#### 问：Aspose.Words for .NET 中的文档保护是什么？

答：Aspose.Words for .NET 中的文档保护是指允许您对 Word 文档应用安全措施以限制编辑、格式设置和内容修改的功能。它有助于确保文档的完整性和机密性。

#### 问：如何使用 Aspose.Words for .NET 删除文档保护？

答：要使用 Aspose.Words for .NET 删除文档保护，您可以按照以下步骤操作：
1. 创建一个实例`Document`类和一个`DocumentBuilder`目的。
2. 使用`DocumentBuilder`向文档添加内容。
3. 致电`Unprotect`的方法`Document`反对从文档中删除任何现有的保护。无需密码或提供正确的密码即可完成此操作。
4. 使用以下命令保存未受保护的文档`Save`的方法`Document`目的。

#### 问：我可以在没有密码的情况下取消对 Word 文档的保护吗？

答：是的，您可以使用 Aspose.Words for .NET 取消对 Word 文档的保护，而无需密码。通过致电`Unprotect`的方法`Document`如果不提供密码，您可以删除对文档的保护（如果该文档之前没有使用密码进行保护）。

#### 问：如何取消 Word 文档的密码保护？

答：要解除受密码保护的Word文档的保护，您需要在调用时提供正确的密码。`Unprotect`的方法`Document`目的。这确保只有具有正确密码的用户才能取消保护并访问文档进行编辑。

#### 问：我可以从 Word 文档中删除特定的保护类型吗？

答：是的，使用 Aspose.Words for .NET，您可以有选择地从 Word 文档中删除特定的保护类型。通过致电`Unprotect`的方法`Document`对象时，您可以删除所需的保护类型，例如只读保护或表单保护，同时保留其他保护类型不变。