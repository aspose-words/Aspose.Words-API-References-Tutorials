---
title: 删除只读限制
linktitle: 删除只读限制
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 删除 Word 文档的只读限制。
type: docs
weight: 10
url: /zh/net/document-protection/remove-read-only-restriction/
---
在本教程中，我们将引导您完成使用 Aspose.Words for .NET 只读限制删除功能的步骤。此功能允许您删除 Word 文档的只读限制，使其可编辑。请按照以下步骤操作：

## 第1步：创建文档并设置保护

首先创建 Document 类的实例：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

使用 WriteProtection 对象的 SetPassword() 属性设置文档的密码：

请务必将“MyPassword”替换为您用于保护文档的实际密码。

## 第 2 步：删除只读限制

要删除只读限制，请将 ReadOnlyRecommended 属性设置为 false：

```csharp
doc.WriteProtection.ReadOnlyRecommended = false;
```

## 第 3 步：应用无限制保护

最后，使用 Document 对象的 Protect() 方法应用不受限制的保护：

```csharp
doc.Protect(ProtectionType.NoProtection);
doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");
```

请务必指定正确的路径和文件名来保存文档，而不受只读限制。

### 使用 Aspose.Words for .NET 删除只读限制的示例源代码

以下是使用 Aspose.Words for .NET 删除只读限制的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	//输入最长 15 个字符的密码。
	doc.WriteProtection.SetPassword("MyPassword");

	//删除只读选项。
	doc.WriteProtection.ReadOnlyRecommended = false;

	//应用写保护而不进行任何保护。
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

通过执行以下步骤，您可以使用 Aspose.Words for .NET 轻松删除 Word 文档的只读限制。

