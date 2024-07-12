---
title: 设置压缩级别
linktitle: 设置压缩级别
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 保存文档时设置压缩级别。
type: docs
weight: 10
url: /zh/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
在本教程中，我们将探索提供的 C# 源代码，以设置使用 Aspose.Words for .NET 保存文档时的压缩级别。此功能允许您控制生成的文档的压缩级别。

## 步骤 1：设置环境

开始之前，请确保您已使用 Aspose.Words for .NET 设置开发环境。请确保您已添加必要的引用并导入适当的命名空间。

## 步骤 2：加载文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

在此步骤中，我们使用`Document`方法并传递要加载的 DOCX 文件的路径。

## 步骤 3：配置 OOXML 备份选项

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

在此步骤中，我们使用`OoxmlSaveOptions`类。我们将压缩级别设置为`SuperFast`以获得更快的压缩。

## 步骤 4：使用指定的压缩级别保存文档

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

在最后一步中，我们使用`Save`方法并将路径传递给输出文件`.docx`扩展，以及指定的保存选项。

现在您可以运行源代码来设置保存文档时的压缩级别。生成的文件将保存在指定的目录中，名称为“WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx”。

### 使用 Aspose.Words for .NET 设置压缩级别的示例源代码 

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## 结论

在本教程中，我们探索了使用 Aspose.Words for .NET 保存文档时设置压缩级别的功能。通过指定适当的压缩级别，您可以优化文档大小和生成速度。

这`OoxmlSaveOptions`类提供了通过设置来控制压缩级别的灵活性`CompressionLevel`属性设置为适当的值，例如`SuperFast`。这可让您根据您的特定需求在文件大小和备份速度之间取得适当的平衡。

当您需要减小生成的文件大小（尤其是大型文档）时，使用压缩会很有用。这可以更轻松地存储、共享和传输文档。

Aspose.Words for .NET 提供了一系列强大的文档处理选项和功能。通过使用适当的备份选项，您可以自定义文档生成过程并优化应用程序的性能。

请随意探索 Aspose.Words for .NET 的更多功能，以增强您的文档生成工作流程。
