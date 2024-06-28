---
title: 导出 PDF 文档中的自定义属性
linktitle: 导出 PDF 文档中的自定义属性
second_title: Aspose.Words 文档处理 API
description: 了解如何在使用 Aspose.Words for .NET 将文档转换为 PDF 时导出自定义属性。
type: docs
weight: 10
url: /zh/net/programming-with-pdfsaveoptions/custom-properties-export/
---

在本教程中，我们将引导您完成使用 Aspose.Words for .NET 将文档的自定义属性导出到 PDF 文档中的步骤。导出自定义属性允许您在生成的 PDF 文档中包含附加信息。请按照以下步骤操作：

## 第 1 步：创建文档并添加自定义属性

首先创建 Document 类的实例：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 第 2 步：添加自定义属性
接下来，添加所需的自定义属性。例如，要添加值为“Apose”的“Company”属性，请使用`Add`CustomDocumentProperties 集合的方法：

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

## 步骤 4：将文档转换为 PDF

使用`Save`将文档转换为 PDF 的方法，指定转换选项：

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);
```

确保指定正确的路径来保存转换后的 PDF。

### 使用 Aspose.Words for .NET 自定义属性导出的示例源代码

以下是使用 Aspose.Words for .NET 从文档导出自定义属性的完整源代码：


```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	doc.CustomDocumentProperties.Add("Company", "Aspose");

	PdfSaveOptions saveOptions = new PdfSaveOptions { CustomPropertiesExport = PdfCustomPropertiesExport.Standard };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.CustomPropertiesExport.pdf", saveOptions);

```

通过执行以下步骤，您可以在使用 Aspose.Words for .NET 转换为 PDF 时轻松导出文档的自定义属性。


## 结论

在本教程中，我们解释了如何使用 Aspose.Words for .NET 将自定义属性从文档导出到 PDF 文档。按照所描述的步骤，您可以通过导出文档的自定义属性，轻松地在生成的 PDF 文档中包含附加信息。利用 Aspose.Words for .NET 的功能，通过导出自定义属性来个性化和丰富您的 PDF 文档。

### 经常问的问题

#### 问：什么是将自定义属性导出到 PDF 文档？
答：将自定义属性导出到 PDF 文档允许在生成的 PDF 文档中包含附加信息。自定义属性是特定于您的文档的元数据，例如标签、关键字或凭据。通过导出这些自定义属性，您可以使用户在查看 PDF 文档时可以使用它们。

#### 问：如何使用 Aspose.Words for .NET 将文档的自定义属性导出到 PDF 文档？
答：要使用 Aspose.Words for .NET 将文档的自定义属性导出到 PDF 文档，请按照下列步骤操作：

创建一个实例`Document`班级。

使用以下命令添加所需的自定义属性`CustomDocumentProperties`收藏。例如，使用`Add`方法添加值为“Apose”的“Company”属性。

创建一个实例`PdfSaveOptions`类并指定如何使用导出自定义属性`CustomPropertiesExport`财产。这`PdfCustomPropertiesExport.Standard`value 根据默认设置导出自定义属性。

使用`Save`的方法`Document`用于将文档转换为 PDF 的类，指定转换选项。

#### 问：如何访问 PDF 文档的自定义属性？
答：要访问 PDF 文档的自定义属性，您可以使用支持查看文档属性的兼容 PDF 阅读器。最常见的 PDF 阅读器（例如 Adobe Acrobat Reader）提供对 PDF 文档的元数据和属性的访问。您通常可以在“文件”菜单下找到这些选项，或者右键单击文档并选择“属性”。