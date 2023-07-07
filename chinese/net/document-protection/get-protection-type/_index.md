---
title: 获取保护类型
linktitle: 获取保护类型
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 的获取保护类型功能来确定文档的保护类型。
type: docs
weight: 10
url: /zh/net/document-protection/get-protection-type/
---

欢迎阅读本分步指南，该指南解释了 Aspose.Words for .NET 的“获取保护类型”功能的 C# 源代码。在本文中，我们将向您展示如何使用这一强大的功能来确定文档的保护类型。文档保护对于确保文件的机密性和完整性至关重要。我们将引导您完成集成 Aspose.Words for .NET 和使用“获取保护类型”功能所需的步骤。

## 第 1 步：加载文档

使用“获取保护类型”功能的第一步是上传您要处理的文档。您可以使用 Aspose.Words for .NET 提供的 Document 类来完成此操作。以下是从文件加载文档的示例代码：

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

请务必指定文档文件的正确路径。

## 步骤 2：检索保护类型

文档上传后，您可以使用 Document 对象的 ProtectionType 属性来检索应用于文档的保护类型。您可以这样做：

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### 使用 Aspose.Words for .NET 获取保护类型的示例源代码

以下是使用 Aspose.Words for .NET 获取保护类型函数的完整源代码：

```csharp

	Document doc = new Document(MyDir + "Document.docx");
	ProtectionType protectionType = doc.ProtectionType;

```

## 结论

在本文中，我们解释了如何使用Aspose.Words for .NET的获取保护类型功能来确定文档的保护类型。通过执行所描述的步骤，您将能够轻松地将此功能集成到您自己的 C# 项目中并有效地操作受保护的文档。 Aspose.Words for .NET 提供了极大的灵活性

