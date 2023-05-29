---
title: 在气球中显示修订
linktitle: 在气球中显示修订
second_title: Aspose.Words for .NET API 参考
description: 使用 Aspose.Words for .NET 在气球中显示修订。
type: docs
weight: 10
url: /zh/net/working-with-revisions/show-revisions-in-balloons/
---

在本分步指南中，我们将向您展示如何使用 Aspose.Words for .NET 在 Word 文档中的气球中显示修订。我们将为您提供完整的源代码，并向您展示如何格式化降价输出。

## 第 1 步：装入文档

第一步是上传包含修订的文档。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Revisions.docx");
```

## 第 2 步：配置评论显示选项

我们将配置显示选项以使修订在气球中可见。

```csharp
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;
```

## 第 3 步：将文档保存为 PDF 格式

最后，我们将文档另存为 PDF，并在气球中显示修订。

```csharp
doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```

## 降价输出格式

可以将输出格式化为 markdown 以提高可读性。例如 ：

```markdown
- Revisions are Showed in bubbles with revision bars on the right side.
```

### 使用 Aspose.Words for .NET 在气球中显示修订的示例源代码

以下是使用 Aspose.Words for .NET 在文档中的气球中显示修订的完整源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(MyDir + "Revisions.docx");

//呈现内联插入修订、删除和格式化气球中的修订。
doc.LayoutOptions.RevisionOptions.ShowInBalloons = ShowInBalloons.FormatAndDelete;
doc.LayoutOptions.RevisionOptions.MeasurementUnit = MeasurementUnits.Inches;
//在页面右侧呈现修订栏。
doc.LayoutOptions.RevisionOptions.RevisionBarsPosition = HorizontalAlignment.Right;

doc.Save(dataDir + "WorkingWithRevisions.ShowRevisionsInBalloons.pdf");
```



