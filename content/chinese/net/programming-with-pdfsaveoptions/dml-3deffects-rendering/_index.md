---
title: 在 PDF 文档中渲染 3D DML 3DEffects
linktitle: 在 PDF 文档中渲染 3D DML 3DEffects
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 转换为 PDF 时启用 3D DML 效果的渲染。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 转换为 PDF 时启用 3D DML 效果渲染的步骤。这会将 3D 效果保留在生成的 PDF 文档中。请按照以下步骤操作：

## 步骤 1：加载文档

首先上传您想要转换为 PDF 的文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请确保指定文档的正确路径。

## 步骤 2：配置 PDF 保存选项

创建 PdfSaveOptions 类的实例并启用 3D DML 效果的高级渲染：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

此选项可在生成的 PDF 文档中保留 3D 效果。

## 步骤 3：将文档转换为 PDF

使用`Save`将文档转换为 PDF 的方法指定保存选项：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

确保指定正确的路径来保存转换后的 PDF。

### 使用 Aspose.Words for .NET 进行 Dml 3DEffects 渲染的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

通过遵循这些步骤，您可以在使用 Aspose.Words for .NET 转换为 PDF 时轻松启用 3D DML 效果的渲染。

## 结论

在本教程中，我们解释了如何在使用 Aspose.Words for .NET 转换为 PDF 时启用 3D DML 效果的渲染。按照所述步骤，您可以轻松地在生成的 PDF 文档中保留 3D 效果。使用此功能可以保留原始文档的重要视觉效果。


### 经常问的问题

#### 问：什么是在 PDF 文档中渲染 3D DML 效果？
答：在 PDF 文档中呈现 3D DML 效果是指在将文档转换为 PDF 格式时保留 3D 效果的能力。这可以保留视觉效果并确保生成的 PDF 文档看起来与原始文档一样。

#### 问：如何使用 Aspose.Words for .NET 转换为 PDF 时启用 3D DML 效果的渲染？
答：要在使用 Aspose.Words for .NET 转换为 PDF 时启用 3D DML 效果的渲染，请按照以下步骤操作：

创建一个实例`Document`指定 Word 文档路径的类。

创建一个实例`PdfSaveOptions`类并设置`Dml3DEffectsRenderingMode`财产`Dml3DEffectsRenderingMode.Advanced`实现 3D DML 效果的高级渲染。

使用`Save`方法`Document`通过指定保存选项将文档保存为 PDF 格式。

#### 问：如何检查生成的 PDF 文档中是否已呈现 3D DML 效果？
答：要检查生成的 PDF 文档中是否呈现了 3D DML 效果，请使用兼容的 PDF 查看器（例如 Adobe Acrobat Reader）打开 PDF 文件并检查文档。您应该会看到原始文档中出现的 3D 效果。



