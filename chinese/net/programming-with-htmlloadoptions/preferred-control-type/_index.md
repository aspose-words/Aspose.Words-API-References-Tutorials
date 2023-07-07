---
title: 首选控制类型
linktitle: 首选控制类型
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 加载 HTML 文档时指定首选控件类型的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlloadoptions/preferred-control-type/
---

本文提供了有关如何将首选控件类型功能与 Aspose.Words for .NET 结合使用的分步指南。我们将详细解释代码的每一部分。在本教程结束时，您将能够了解如何在加载 HTML 文档时指定首选控件类型。

在开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到库和安装说明。

## 第 1 步：定义 HTML 代码

首先，您需要定义要作为文档加载的 HTML 代码。在这个例子中，我们定义了一个`html`包含带有选项的选择器的 HTML 代码的变量。

```csharp
const string html=@"
<html>
<select name='ComboBox' size='1'>
<option value='val1'>item1</option>
<option value='val2'></option>
</select>
</html>
";
```

## 第 2 步：设置 HTML 加载选项

接下来，我们创建一个`HtmlLoadOptions`对象并设置`PreferredControlType`财产给`HtmlControlType.StructuredDocumentTag`。这告诉 Aspose.Words 在加载时使用 StructuredDocumentTags 来表示 HTML。

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## 步骤 3：加载并保存文档

我们使用`Document`类，使用之前定义的加载选项从内存流加载 HTML 代码。然后我们将文档保存在指定目录中`.docx`文件格式。

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);
doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);
```

### 使用 Aspose.Words for .NET 的首选控件类型的示例源代码

```csharp
	
	const string html = @"
		<html>
			<select name='ComboBox' size='1'>
				<option value='val1'>item1</option>
				<option value='val2'></option>                        
			</select>
		</html>
	";
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };

	Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(html)), loadOptions);

	doc.Save(dataDir + "WorkingWithHtmlLoadOptions.PreferredControlType.docx", SaveFormat.Docx);

```

就这样 ！使用 Aspose.Words for .NET 加载 HTML 文档时，您已成功指定首选控件类型。