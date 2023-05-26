---
title: 使用警告源
linktitle: 使用警告源
second_title: Aspose.Words for .NET API 参考
description: 通过 Aspose.Words for .NET 分步指南了解如何使用警告源。
type: docs
weight: 10
url: /zh/net/working-with-markdown/use-warning-source/
---

在这个例子中，我们将向您展示如何在 Aspose.Words for .NET 中使用警告源。警告源表示使用回调函数时警告的来源。

## 第 1 步：装入文档

我们将使用`Load`的方法`Document`班级。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Emphases markdown warning.docx");
```

## 第 3 步：使用警告源

我们将通过设置文档的`WarningCallback`属性集合`WarningInfo`对象。

```csharp
WarningInfoCollection warnings = new WarningInfoCollection();
doc.WarningCallback = warnings;
```

## 第 4 步：保存文档

最后，我们可以将文档保存为所需的格式。

```csharp
doc.Save(dataDir + "WorkingWithMarkdown.UseWarningSource.md");
foreach (WarningInfo warningInfo in warnings)
{
if (warningInfo.Source == WarningSource.Markdown)
	Console.WriteLine(warningInfo.Description);
}
```

### 将 Warning Source 与 Aspose.Words for .NET 一起使用的示例源代码

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