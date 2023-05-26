---
title: 删除文档保护
linktitle: 删除文档保护
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 移除 Word 文档的保护。
type: docs
weight: 10
url: /zh/net/document-protection/remove-document-protection/
---

在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的取消保护文档功能的步骤。此功能允许您取消对 Word 文档的保护，以便可以对其进行进一步编辑。请按照以下步骤操作：

## 第 1 步：创建文档并添加内容

首先创建一个 Document 类的实例和一个 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：向文档添加内容

使用 DocumentBuilder 对象向文档添加内容：

```csharp
builder.Writeln("Text added to a document.");
```

## 第 3 步：取消保护文档

要取消对文档的保护，可以使用 Document 对象的 Unprotect() 方法。您可以选择在没有密码的情况下或使用正确的密码解除保护。删除无密码保护：

```csharp
doc.Unprotect();
doc.Protect(ProtectionType.ReadOnly, "newPassword");
doc.Unprotect("newPassword");
```

请务必将“newPassword”替换为正确的文档密码。

## 第 4 步：在没有保护的情况下保存文档

最后，使用 Document 对象的 Save() 方法不受保护地保存文档：

```csharp
doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");
```

请务必指定正确的路径和文件名以不受保护地保存文档。

### 使用 Aspose.Words for .NET 移除文档保护的示例源代码

以下是使用 Aspose.Words for .NET 解除文档保护的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Text added to a document.");

	//可以在没有密码或使用正确密码的情况下删除文档的保护。
	doc.Unprotect();
	doc.Protect(ProtectionType.ReadOnly, "newPassword");
	doc.Unprotect("newPassword");

	doc.Save(dataDir + "DocumentProtection.RemoveDocumentProtection.docx");

```

通过执行这些步骤，您可以使用 Aspose.Words for .NET 轻松移除 Word 文档的保护。
