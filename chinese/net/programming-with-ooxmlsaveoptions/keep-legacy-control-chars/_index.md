---
title: 保留遗留控制字符
linktitle: 保留遗留控制字符
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 保存文档时保留遗留控制字符。
type: docs
weight: 10
url: /zh/net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

在本教程中，我们将探索提供的 C# 源代码，以在使用 Aspose.Words for .NET 保存文档时保留遗留控制字符。此功能允许您在转换或保存文档时保留特殊控制字符。

## 第 1 步：设置环境

在您开始之前，请确保您已经使用 Aspose.Words for .NET 设置了您的开发环境。确保您已经添加了必要的引用并导入了适当的命名空间。

## 第 2 步：装入文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

在此步骤中，我们使用`Document`方法并将路径传递给包含继承的控制字符的文件。

## 第 3 步：配置 OOXML 备份选项

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

在此步骤中，我们通过创建一个新的`OoxmlSaveOptions`目的。我们指定所需的保存格式（这里，`FlatOpc` ) 并启用`KeepLegacyControlChars`保留旧控制字符的选项。

## 第 4 步：使用遗留控制字符保存文档

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

在这最后一步中，我们使用`Save`方法并将路径传递给输出文件`.docx`扩展名，以及指定的保存选项。

现在您可以运行源代码以在保存文档时保留遗留控制字符。生成的文件将保存在指定目录中，名称为“WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx”。

### 使用 Aspose.Words for .NET 的 Keep Legacy Control Chars 示例源代码 
```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## 结论

在本教程中，我们探索了在使用 Aspose.Words for .NET 保存文档时保留遗留控制字符的功能。我们已经学习了如何保留那些可能对正确的文档格式或显示很重要的特殊字符。

在处理使用较旧或特定功能（例如特殊控制字符）的文档时，保留旧控制字符特别有用。通过启用`KeepLegacyControlChars`保存文档时的选项，请确保保留这些字符。

Aspose.Words for .NET 提供了一系列灵活而强大的备份选项来满足您的文档操作需求。通过使用适当的选项，您可以自定义备份过程以保留文档的特定特征。

随意将此功能合并到您的 Aspose.Words for .NET 项目中，以确保文档中遗留控制字符的完整性和保留。