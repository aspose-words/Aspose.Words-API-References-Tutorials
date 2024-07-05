---
title: 获取 Word 文档中的保护类型
linktitle: 获取 Word 文档中的保护类型
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 的 Word 文档中的获取保护类型功能来确定文档的保护类型。
type: docs
weight: 10
url: /zh/net/document-protection/get-protection-type/
---
欢迎阅读本分步指南，该指南介绍了 Aspose.Words for .NET 获取保护类型功能的 C# 源代码。在本文中，我们将向您展示如何使用此强大功能来确定文档的保护类型。文档保护对于确保文件的机密性和完整性至关重要。我们将引导您完成集成 Aspose.Words for .NET 和使用获取保护类型功能所需的步骤。

## 步骤 1：加载文档

使用“获取保护类型”功能的第一步是上传您要处理的文档。您可以使用 Aspose.Words for .NET 提供的 Document 类执行此操作。以下是从文件加载文档的示例代码：

```csharp
Document doc = new Document(MyDir + "Document.docx");
```

请确保指定文档文件的正确路径。

## 步骤 2：检索保护类型

文档上传后，您可以使用 Document 对象的 ProtectionType 属性来检索应用于文档的保护类型。操作方法如下：

```csharp
ProtectionType protectionType = doc.ProtectionType;
```

### 使用 Aspose.Words for .NET 获取保护类型的示例源代码

以下是使用 Aspose.Words for .NET 获取保护类型功能的完整源代码：

```csharp
Document doc = new Document(MyDir + "Document.docx");
ProtectionType protectionType = doc.ProtectionType;
```

## 结论

在本文中，我们解释了如何使用 Aspose.Words for .NET 的“获取保护类型”功能来确定文档的保护类型。通过遵循所述步骤，您将能够轻松地将此功能集成到您自己的 C# 项目中并有效地操作受保护的文档。Aspose.Words for .NET 提供了极大的灵活性

### 常见问题解答

#### 问：Aspose.Words for .NET 中的 ProtectionType 属性是什么？

答：`ProtectionType` Aspose.Words for .NET 中的 属性是一项功能，可让您确定应用于 Word 文档的保护类型。它提供有关文档保护级别的信息，例如文档是否受注释、修订、表单或其他类型限制的保护。

#### 问：如何使用 Aspose.Words for .NET 检索文档的保护类型？

答：要使用 Aspose.Words for .NET 检索文档的保护类型，您可以按照以下步骤操作：
1. 使用加载文档`Document`班级。
2. 访问`ProtectionType`的财产`Document`对象来检索保护类型。

#### 问：我可以使用 ProtectionType 属性确定文档是否受到表单或表单字段的保护吗？

答：是的，您可以使用以下方式确定文档是否受表单或表单字段保护：`ProtectionType` Aspose.Words for .NET 中的属性。如果保护类型设置为`AllowOnlyFormFields`，表示该文档受到保护，只有表单字段可以编辑。

#### 问：ProtectionType 属性还可以返回哪些其他保护类型？

答：`ProtectionType` Aspose.Words for .NET 中的属性可以返回各种保护类型，包括：
- `NoProtection`：该文档未受保护。
- `AllowOnlyRevisions`：该文档受到保护，只能进行修改。
- `AllowOnlyComments`：该文档已保护，仅可添加评论。
- `AllowOnlyFormFields`：该文档受到保护，仅可编辑表单字段。
- `ReadOnly`：该文档被保护并设置为只读。

#### 问：我可以使用 ProtectionType 属性修改文档的保护类型吗？

答：不，`ProtectionType`Aspose.Words for .NET 中的 属性是只读属性。它允许您检索文档的当前保护类型，但不提供修改保护类型的直接方法。要修改保护类型，您需要使用`Document`类，例如`Protect`或者`Unprotect`.

#### 问：是否可以同时使用多种保护类型来保护一个文档？

答：不可以，Aspose.Words for .NET 一次只允许对文档应用一种保护类型。但是，您可以通过启用保护、设置一种类型、禁用保护，然后再次启用另一种类型来组合不同的保护类型。

