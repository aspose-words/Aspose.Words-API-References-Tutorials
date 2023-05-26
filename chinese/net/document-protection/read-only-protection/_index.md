---
title: 只读保护
linktitle: 只读保护
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 保护您的只读 Word 文档。
type: docs
weight: 10
url: /zh/net/document-protection/read-only-protection/
---
在本教程中，我们将引导您完成使用 Aspose.Words for .NET 的只读保护功能的步骤。此功能允许您将 Word 文档设置为只读，以防止未经授权的修改。请按照以下步骤操作：

## 第 1 步：创建文档并应用保护

首先创建一个 Document 类的实例和一个 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第二步：向文档写入内容
使用 DocumentBuilder 对象将内容写入文档：

```csharp
builder.Write("Open document as read-only");
```

## 第 3 步：设置密码并将文档设置为只读

使用 WriteProtection 对象的 SetPassword() 属性为文档设置密码：

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

请务必将“MyPassword”替换为您要使用的实际密码。

## 第四步：申请只读文件

通过将 ReadOnlyRecommended 属性设置为 true 使文档为只读：

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## 步骤 5：应用只读保护并保存文档

最后，使用 Document 对象的 Protect() 方法应用只读保护：

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

请务必指定正确的路径和文件名以保存受保护的文档。

### 使用 Aspose.Words for .NET 的只读保护示例源代码

以下是使用 Aspose.Words for .NET 进行只读保护的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Write("Open document as read-only");

	//输入最多 15 个字符的密码。
	doc.WriteProtection.SetPassword("MyPassword");

	//将文档设置为只读。
	doc.WriteProtection.ReadOnlyRecommended = true;

	//将写保护应用为只读。
	doc.Protect(ProtectionType.ReadOnly);
	doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

按照这些步骤，您可以轻松保护您的文档

