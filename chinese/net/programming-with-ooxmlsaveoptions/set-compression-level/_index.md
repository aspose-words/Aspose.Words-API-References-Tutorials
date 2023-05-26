---
title: 设置压缩级别
linktitle: 设置压缩级别
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 保存文档时设置压缩级别。
type: docs
weight: 10
url: /zh/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
在本教程中，我们将探索提供的 C# 源代码以在使用 Aspose.Words for .NET 保存文档时设置压缩级别。此功能允许您控制生成文档的压缩级别。

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
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

在此步骤中，我们使用`OoxmlSaveOptions`班级。我们将压缩级别设置为`SuperFast`以获得更快的压缩。

## 第 4 步：以指定的压缩级别保存文档

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

在这最后一步中，我们使用`Save`方法并将路径传递给输出文件`.docx`扩展名，以及指定的保存选项。

现在您可以运行源代码来设置保存文档时的压缩级别。生成的文件将保存在指定目录中，名称为“WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx”。

### 使用 Aspose.Words for .NET 设置压缩级别的示例源代码 

```csharp

//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
            
        
```

## 结论

在本教程中，我们探讨了使用 Aspose.Words for .NET 保存文档时设置压缩级别的功能。通过指定适当的压缩级别，您可以优化文档大小和生成速度。

这`OoxmlSaveOptions`类提供了通过设置来控制压缩级别的灵活性`CompressionLevel`属性设置为适当的值，例如`SuperFast`.这使您可以根据您的特定需求在文件大小和备份速度之间取得适当的平衡。

当您需要减小生成文件的大小时，尤其是对于大型文档，使用压缩会很有用。这样可以更轻松地存储、共享和传输文档。

Aspose.Words for .NET 为文档操作提供了一系列强大的选项和功能。通过使用适当的备份选项，您可以自定义文档生成过程并优化应用程序的性能。

随意探索 Aspose.Words for .NET 的更多功能，以增强您的文档生成工作流程。
