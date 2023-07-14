---
title: Word 文档中的只读保护
linktitle: Word 文档中的只读保护
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 保护 Word 文档中的只读内容。
type: docs
weight: 10
url: /zh/net/document-protection/read-only-protection/
---
在本教程中，我们将指导您完成使用 Aspose.Words for .NET 的只读保护功能的步骤。此功能允许您将 Word 文档设置为只读以防止未经授权的修改。请按照以下步骤操作：

## 第 1 步：创建文档并应用保护

首先创建 Document 类的实例和 DocumentBuilder 对象：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 步骤2：将内容写入文档
使用 DocumentBuilder 对象将内容写入文档：

```csharp
builder.Write("Open document as read-only");
```

## 第三步：设置密码并将文档设置为只读

使用 WriteProtection 对象的 SetPassword() 属性设置文档的密码：

```csharp
doc.WriteProtection.SetPassword("MyPassword");
```

请务必将“MyPassword”替换为您要使用的实际密码。

## 第4步：应用只读文档

通过将 ReadOnlyRecommended 属性设置为 true 使文档只读：

```csharp
doc.WriteProtection.ReadOnlyRecommended = true;
```

## 步骤 5：应用只读保护并保存文档

最后，使用 Document 对象的 Protect() 方法应用只读保护：

```csharp
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");
```

请务必指定正确的路径和文件名来保存受保护的文档。

### 使用 Aspose.Words for .NET 进行只读保护的示例源代码

以下是使用 Aspose.Words for .NET 进行只读保护的完整源代码：

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Open document as read-only");

//输入最长 15 个字符的密码。
doc.WriteProtection.SetPassword("MyPassword");

//将文档设置为只读。
doc.WriteProtection.ReadOnlyRecommended = true;

//将写保护应用为只读。
doc.Protect(ProtectionType.ReadOnly);
doc.Save(dataDir + "DocumentProtection.ReadOnlyProtection.docx");

```

通过执行以下步骤，您可以轻松保护您的文档

## 结论

在本教程中，我们探索了 Aspose.Words for .NET 的只读保护功能，该功能允许您将 Word 文档设为只读以防止未经授权的修改。通过按照提供的步骤操作，您可以轻松地对文档应用只读保护并增强其安全性。只读保护通过限制编辑功能来帮助确保文档内容的完整性和准确性。 Aspose.Words for .NET 提供了强大而灵活的 API 来处理文档保护，并支持各种其他功能来自定义和保护您的 Word 文档。

### Word 文档只读保护常见问题解答

#### 问：Aspose.Words for .NET 中的只读保护是什么？

答：Aspose.Words for .NET 中的只读保护功能允许您将 Word 文档设置为只读，从而防止未经授权的修改。当文档设置为只读时，用户可以打开和查看该文档，但无法对其内容进行任何更改。

#### 问：如何使用 Aspose.Words for .NET 对 Word 文档应用只读保护？

答：要使用 Aspose.Words for .NET 对 Word 文档应用只读保护，您可以按照以下步骤操作：
1. 创建一个实例`Document`类和一个`DocumentBuilder`目的。
2. 使用`DocumentBuilder`将内容写入文档。
3. 使用以下命令为文档设置密码`SetPassword`的方法`WriteProtection`目的。
4. 设置`ReadOnlyRecommended`的财产`WriteProtection`反对`true`建议以只读方式打开文档。
5. 使用以下命令应用只读保护`Protect`的方法`Document`对象，指定`ProtectionType`作为`ReadOnly`.
6. 使用以下命令保存受保护的文档`Save`的方法`Document`目的。

#### 问：我可以使用 Aspose.Words for .NET 删除 Word 文档的只读保护吗？

答：是的，您可以使用 Aspose.Words for .NET 从 Word 文档中删除只读保护。为此，您可以使用`Unprotect`的方法`Document`类，它从文档中删除任何现有的保护。

#### 问：我可以在Word文档中设置不同的密码以进行只读保护吗？

答：不可以，Aspose.Words for .NET 中的只读保护不允许您专门为只读保护设置单独的密码。使用设置的密码`SetPassword`的方法`WriteProtection`object适用于整个文档的保护，包括只读和读写保护。

#### 问：用户可以绕过 Word 文档中的只读保护吗？

答：Word 文档中的只读保护旨在阻止和防止意外或未经授权的修改。虽然它提供了一定程度的保护，但具有足够技术知识或编辑权限的用户可以绕过它。然而，只读保护可以起到威慑作用，并有助于维护文档的完整性。