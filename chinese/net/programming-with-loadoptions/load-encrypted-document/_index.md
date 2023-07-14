---
title: 加载加密文档
linktitle: 加载加密文档
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 加载和保存加密文档。
type: docs
weight: 10
url: /zh/net/programming-with-loadoptions/load-encrypted-document/
---

在 C# 应用程序中对加密文档进行文字处理时，能够通过提供正确的密码正确加载它们非常重要。借助适用于 .NET 的 Aspose.Words 库，您可以使用适当的加载选项轻松加载加密文档。在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 的 C# 源代码通过 LoadOptions 加载选项加载加密文档。

## 了解 Aspose.Words 库

在深入研究代码之前，了解 .NET 的 Aspose.Words 库非常重要。 Aspose.Words 是一个功能强大的库，可在包括.NET 在内的不同平台上创建、编辑、转换和保护 Word 文档。它提供了许多用于操作文档的功能，例如插入文本、更改格式、添加部分等等。

## 加载加密文档

第一步是使用适当的上传选项上传加密文档。在我们的例子中，我们使用 Document 类通过指定文档路径和密码来加载文档。这是一个例子：

```csharp
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));
```

在此示例中，我们使用密码“password”加载位于文档目录中的文档“Encrypted.docx”。

## 保存加密文档

上传加密文档后，您还可以通过为输出文件指定新密码来保存它。在我们的示例中，我们使用 OdtSaveOptions 类使用新密码以 ODT 格式保存文档。操作方法如下：

```csharp
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

在此示例中，我们通过指定新密码“newpassword”以名称“WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt”保存文档。

### 使用 Aspose.Words for .NET 的具有“加载加密文档”功能的 LoadOptions 示例源代码

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用指定密码加载加密文档
Document doc = new Document(dataDir + "Encrypted.docx", new LoadOptions("password"));

//使用新密码保存加密文档
doc.Save(dataDir + "WorkingWithLoadOptions.LoadAndSaveEncryptedOdt.odt", new OdtSaveOptions("newpassword"));
```

## 结论

在本指南中，我们解释了如何使用 .NET 的 Aspose.Words 库加载和保存加密文档。通过遵循提供的步骤并使用提供的 C# 源代码，您可以轻松地在 C# 应用程序中应用此功能。上传加密文档可确保您的数据安全，并允许您在 Aspose.Words 中使用受保护的文档。