---
title: 密码保护
linktitle: 密码保护
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 对 Word 文档进行密码保护。
type: docs
weight: 10
url: /zh/net/document-protection/password-protection/
---

在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的密码保护功能的步骤。此功能允许您使用密码保护 Word 文档，以确保其机密性。请按照以下步骤操作：

## 第 1 步：创建文档并应用保护

首先创建 Document 类的实例：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## 第 2 步：应用密码保护

然后，您可以使用 Document 对象的 Protect() 方法应用密码保护：

```csharp
doc.Protect(ProtectionType.NoProtection, "password");
```

请务必将“密码”替换为您要用于保护文档的实际密码。

## 步骤3：保存受保护的文档

最后，您可以使用 Document 对象的 Save() 方法保存受保护的文档：

```csharp
doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");
```

请务必指定正确的路径和文件名来保存受保护的文档。

### 使用 Aspose.Words for .NET 进行密码保护的示例源代码

以下是使用 Aspose.Words for .NET 进行密码保护的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();

	//应用文档保护。
	doc.Protect(ProtectionType.NoProtection, "password");

	doc.Save(dataDir + "DocumentProtection.PasswordProtection.docx");

```

请记住将“您的文档目录”替换为您的文档目录，并将“密码”替换为您要使用的实际密码。

