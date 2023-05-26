---
title: 使用密码加密文档
linktitle: 使用密码加密文档
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 使用密码加密文档。
type: docs
weight: 10
url: /zh/net/programming-with-docsaveoptions/encrypt-document-with-password/
---
在 C# 应用程序中处理文件时，文档安全性至关重要。借助 .NET 的 Aspose.Words 库，您可以通过使用密码加密来轻松保护您的文档。在本分步指南中，我们将带您了解如何使用 Aspose.Words for .NET C# 源代码使用 DocSaveOptions 保存选项加密文档。

## 理解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库很重要。 Aspose.Words 是一个强大的库，可以在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 第 1 步：定义文档目录

第一步是设置要保存加密文档的目录。您必须指定完整的目录路径。例如 ：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

请务必将“您的文档目录”替换为您的文档目录的实际路径。

## 第 2 步：创建和编辑文档

然后您可以创建文档并向其中添加内容。使用 Aspose.Words 提供的 DocumentBuilder 类来构建文档的内容。例如 ：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");
```

在此示例中，我们创建一个新的空白文档，然后使用 DocumentBuilder 编写文本“Hello World!”。

## 第 3 步：配置录制选项

现在让我们为文档配置保存选项。使用 DocSaveOptions 类指定保存设置。例如 ：

```csharp
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };
```

在此示例中，我们创建一个新的 DocSaveOptions 对象并将密码属性设置为“密码”以使用此密码加密文档。

## 第 4 步：启用“使用密码加密文档”功能

我们已经配置了选项

使用指定的密码注册，这将自动激活“使用密码加密文档”功能。这可确保文档使用保存时指定的密码进行加密。

## 第 5 步：保存文档

最后，您可以使用 Document 类的 Save 方法保存文档。指定文件的完整路径和所需的文件名。例如 ：

```csharp
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

请务必将“dataDir”替换为文档的目录路径。

### 使用 Aspose.Words for .NET 的具有“使用密码加密文档”功能的 DocSaveOptions 保存选项的示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建和编辑文档
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
            
builder.Write("Hello world!");

//使用“使用密码加密文档”功能配置保存选项
DocSaveOptions saveOptions = new DocSaveOptions { Password = "password" };

//使用指定选项保存文档
doc.Save(dataDir + "WorkingWithDocSaveOptions.EncryptDocumentWithPassword.docx", saveOptions);
```

## 结论

在本指南中，我们解释了如何使用适用于 .NET 的 Aspose.Words 库使用 DocSaveOptions 保存选项使用密码加密文档。按照提供的步骤并使用提供的 C# 源代码，您可以轻松地将此功能应用到您的 C# 应用程序中。使用密码对文档进行加密可确保处理文档时的机密性和安全性。