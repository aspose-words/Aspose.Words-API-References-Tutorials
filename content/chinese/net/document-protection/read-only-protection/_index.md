---
title: Word 文档中的只读保护
linktitle: Word 文档中的只读保护
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 保护 Word 文档中的只读内容。
type: docs
weight: 10
url: /zh/net/document-protection/read-only-protection/
---
在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的只读保护功能的步骤。此功能允许您将 Word 文档设为只读，以防止未经授权的修改。请按照以下步骤操作：

## 步骤 1：创建文档并应用保护

首先创建 Document 类和 DocumentBuilder 对象的实例：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤 2：将内容写入文档
使用 DocumentBuilder 对象将内容写入文档：

```csharp
builder.Write("Open document as read-only");
```

## 步骤 3：设置密码并使文档只读

使用 WriteProtection 对象的 SetPassword() 属性为文档设置密码：

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

确保将“MyPassword”替换为您要使用的实际密码。

## 步骤 4：应用只读文档

通过将 ReadOnlyRecommended 属性设置为 true，使文档变为只读：

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## 步骤 5：应用只读保护并保存文档

最后，使用 Document 对象的 Protect() 方法应用只读保护：

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

确保指定正确的路径和文件名来保存受保护的文档。

### 使用 Aspose.Words for .NET 进行只读保护的示例源代码

以下是使用 Aspose.Words for .NET 进行只读保护的完整源代码：

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

//输入最多 15 个字符的密码。
doc.WriteProtection.SetPassword("MyPassword");

//将文档设为只读。
doc.WriteProtection.ReadOnlyRecommended = true;

//应用只读写保护。
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

通过遵循以下步骤，您可以轻松保护您的文档

## 结论

在本教程中，我们探索了 Aspose.Words for .NET 的只读保护功能，该功能允许您将 Word 文档设为只读以防止未经授权的修改。按照提供的步骤，您可以轻松地对文档应用只读保护并增强其安全性。只读保护通过限制编辑功能来帮助确保文档内容的完整性和准确性。Aspose.Words for .NET 提供了强大而灵活的 API 来处理文档保护，并支持各种其他功能来自定义和保护您的 Word 文档。

### Word 文档中只读保护的常见问题解答

#### 问：Aspose.Words for .NET 中的只读保护是什么？

答：Aspose.Words for .NET 中的只读保护功能可让您将 Word 文档设为只读，以防止未经授权的修改。当文档设置为只读时，用户可以打开和查看文档，但不能对其内容进行任何更改。

#### 问：如何使用 Aspose.Words for .NET 对 Word 文档应用只读保护？

答：要使用 Aspose.Words for .NET 对 Word 文档应用只读保护，您可以按照以下步骤操作：
1. 创建一个实例`Document`类和一个`DocumentBuilder`目的。
2. 使用`DocumentBuilder`将内容写入文档。
3. 使用`SetPassword`方法`WriteProtection`目的。
4. 设置`ReadOnlyRecommended`的财产`WriteProtection`反对`true`建议以只读方式打开文档。
5. 使用应用只读保护`Protect`方法`Document`对象，指定`ProtectionType`作为`ReadOnly`.
6. 使用保存受保护的文档`Save`方法`Document`目的。

#### 问：我可以使用 Aspose.Words for .NET 从 Word 文档中删除只读保护吗？

答：是的，您可以使用 Aspose.Words for .NET 删除 Word 文档的只读保护。为此，您可以使用`Unprotect`方法`Document`类，它将删除文档中所有现有的保护。

#### 问：我可以为 Word 文档的只读保护设置不同的密码吗？

答：不可以，Aspose.Words for .NET 中的只读保护不允许您专门为只读保护设置单独的密码。使用`SetPassword`方法`WriteProtection`对象适用于整体文档保护，包括只读保护和读写保护。

#### 问：用户能否绕过 Word 文档中的只读保护？

答：Word 文档中的只读保护旨在阻止和防止意外或未经授权的修改。虽然它提供了一定程度的保护，但具有足够技术知识或编辑权限的用户可以绕过它。不过，只读保护可以起到威慑作用，并有助于维护文档的完整性。