---
title: 仅允许表单字段保护
linktitle: 仅允许表单字段保护
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 保护文档并仅允许编辑表单字段。
type: docs
weight: 10
url: /zh/net/document-protection/allow-only-form-fields-protect/
---

在 C# 应用程序中处理文件时，文档保护是一项重要功能。借助适用于 .NET 的 Aspose.Words 库，您可以轻松保护文档并只允许编辑表单字段。在本分步指南中，我们将引导您了解如何使用 C# 源代码仅允许使用 Aspose.Words for .NET 的“仅允许表单字段保护”功能来编辑表单字段。

## 第1步：设置文档目录

第一步是定义文档的目录。您必须指定要保存受保护文档的路径。例如 ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

请务必将“您的文档目录”替换为文档目录的实际路径。

## 第 2 步：插入部分和文本

接下来，您需要将部分和文本插入文档中。使用 Aspose.Words 提供的 DocumentBuilder 类来构建文档的内容。这是一个简单的例子：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");
```

在此示例中，我们创建一个新的空白文档，然后使用 DocumentBuilder 添加一行文本。

## 步骤 3：启用文档保护

仅当启用文档保护时，文档保护才起作用。您可以使用以下命令启用文档保护`Protect`Document 类的方法。就是这样：

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

在此示例中，我们通过指定保护类型`来启用文档保护

AllowOnlyFormFields` 并设置密码。

## 第 4 步：仅允许表单字段

现在已启用文档保护，我们需要指定仅允许编辑表单字段。这确保用户只能编辑文档中表单字段的部分。就是这样：

```csharp
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");
```

请务必将“password”替换为您之前设置的密码。

## 第5步：保存受保护的文档

最后，您可以使用以下命令保存受保护的文档`Save`Document 类的方法。指定完整文件路径和所需的文件名。例如 ：

```csharp
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

请务必将“dataDir”替换为文档目录的路径。

### 使用 Aspose.Words for .NET 的“仅允许表单字段保护”功能的示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//插入带有一些文本的两个部分。
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Text added to a document.");

//仅当打开文档保护并且仅允许在表单字段中进行编辑时，文档保护才起作用。
doc.Protect(ProtectionType.AllowOnlyFormFields, "password");

//保存受保护的文档。
doc.Save(dataDir + "DocumentProtection.AllowOnlyFormFieldsProtect.docx");
```

## 结论

在本指南中，我们探讨了如何使用 .NET 的 Aspose.Words 库来保护文档并仅允许编辑表单字段。通过按照提供的步骤操作，您可以在 C# 应用程序中轻松实现此功能。文档保护对于确保文档的安全性和机密性至关重要。
