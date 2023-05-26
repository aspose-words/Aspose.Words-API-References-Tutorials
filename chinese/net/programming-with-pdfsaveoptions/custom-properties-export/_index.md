---
title: 自定义属性导出
linktitle: 自定义属性导出
second_title: Aspose.Words for .NET API 参考
description: 了解如何在使用 Aspose.Words for .NET 将文档转换为 PDF 时导出自定义属性。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/custom-properties-export/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 导出文档自定义属性的步骤。导出自定义属性允许您在生成的 PDF 文档中包含附加信息。请按照以下步骤操作：

## 第 1 步：创建文档并添加自定义属性

首先创建 Document 类的实例：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 第 2 步：添加自定义属性
接下来，添加所需的自定义属性。例如，要添加值为“Aspose”的“Company”属性，请使用`Add`CustomDocumentProperties 集合的方法：

```csharp
doc.CustomDocumentProperties.Add("Company", "Aspose");
```

您可以根据需要添加任意数量的自定义属性。

## 第 3 步：设置 PDF 导出选项

创建 PdfSaveOptions 类的实例并指定如何导出自定义属性：

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };
```

此选项控制转换为 PDF 时自定义属性的导出。

## 第 4 步：将文档转换为 PDF

使用`Save`指定转换选项将文档转换为 PDF 的方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

确保指定正确的路径以保存转换后的 PDF。

### 使用 Aspose.Words for .NET 的自定义属性导出示例源代码

以下是使用 Aspose.Words for .NET 从文档中导出自定义属性的完整源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

通过执行这些步骤，您可以在使用 Aspose.Words for .NET 转换为 PDF 时轻松导出文档的自定义属性。

