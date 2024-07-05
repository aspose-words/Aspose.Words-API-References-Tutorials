---
title: 仅允许在 Word 文档中保护表单字段
linktitle: 仅允许在 Word 文档中保护表单字段
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 保护 Word 文档并只允许编辑表单字段。
type: docs
weight: 10
url: /zh/net/document-protection/allow-only-form-fields-protect/
---
文档保护是使用 C# 应用程序中的文件进行文字处理时必不可少的功能。使用 .NET 的 Aspose.Words 库，您可以轻松保护文档并仅允许编辑表单字段。在本分步指南中，我们将引导您了解如何使用 C# 源代码仅允许使用 .NET 的 Aspose.Words 的“仅允许表单字段保护”功能编辑表单字段。

## 步骤 1：设置文档目录

第一步是定义文档的目录。您必须指定要保存受保护文档的路径。例如：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

确保将“YOUR DOCUMENTS DIRECTORY”替换为您的文档目录的实际路径。

## 步骤 2：插入章节和文本

接下来，您需要在文档中插入章节和文本。使用 Aspose.Words 提供的 DocumentBuilder 类来构建文档的内容。这是一个简单的例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

在这个例子中，我们创建一个新的空白文档，然后使用 DocumentBuilder 添加一行文本。

## 步骤 3：启用文档保护

文档保护仅在启用文档保护时才有效。您可以使用`Protect`方法。操作方法如下：

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

在此示例中，我们通过指定保护类型来启用文档保护`

AllowOnlyFormFields`并设置密码。

## 步骤 4：仅允许表单字段

现在已启用文档保护，我们需要指定仅允许编辑表单字段。这可确保用户只能编辑文档中属于表单字段的部分。操作方法如下：

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

请务必将“密码”替换为您之前设置的密码。

## 步骤5：保存受保护的文档

最后，您可以使用`Save`方法。指定完整文件路径和所需文件名。例如：

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

确保将“dataDir”替换为您的文档目录的路径。

### 使用 Aspose.Words for .NET 的“仅允许表单字段保护”功能的示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//插入两个包含一些文本的部分。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

//仅当文档保护处于开启状态时，文档保护才有效，并且只允许在表单字段中进行编辑。
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//保存受保护的文档。
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## 结论

在本指南中，我们探讨了如何使用 .NET 的 Aspose.Words 库来保护文档并仅允许编辑表单字段。按照提供的步骤，您可以轻松地在 C# 应用程序中实现此功能。文档保护对于确保文档的安全性和机密性至关重要。

### 有关仅允许在 Word 文档中保护表单字段的常见问题解答

#### 问：Aspose.Words for .NET 中的文档保护是什么？

答：Aspose.Words for .NET 中的文档保护功能允许您通过限制某些操作（例如编辑、格式化或内容修改）来保护文档。它通过防止未经授权的更改来帮助维护文档的完整性和机密性。

#### 问：如何保护文档并仅允许使用 Aspose.Words for .NET 编辑表单字段？

答：要保护文档并仅允许使用 Aspose.Words for .NET 编辑表单字段，您可以按照以下步骤操作：
1. 定义文档的目录路径。
2. 使用`DocumentBuilder`班级。
3. 使用启用文档保护`Protect`方法`Document`类，指定保护类型为`AllowOnlyFormFields`并提供密码。
4. 使用保存受保护的文档`Save`方法`Document`班级。

#### 问：我可以使用 Aspose.Words for .NET 将表单字段插入受保护的文档中吗？

答：是的，您可以使用 Aspose.Words for .NET 将表单字段插入受保护的文档中。使用`AllowOnlyFormFields`类型允许用户仅编辑表单字段，同时保护文档的其余内容。您可以使用`DocumentBuilder`在启用保护之前将表单字段插入到文档中。

#### 问：我可以从受保护的文档中删除文档保护吗？

答：是的，您可以使用 Aspose.Words for .NET 从受保护的文档中删除文档保护。要删除保护，您可以使用`Unprotect`方法`Document`类并提供正确的密码。这将删除保护并允许不受限制地编辑文档。

#### 问：可以使用多种保护类型来保护一个文档吗？

答：不可以，Aspose.Words for .NET 一次只允许将一种保护类型应用于文档。但是，`AllowOnlyFormFields`保护类型可以有效地限制对表单字段的编辑，同时允许其他保护类型，例如`AllowOnlyComments`或者`AllowOnlyRevisions`，与表单字段保护相结合。

#### 问：我可以为文档中的不同保护类型设置不同的密码吗？

答：不，Aspose.Words for .NET 允许您设置单个密码来保护文档，无论保护类型如何。启用和禁用文档保护将使用相同的密码。