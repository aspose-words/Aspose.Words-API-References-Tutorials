---
title: 设置压缩级别
linktitle: 设置压缩级别
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 保存文档时设置压缩级别。
type: docs
weight: 10
url: /zh/net/programming-with-ooxmlsaveoptions/set-compression-level/
---
在本教程中，我们将探索提供的 C# 源代码，以在使用 Aspose.Words for .NET 保存文档时设置压缩级别。此功能允许您控制生成文档的压缩级别。

## 第一步：搭建环境

在开始之前，请确保您已使用 Aspose.Words for .NET 设置开发环境。确保您已添加必要的引用并导入适当的命名空间。

## 第 2 步：加载文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

在此步骤中，我们使用以下命令加载文档`Document`方法并传递要加载的 DOCX 文件的路径。

## 步骤 3：配置 OOXML 备份选项

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { CompressionLevel = CompressionLevel.SuperFast };
```

在此步骤中，我们使用以下命令配置 OOXML 保存选项`OoxmlSaveOptions`班级。我们将压缩级别设置为`SuperFast`以获得更快的压缩。

## 步骤 4：使用指定的压缩级别保存文档

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.SetCompressionLevel.docx", saveOptions);
```

在最后一步中，我们使用以下命令保存文档`Save`方法并将路径传递给输出文件`.docx`扩展名以及指定的保存选项。

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

这`OoxmlSaveOptions`类提供了通过设置来灵活地控制压缩级别`CompressionLevel`属性到适当的值，例如`SuperFast`。这使您可以根据您的特定需求在文件大小和备份速度之间取得适当的平衡。

当您需要减小生成的文件的大小时，尤其是对于大型文档，使用压缩会很有用。这可以使存储、共享和传输文档变得更加容易。

Aspose.Words for .NET 提供了一系列强大的文档操作选项和功能。通过使用适当的备份选项，您可以自定义文档生成过程并优化应用程序的性能。

请随意探索 Aspose.Words for .NET 的更多功能，以增强您的文档生成工作流程。
