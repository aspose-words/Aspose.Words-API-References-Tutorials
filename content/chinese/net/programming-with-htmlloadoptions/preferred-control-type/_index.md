---
title: Word 文档中的首选控件类型
linktitle: Word 文档中的首选控件类型
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 加载 HTML 文档时，在 Word 文档中指定首选控件类型的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-htmlloadoptions/preferred-control-type/
---
本文提供了有关如何使用 Aspose.Words for .NET 的首选控件类型功能的分步指南。我们将详细解释代码的每个部分。在本教程结束时，您将能够了解如何在加载 HTML 文档时指定首选控件类型。

开始之前，请确保您已在项目中安装并配置了 Aspose.Words for .NET 库。您可以在 Aspose 网站上找到该库和安装说明。

## 步骤 1：定义 HTML 代码

首先，您需要定义要作为文档加载的 HTML 代码。在此示例中，我们定义了一个`html`包含带有选项的选择器的 HTML 代码的变量。

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

接下来我们创建一个`HtmlLoadOptions`对象并设置`PreferredControlType`财产`HtmlControlType.StructuredDocumentTag`。这告诉 Aspose.Words 在加载时使用 StructuredDocumentTags 来表示 HTML。

```csharp
HtmlLoadOptions loadOptions = new HtmlLoadOptions { PreferredControlType = HtmlControlType.StructuredDocumentTag };
```

## 步骤 3：加载并保存文档

我们使用`Document`类使用先前定义的加载选项从内存流加载 HTML 代码。然后我们使用`.docx`文件格式。

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

就这样！您已成功指定使用 Aspose.Words for .NET 加载 HTML 文档时的首选控件类型。

## 结论

通过遵循本分步指南，您已经学会了如何使用 Aspose.Words for .NET 中的“首选控件类型”功能在加载 HTML 文档时指定所需的控件类型。设置`PreferredControlType`财产`HtmlControlType.StructuredDocumentTag`允许 Aspose.Words 使用 StructuredDocumentTags (SDT) 来更好地表示和处理 HTML 内容。您还可以探索其他控件类型以满足您的特定要求。使用此功能有助于确保使用 Aspose.Words 准确高效地处理 C# 应用程序中的 HTML 文档。

### Word 文档中首选控件类型的常见问题解答

#### 问：Aspose.Words for .NET 中的“首选控制类型”功能是什么？

答：“首选控件类型”功能允许您在加载 HTML 文档时指定首选的控件类型来表示 HTML 元素。它有助于选择适当的控件类型，以便更好地表示和处理 HTML 内容。

#### 问：如何设置加载 HTML 文档时首选的控件类型？

答：要设置首选控制类型，您需要创建一个`HtmlLoadOptions`对象并设置其`PreferredControlType`属性到所需的`HtmlControlType` 在提供的示例中，`HtmlControlType.StructuredDocumentTag`用来。

#### 问：使用 StructuredDocumentTags (SDT) 作为首选控制类型有何意义？

答：StructuredDocumentTags (SDT) 是基于 XML 的元素，可用于表示 Word 文档中的复杂内容和控件。使用 SDT 作为首选控件类型可以提供更好的兼容性和 HTML 内容表示。

#### 问：如何确保 Aspose.Words 在加载 HTML 文档时使用首选的控件类型？

答：通过设置`PreferredControlType`财产`HtmlControlType.StructuredDocumentTag`如示例源代码所示，Aspose.Words 在加载文档时将使用 SDT 来表示 HTML 元素。

#### 问：我可以使用其他控制类型作为首选选项吗？

答：是的，除了`HtmlControlType.StructuredDocumentTag`，Aspose.Words for .NET支持其他控件类型，例如`HtmlControlType.ContentControl`和`HtmlControlType.CustomXmlMarkup`.