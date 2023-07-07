---
title: 保留旧控制字符
linktitle: 保留旧控制字符
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 保存文档时保留旧控制字符。
type: docs
weight: 10
url: /zh/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

在本教程中，我们将探索提供的 C# 源代码，以在使用 Aspose.Words for .NET 保存文档时保留旧控制字符。此功能允许您在转换或保存文档时保留特殊控制字符。

## 第一步：搭建环境

在开始之前，请确保您已使用 Aspose.Words for .NET 设置开发环境。确保您已添加必要的引用并导入适当的命名空间。

## 第 2 步：加载文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

在此步骤中，我们使用以下命令加载文档`Document`方法并将路径传递给包含继承的控制字符的文件。

## 步骤 3：配置 OOXML 备份选项

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

在此步骤中，我们通过创建新的 OOXML 保存选项来配置`OoxmlSaveOptions`目的。我们指定所需的保存格式（此处，`FlatOpc` ）并启用`KeepLegacyControlChars`保留传统控制字符的选项。

## 步骤 4：使用旧控制字符保存文档

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

在最后一步中，我们使用以下命令保存文档`Save`方法并将路径传递给输出文件`.docx`扩展名以及指定的保存选项。

现在，您可以运行源代码以在保存文档时保留旧控制字符。生成的文件将保存在指定目录中，名称为“WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx”。

### 使用 Aspose.Words for .NET 保留旧版控制字符的示例源代码 
```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## 结论

在本教程中，我们探讨了使用 Aspose.Words for .NET 保存文档时保留旧控制字符的功能。我们已经了解了如何保留那些对于正确的文档格式或显示可能很重要的特殊字符。

在处理使用较旧或特定功能（例如特殊控制字符）的文档时，保留旧控制字符特别有用。通过启用`KeepLegacyControlChars`保存文档时选择选项，确保保留这些字符。

Aspose.Words for .NET 提供了一系列灵活且强大的备份选项来满足您的文档操作需求。通过使用适当的选项，您可以自定义备份过程以保留文档的特定特征。

请随意将此功能合并到您的 Aspose.Words for .NET 项目中，以确保文档中旧控制字符的完整性和保留。