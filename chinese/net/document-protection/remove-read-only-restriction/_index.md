---
title: 解除只读限制
linktitle: 解除只读限制
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 从 Word 文档中删除只读限制。
type: docs
weight: 10
url: /zh/net/document-protection/remove-read-only-restriction/
---
在本教程中，我们将引导您完成使用 Aspose.Words for .NET 只读限制删除功能的步骤。此功能允许您从 Word 文档中删除只读限制，使其可编辑。请按照以下步骤操作：

## 第 1 步：创建文档并设置保护

首先创建 Document 类的实例：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
doc.WriteProtection.SetPassword("MyPassword");
```

使用 WriteProtection 对象的 SetPassword() 属性为文档设置密码：

请务必将“MyPassword”替换为您用于保护文档的实际密码。

## 第 2 步：解除只读限制

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

请务必指定正确的路径和文件名以保存没有只读限制的文档。

### 使用 Aspose.Words for .NET 移除只读限制的示例源代码

以下是使用 Aspose.Words for .NET 移除只读限制的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	
	//输入最多 15 个字符的密码。
	doc.WriteProtection.SetPassword("MyPassword");

	//删除只读选项。
	doc.WriteProtection.ReadOnlyRecommended = false;

	//在没有任何保护的情况下应用写保护。
	doc.Protect(ProtectionType.NoProtection);
	doc.Save(dataDir + "DocumentProtection.RemoveReadOnlyRestriction.docx");

```

通过执行这些步骤，您可以使用 Aspose.Words for .NET 轻松地从 Word 文档中删除只读限制。

