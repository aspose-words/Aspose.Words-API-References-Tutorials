---
title: 使用警告源
linktitle: 使用警告源
second_title: Aspose.Words 文档处理 API
description: 了解如何通过 Aspose.Words for .NET 分步指南使用警告源。
type: docs
weight: 10
url: /zh/net/working-with-markdown/use-warning-source/
---

在此示例中，我们将向您展示如何将警告源与 Aspose.Words for .NET 一起使用。警告源指示使用回调函数时警告的来源。

## 第 1 步：加载文档

我们将使用以下命令加载包含警告的现有文档`Load`的方法`Document`班级。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## 步骤 3：使用警告源

我们将通过设置文档的`WarningCallback`属性到集合`WarningInfo`对象。

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## 步骤 4：保存文档

最后，我们可以将文档保存为所需的格式。

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### 将警告源与 Aspose.Words for .NET 一起使用的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");

WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;

doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");

foreach (WarningInfo warningInfo in warnings)
{
	if (warningInfo.Source == WarningSource.Markdown)
		Console.WriteLine(warningInfo.Description);
}
```

恭喜！您现在已经了解了如何将警告源与 Aspose.Words for .NET 一起使用。

### 常见问题解答

#### 问：我们可以自定义“警告”标签的外观吗？

答：“警告”标签的格式取决于所使用的 Markdown 渲染器。在大多数情况下，您可以使用 CSS 来自定义外观`blockquote`标记在您的文档中。

#### 问：“警告”标签可以添加图标吗？

答：是的，可以在 Markdown 文档中使用 HTML 代码将图标添加到“警告”标签。您可以插入一个`span`具有适当类别的标记以在警告文本旁边显示图标。

#### 问：“警告”标签与所有 Markdown 阅读器兼容吗？

 A：“警告”标签的兼容性取决于所使用的 Markdown 渲染。大多数 Markdown 读者都会支持`blockquote`标签来显示突出显示的文本，但确切的外观可能会有所不同。