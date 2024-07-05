---
title: 在气球中显示修订
linktitle: 在气球中显示修订
second_title: Aspose.Words 文档处理 API
description: 使用 Aspose.Words for .NET 在气球中显示修订。
type: docs
weight: 10
url: /zh/net/working-with-revisions/show-revisions-in-balloons/
---

在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 在 Word 文档的气泡框中显示修订。我们将为您提供完整的源代码并向您展示如何格式化 markdown 输出。

## 步骤 1：加载文档

第一步是上传包含修订内容的文档。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：配置评论展示选项

我们将配置显示选项以使修订在气球中可见。

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## 步骤 3：将文档保存为 PDF 格式

最后，我们将文档保存为 PDF，并在气泡框中显示修订内容。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## Markdown 输出格式

输出可以采用 markdown 格式来提高可读性。例如：

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### 使用 Aspose.Words for .NET 在气球中显示修订的示例源代码

以下是使用 Aspose.Words for .NET 在文档中的气球中显示修订的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

//渲染以内联方式插入修订，在气球中删除和格式化修订。
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
//在页面右侧呈现修订栏。
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## 结论

在本教程中，我们学习了如何使用 Aspose.Words for .NET 在 Word 文档的气泡框中显示修订。通过使用适当的显示选项，我们能够使修订在气泡中可见，并在右侧显示修订栏。Aspose.Words for .NET 提供了许多用于操作 Word 文档的强大功能，包括修订管理。现在，您可以使用这些知识，使用 Aspose.Words for .NET 在您自己的 Word 文档的气泡框中显示修订。


### 常见问题解答

#### 问：如何在 Aspose.Words for .NET 中上传文档？

答：使用`Document` Aspose.Words for .NET 类用于从文件加载文档。您可以指定完整的文档路径。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### 问：如何使用 Aspose.Words for .NET 在气球中显示修订？

答：使用`ShowInBalloons`的财产`RevisionOptions`对象来配置修订在气球中的显示。您可以在`ShowInBalloons.FormatAndDelete`在气球中显示删除和格式修改的修改。

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
```

#### 问：如何使用 Aspose.Words for .NET 将文档保存为 PDF 格式？

答：使用`Save`方法`Document`对象以 PDF 格式保存文档。您必须指定带有“.pdf”扩展名的完整目标路径。

```csharp
doc.Save("path/to/destination/document.pdf");
```