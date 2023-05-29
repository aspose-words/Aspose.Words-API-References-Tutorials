---
title: 使用密码加密 Docx
linktitle: 使用密码加密 Docx
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 使用密码加密 DOCX 文件。文档安全的完整教程。
type: docs
weight: 10
url: /zh/net/programming-with-ooxmlsaveoptions/encrypt-docx-with-password/
---
在本教程中，我们将探索提供的 C# 源代码，以使用 Aspose.Words for .NET 使用密码加密 DOCX 文件。此功能允许您通过仅使用指定密码访问来保护您的文档。

## 第 1 步：设置环境

在您开始之前，请确保您已经使用 Aspose.Words for .NET 设置了您的开发环境。确保您已经添加了必要的引用并导入了适当的命名空间。

## 第 2 步：装入文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

在此步骤中，我们使用`Document`方法并将路径传递给要加载的 DOCX 文件。

## 第 3 步：配置 OOXML 备份选项

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };
```

在此步骤中，我们通过创建一个新的`OoxmlSaveOptions`目的。我们通过设置指定所需的密码来加密文档`Password`属性到您的自定义密码。

## 第 4 步：使用密码加密文档

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
```

在这最后一步中，我们使用`Save`方法并将路径传递给输出文件`.docx`扩展名，以及指定的保存选项。

现在您可以运行源代码来使用密码加密您的 DOCX 文档。生成的文件将保存在指定目录中，名称为“WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx”。请务必妥善保管您的密码，因为打开加密文档需要用到它。

### 使用 Aspose.Words for .NET 使用密码加密 Docx 的示例源代码 

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";  

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { Password = "password" };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.EncryptDocxWithPassword.docx", saveOptions);
            
        
```

## 结论

在本教程中，我们探讨了使用 Aspose.Words for .NET 使用密码加密 DOCX 文件的功能。我们学习了如何通过仅使用指定密码访问文档来保护它们。

文档加密是保护敏感信息的基本安全措施。感谢 Aspose.Words for .NET，我们可以轻松地将此功能添加到我们的应用程序中。

按照提供的步骤，您可以将密码加密集成到您的 Aspose.Words for .NET 项目中，并确保您的文档的机密性。

随意尝试 Aspose.Words for .NET 提供的其他功能，以使用高级文档操作功能丰富您的应用程序。
