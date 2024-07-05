---
title: 保留旧版控制字符
linktitle: 保留旧版控制字符
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 保存文档时保留传统的控制字符。
type: docs
weight: 10
url: /zh/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

在本教程中，我们将探索提供的 C# 源代码，以便在使用 Aspose.Words for .NET 保存文档时保留旧式控制字符。此功能允许您在转换或保存文档时保留特殊控制字符。

## 步骤 1：设置环境

开始之前，请确保您已使用 Aspose.Words for .NET 设置开发环境。请确保您已添加必要的引用并导入适当的命名空间。

## 步骤 2：加载文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

在此步骤中，我们使用`Document`方法并将路径传递给包含继承的控制字符的文件。

## 步骤 3：配置 OOXML 备份选项

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

在此步骤中，我们通过创建新的`OoxmlSaveOptions`对象。我们指定所需的保存格式（这里，`FlatOpc` ）并启用`KeepLegacyControlChars`保留传统控制字符的选项。

## 步骤 4：使用旧式控制字符保存文档

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

在最后一步中，我们使用`Save`方法并将路径传递给输出文件`.docx`扩展，以及指定的保存选项。

现在，您可以运行源代码以在保存文档时保留旧版控制字符。生成的文件将保存在指定目录中，名称为“WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx”。

### 使用 Aspose.Words for .NET 保留旧版控制字符的示例源代码 
```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## 结论

在本教程中，我们探讨了使用 Aspose.Words for .NET 保存文档时保留旧控制字符的功能。我们学习了如何保留那些对于正确的文档格式或显示可能很重要的特殊字符。

保留旧控制字符在处理使用较旧或特定功能（如特殊控制字符）的文档时尤其有用。通过启用`KeepLegacyControlChars`选项，确保这些字符被保留。

Aspose.Words for .NET 提供一系列灵活而强大的备份选项，以满足您的文档处理需求。通过使用适当的选项，您可以自定义备份过程以保留文档的特定特征。

请随意将此功能合并到您的 Aspose.Words for .NET 项目中，以确保文档中旧式控制字符的完整性和保存。