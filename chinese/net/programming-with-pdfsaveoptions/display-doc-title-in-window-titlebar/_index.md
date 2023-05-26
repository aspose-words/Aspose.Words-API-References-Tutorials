---
title: 在窗口标题栏中显示文档标题
linktitle: 在窗口标题栏中显示文档标题
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 转换为 PDF 时在窗口标题栏中显示文档标题。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

在本教程中，我们将指导您完成使用 Aspose.Words for .NET 在窗口标题栏中显示文档标题的步骤。此功能允许您在打开生成的 PDF 文档时在窗口标题栏中显示文档标题。请按照以下步骤操作：

## 第 1 步：装入文档

首先上传要转换为 PDF 的文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请务必指定文档的正确路径。

## 第 2 步：配置 PDF 保存选项

创建 PdfSaveOptions 类的实例并启用在窗口标题栏中显示文档标题：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

此选项启用在转换为 PDF 时在窗口标题栏中显示文档标题。

## 第 3 步：将文档转换为 PDF

使用`Save`指定转换选项将文档转换为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

确保指定正确的路径以保存转换后的 PDF。

### 使用 Aspose.Words for .NET 在窗口标题栏中显示文档标题的示例源代码

以下是使用 Aspose.Words for .NET 在 PDF 文档的窗口标题栏中显示文档标题的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
通过执行这些步骤，您可以在使用 Aspose.Words for .NET 转换为 PDF 时轻松地在窗口标题栏中显示文档标题。

