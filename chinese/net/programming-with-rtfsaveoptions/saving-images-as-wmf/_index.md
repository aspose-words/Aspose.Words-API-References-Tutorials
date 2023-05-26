---
title: 将图像保存为 Wmf
linktitle: 将图像保存为 Wmf
second_title: Aspose.Words for .NET API 参考
description: 了解在使用 Aspose.Words for .NET 将图像转换为 RTF 时如何将图像保存为 WMF。
type: docs
weight: 10
url: /zh/net/programming-with-rtfsaveoptions/saving-images-as-wmf/
---

在本教程中，我们将探索为 Aspose.Words for .NET 的“使用 RTF 保存选项将图像保存为 WMF”功能提供的 C# 源代码。此功能允许您在转换为 RTF 格式时将文档图像保存为 Windows 图元文件 (WMF) 格式。

## 第 1 步：设置环境

在您开始之前，请确保您已经使用 Aspose.Words for .NET 设置了您的开发环境。确保您已经添加了必要的引用并导入了适当的命名空间。

## 第 2 步：装入文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

在此步骤中，我们使用`Document`方法并将路径传递给要加载的 DOCX 文件。

## 第 3 步：配置备份选项

```csharp
RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };
```

在此步骤中，我们配置 RTF 备份选项。我们创造一个新的`RtfSaveOptions`对象并设置`SaveImagesAsWmf`财产给`true`.这告诉 Aspose.Words 在转换为 RTF 时将文档图像保存为 WMF。

## 第 4 步：保存文档

```csharp
doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
```

在这最后一步中，我们使用 RTF 格式保存生成的文档`Save`方法并将路径传递到输出文件，以及指定的保存选项。

现在您可以运行源代码将文档图像保存为 WMF 格式，同时转换为 RTF 格式。生成的文档将保存在指定目录中，名称为“WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf”。

### 使用 Aspose.Words for .NET 使用 RTF 保存选项保存 WMF 图像的功能示例源代码”。

```csharp

            
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");

RtfSaveOptions saveOptions = new RtfSaveOptions { SaveImagesAsWmf = true };

doc.Save(dataDir + "WorkingWithRtfSaveOptions.SavingImagesAsWmf.rtf", saveOptions);
            
        
```
## 结论

在本教程中，我们探讨了在 Aspose.Words for .NET 中使用 RTF 保存选项将图像保存为 WMF 的功能。我们学习了如何在转换为 RTF 格式时以 WMF 格式保存文档中的图像。

当您想要保持 RTF 文档中图像的质量和分辨率时，此功能很有用。通过以 WMF 格式保存图像，您可以确保它们的外观和清晰度保持不变。

Aspose.Words for .NET 提供了许多用于文档操作和生成的高级功能。在转换为 RTF 格式的同时以 WMF 格式保存图像是它为您提供的众多强大工具之一。