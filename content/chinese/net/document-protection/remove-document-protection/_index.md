---
title: 在 Word 文档中删除文档保护
linktitle: 在 Word 文档中删除文档保护
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 删除 Word 文档中的保护。
type: docs
weight: 10
url: /zh/net/document-protection/remove-document-protection/
---
在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的取消保护文档功能的步骤。此功能允许您删除 Word 文档中的保护，以便可以对其进行进一步编辑。请按照以下步骤操作：

## 步骤 1：创建文档并添加内容

首先创建 Document 类和 DocumentBuilder 对象的实例：

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

要取消文档保护，可以使用 Document 对象的 Unprotect() 方法。您可以选择不使用密码或使用正确密码来取消保护。取消无密码保护：

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

确保将“newPassword”替换为正确的文档密码。

## 步骤 4：不加保护地保存文档

最后，使用 Document 对象的 Save() 方法保存不受保护的文档：

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

确保指定正确的路径和文件名以保存不受保护的文档。

### 使用 Aspose.Words for .NET 删除文档保护的示例源代码

以下是使用 Aspose.Words for .NET 取消保护文档的完整源代码：

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Text added to a document.");

//无需密码或使用正确密码即可解除文档保护。
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");

doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

通过遵循这些步骤，您可以轻松地使用 Aspose.Words for .NET 从 Word 文档中删除保护。

## 结论

在本教程中，我们探讨了如何使用 Aspose.Words for .NET 删除 Word 文档中的文档保护。按照提供的步骤，您可以轻松取消文档保护并使其可供进一步编辑。Aspose.Words for .NET 提供了一个强大的 API，允许您操作文档保护设置并自定义 Word 文档的安全级别。删除文档保护使您可以灵活地根据需要修改文档内容和格式。

### 关于删除 Word 文档中的文档保护的常见问题解答

#### 问：Aspose.Words for .NET 中的文档保护是什么？

答：Aspose.Words for .NET 中的文档保护是指允许您对 Word 文档应用安全措施以限制编辑、格式化和内容修改的功能。它有助于确保文档的完整性和机密性。

#### 问：如何使用 Aspose.Words for .NET 删除文档保护？

答：要使用 Aspose.Words for .NET 删除文档保护，您可以按照以下步骤操作：
1. 创建一个实例`Document`类和一个`DocumentBuilder`目的。
2. 使用`DocumentBuilder`向文档添加内容。
3. 致电`Unprotect`方法`Document`对象可删除文档中现有的任何保护。此操作无需密码，也可以通过提供正确的密码来完成。
4. 使用`Save`方法`Document`目的。

#### 问：我可以不使用密码来删除 Word 文档的保护吗？

答：是的，您可以使用 Aspose.Words for .NET 删除 Word 文档的保护，无需密码。通过调用`Unprotect`方法`Document`对象而不提供密码，如果文档之前没有密码保护，则可以删除该文档的保护。

#### 问：如何使用密码取消 Word 文档的保护？

答：要取消对受密码保护的 Word 文档的保护，您需要在调用`Unprotect`方法`Document`对象。这确保只有拥有正确密码的用户才能解除保护并访问文档进行编辑。

#### 问：我可以从 Word 文档中删除特定的保护类型吗？

答：是的，使用 Aspose.Words for .NET，您可以有选择地从 Word 文档中删除特定的保护类型。通过调用`Unprotect`方法`Document`对象，您可以删除所需的保护类型，例如只读保护或表单保护，同时保留其他保护类型不变。