---
title: 通过禁用嵌入字体来减小 PDF 大小
linktitle: 通过禁用嵌入字体来减小 PDF 大小
second_title: Aspose.Words for .NET API 参考
description: 了解在使用 Aspose.Words for .NET 将文档转换为 PDF 时如何通过禁用 Windows 字体嵌入来减小 PDF 大小。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/disable-embed-windows-fonts/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 在 PDF 文档中禁用 Windows 字体嵌入来减小 PDF 大小的步骤。通过禁用字体嵌入，您可以减小生成的 PDF 文件的大小。请按照以下步骤操作：

## 第 1 步：加载文档

首先上传您想要转换为 PDF 的文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

请务必指定文档的正确路径。

## 第 2 步：设置 PDF 保存选项

创建 PdfSaveOptions 类的实例并指定如何嵌入字体：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
```

此选项允许您在生成的 PDF 文件中停用 Windows 字体的集成。

## 步骤 3：将文档转换为 PDF

使用`Save`将文档转换为 PDF 的方法，指定转换选项：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);
```

确保指定正确的路径来保存转换后的 PDF。

### 使用 Aspose.Words for .NET 禁用嵌入 Windows 字体的示例源代码

以下是使用 Aspose.Words for .NET 在 PDF 文档中禁用嵌入 Windows 字体的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//保存输出的 PDF 时不会嵌入标准 Windows 字体。
	PdfSaveOptions saveOptions = new PdfSaveOptions { FontEmbeddingMode = PdfFontEmbeddingMode.EmbedNone };
	
	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisableEmbedWindowsFonts.pdf", saveOptions);

```
通过执行以下步骤，您可以使用 Aspose.Words for .NET 轻松禁用在 PDF 文档中嵌入 Windows 字体。


## 结论

在本教程中，我们学习了如何通过使用 Aspose.Words for .NET 禁用嵌入 Windows 字体来减小 PDF 文件的大小。通过禁用字体嵌入，您可以减小生成的 PDF 文件的大小，从而更轻松地存储、共享和传输文件。但是，请务必注意，禁用 Windows 字体嵌入可能会导致最终 PDF 文档的外观和格式发生变化。使用此功能时请务必考虑这些后果。请随意探索 Aspose.Words for .NET 的更多功能来优化 PDF 文件的生成。

### 经常问的问题

#### 问：什么是在 PDF 文档中禁用 Windows 字体嵌入？为什么它很重要？
答：在 PDF 文档中禁用 Windows 字体嵌入是防止 Windows 字体包含在生成的 PDF 文件中的过程。这可以通过删除嵌入的 Windows 字体数据来减小 PDF 文件的大小。这对于减小 PDF 文件的大小非常重要，从而使它们更容易存储、共享和更快地传输。

#### 问：如何使用 Aspose.Words for .NET 在 PDF 文档中禁用 Windows 字体嵌入？
答：要使用 Aspose.Words for .NET 在 PDF 文档中禁用嵌入 Windows 字体，请按照下列步骤操作：

使用以下命令加载要转换为 PDF 的文档`Document`类和文档路径。

创建一个实例`PdfSaveOptions`类并设置`FontEmbeddingMode`财产给`PdfFontEmbeddingMode.EmbedNone`。这会禁用在生成的 PDF 文件中嵌入 Windows 字体。

使用`Save`的方法`Document`将文档转换为 PDF 的对象，指定之前配置的转换选项。

#### 问：在 PDF 文档中禁用 Windows 字体嵌入有什么好处？
答：在 PDF 文档中禁用 Windows 字体嵌入的好处是：

减小 PDF 文件大小：通过禁用 Windows 字体嵌入，嵌入的 Windows 字体数据将被删除，从而减小生成的 PDF 文件的大小。

更容易存储：较小的 PDF 文件更容易存储、保存和传输。

更快的共享和传输：较小的 PDF 文件可以更快地共享和传输，从而节省时间和资源。

#### 问：在 PDF 文档中禁用 Windows 字体嵌入会产生什么后果？
答：在 PDF 文档中禁用 Windows 字体嵌入可能会导致以下后果：

外观和格式丢失：如果文档中指定的 Windows 字体在打开 PDF 的系统上不可用，则将使用替代字体，这可能会导致外观和格式不正确。形状与预期不同。

可读性问题：如果使用的替代字体不如原始字体可读，可能会影响 PDF 文档中文本的可读性。