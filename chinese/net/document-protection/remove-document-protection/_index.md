---
title: 删除文档保护
linktitle: 删除文档保护
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 删除 Word 文档的保护。
type: docs
weight: 10
url: /zh/net/document-protection/remove-document-protection/
---

在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的取消保护文档功能的步骤。此功能允许您删除 Word 文档的保护，以便可以对其进行进一步编辑。请按照以下步骤操作：

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
