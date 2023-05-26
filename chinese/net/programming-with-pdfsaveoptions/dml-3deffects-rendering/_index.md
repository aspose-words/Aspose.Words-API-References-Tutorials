---
title: Dml 3D效果渲染
linktitle: Dml 3D效果渲染
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 转换为 PDF 时启用 3D DML 效果渲染。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/dml-3deffects-rendering/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 转换为 PDF 时启用 3D DML 效果渲染的步骤。这会在生成的 PDF 文档中保留 3D 效果。请按照以下步骤操作：

## 第 1 步：装入文档

首先上传要转换为 PDF 的文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请务必指定文档的正确路径。

## 第 2 步：配置 PDF 保存选项

创建 PdfSaveOptions 类的实例并启用 3D DML 效果的高级渲染：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };
```

此选项将 3D 效果保留在生成的 PDF 文档中。

## 第 3 步：将文档转换为 PDF

使用`Save`指定保存选项将文档转换为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
```

确保指定正确的路径以保存转换后的 PDF。

### 使用 Aspose.Words for .NET 的 Dml 3DEffects 渲染示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Dml3DEffectsRenderingMode = Dml3DEffectsRenderingMode.Advanced };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.Dml3DEffectsRendering.pdf", saveOptions);
	 
```

通过执行这些步骤，您可以在使用 Aspose.Words for .NET 转换为 PDF 时轻松启用 3D DML 效果渲染。



