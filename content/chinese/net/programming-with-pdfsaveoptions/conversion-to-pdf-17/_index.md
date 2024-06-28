---
title: 将Word文档转换为PDF 1.7
linktitle: 将Word文档转换为PDF 1.7
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 将 Word 文档转换为 PDF 1.7。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

在本教程中，我们将引导您完成如何使用 Aspose.Words for .NET 将 Word 文档转换为 PDF 1.7 的步骤。转换为 PDF 1.7 允许您生成符合 PDF 1.7 标准的 PDF 文件。请按照以下步骤操作：

## 第 1 步：加载文档

首先上传您想要转换为 PDF 的文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请务必指定文档的正确路径。

## 第 2 步：设置 PDF 转换选项

创建 PdfSaveOptions 类的实例并指定要使用的 PDF 标准的版本：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

此选项可确保生成的 PDF 文件符合 PDF 1.7 标准。

## 步骤 3：将文档转换为 PDF

使用`Save`将文档转换为 PDF 的方法，指定转换选项：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

确保指定正确的路径来保存转换后的 PDF。

### 使用 Aspose.Words for .NET 转换为 Pdf 17 的示例源代码

以下是使用 Aspose.Words for .NET 转换为 PDF 1.7 的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

通过执行以下步骤，您可以使用 Aspose.Words for .NET 轻松转换为 PDF 1.7。


## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 将 Word 文档转换为 PDF 1.7。通过执行所述步骤，您可以轻松生成符合 PDF 1.7 标准的 PDF 文件。请务必指定 Word 文档的正确路径，并根据需要配置转换为 PDF 的选项。转换为 PDF 1.7 可确保不同平台上的最佳兼容性和可读性。

### 经常问的问题

#### 问：什么是 Word 到 PDF 1.7 转换？
答：将Word文档转换为PDF 1.7就是生成符合PDF 1.7标准的PDF文件。该标准规定了 PDF 文件的功能和要求，以实现不同平台上的最佳兼容性和可读性。

#### 问：如何使用 Aspose.Words for .NET 将 Word 文档转换为 PDF 1.7？
答：要使用 Aspose.Words for .NET 将 Word 文档转换为 PDF 1.7，请按照下列步骤操作：

通过替换设置文档所在的目录路径`"YOUR DOCUMENTS DIRECTORY"`与文档目录的实际路径。

使用以下命令加载要转换为 PDF 的 Word 文档`Document`类并指定指定文档目录中Word文档的路径。

通过创建一个实例将转换配置为 PDF 选项`PdfSaveOptions`类并指定您要使用的 PDF 标准的版本`Compliance`具有价值的财产`PdfCompliance. Pdf17`生成符合 PDF 1.7 标准的 PDF 文件。

使用以下命令将文档保存为 PDF 格式`Save`的方法`Document`类指定路径和保存选项。

#### 问：使用 Aspose.Words for .NET 转换为 PDF 1.7 有什么好处？
答：使用 Aspose.Words for .NET 转换为 PDF 1.7 的优点是：

符合 PDF 1.7 标准：转换为 PDF 1.7 可确保生成的 PDF 文件符合 PDF 1.7 标准，从而确保在不同平台上的兼容性和可读性。

文档格式保留：Aspose.Words for .NET 通过保留格式、图像和样式确保准确的 Word 文档转换，从而生成真实的原始 PDF 文件。