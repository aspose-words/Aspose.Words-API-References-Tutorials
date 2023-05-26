---
title: 句柄空格选项
linktitle: 句柄空格选项
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 管理 TXT 文档中的空格。删除不必要的空格并提高可读性。
type: docs
weight: 10
url: /zh/net/programming-with-txtloadoptions/handle-spaces-options/
---

在本教程中，我们将使用 Aspose.Words for .NET 探索为“使用 TXT 加载选项管理空间”功能提供的 C# 源代码。此功能允许您在加载 TXT 文档时指定空白处理行为。

## 第 1 步：设置环境

在您开始之前，请确保您已经使用 Aspose.Words for .NET 设置了您的开发环境。确保您已经添加了必要的引用并导入了适当的命名空间。

## 第 2 步：创建文本文档

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

const string textDoc = "Line 1\n" +
                        "Line 2\n" +
                        "Line 3";
```

在此步骤中，我们创建一个文本字符串来模拟包含带有前导空格和尾随空格的行的文本文档。

## 第 3 步：配置上传选项

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions
{
     LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
     TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};
```

在此步骤中，我们配置用于加载 TXT 文档的选项。我们创造一个新的`TxtLoadOptions`对象并设置`LeadingSpacesOptions`和`TrailingSpacesOptions`属性到`TxtLeadingSpacesOptions.Trim`和`TxtTrailingSpacesOptions.Trim`分别。这告诉 Aspose.Words 在加载文档时从行中删除前导和尾随空格。

## 第 4 步：装入文档

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);
```

在此步骤中，我们使用`Document`方法并传递包含指定文本字符串和加载选项的内存流。

## 第 5 步：保存文档

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx");
```

在这最后一步中，我们使用`Save`方法并将路径传递到输出文件。

现在您可以运行源代码以通过指定空白处理选项来加载文本文档。生成的文档将保存在指定目录中，名称为“WorkingWithTxtLoadOptions.HandleSpacesOptions.docx”。

### 带有 TXT 加载选项的空间管理功能示例源代码以及 Aspose.Words for .NET*

```csharp

            
//文档目录的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

const string textDoc = "      Line 1 \n" +
					   "    Line 2   \n" +
					   " Line 3       ";

TxtLoadOptions loadOptions = new TxtLoadOptions
{
	LeadingSpacesOptions = TxtLeadingSpacesOptions.Trim,
	TrailingSpacesOptions = TxtTrailingSpacesOptions.Trim
};

Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.HandleSpacesOptions.docx")
            
        
```

## 结论

在本教程中，我们探讨了在 Aspose.Words for .NET 中使用 TXT 加载选项管理空间的功能。我们学习了如何在加载 TXT 文档时指定空白处理行为。

此功能对于处理文档中行左右不必要的空格非常有用。通过配置适当的加载选项，您可以轻松删除这些不需要的空格，这有助于使文档内容更清晰、更易读。

Aspose.Words for .NET 提供了许多用于文档操作和生成的高级功能。加载 TXT 文档时管理空间是它为您提供的众多强大工具之一。

选择最适合您的特定场景的空间管理选项很重要。在这个例子中，我们使用了`Trim`从行的开头和结尾删除不必要的空格的选项。但是，Aspose.Words 也有其他选项来保留空格、完全删除它们或保持它们原样。

不要忘记根据您的特定需求和 TXT 文档的结构调整这些选项。

使用 Aspose.Words for .NET，您可以轻松地处理文档中的空白，提高布局质量和内容的可读性。

因此，请毫不犹豫地将空白管理与 TXT 加载选项集成到您的 Aspose.Words for .NET 项目中，并利用其优势创建格式良好且易于阅读的文档。