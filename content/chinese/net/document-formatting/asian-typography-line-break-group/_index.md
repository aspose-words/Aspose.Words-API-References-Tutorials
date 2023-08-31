---
title: Word 文档中的亚洲版式换行组
linktitle: Word 文档中的亚洲版式换行组
second_title: Aspose.Words 文档处理 API
description: 了解如何通过 Aspose.Words for .NET 在 Word 文档中使用亚洲版式换行符组。
type: docs
weight: 10
url: /zh/net/document-formatting/asian-typography-line-break-group/
---
在本教程中，我们将向您展示如何通过 Aspose.Words for .NET 在 Word 文档功能中使用亚洲版式换行符组。请按照以下步骤了解源代码并应用格式更改。

## 第 1 步：加载文档

首先，指定文档的目录并将包含亚洲版式的文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 第 2 步：亚洲版式设置

我们现在将为文档第一段配置亚洲版式设置。就是这样：

```csharp
ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
format. FarEastLineBreakControl = false;
format. WordWrap = true;
format. HangingPunctuation = false;
```

## 步骤 3：保存文档

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
```

### 使用 Aspose.Words for .NET 的亚洲版式换行组的示例源代码

以下是 Aspose.Words for .NET 的亚洲版式换行组功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat;
	format.FarEastLineBreakControl = false;
	format.WordWrap = true;
	format.HangingPunctuation = false;

	doc.Save(dataDir + "DocumentFormatting.AsianTypographyLineBreakGroup.docx");
	
```
通过此代码，您将能够使用 Aspose.Words for .NET 应用亚洲版式换行符组。

## 结论

在本教程中，我们探索了 Aspose.Words for .NET 中的“亚洲版式换行组”功能。通过配置`FarEastLineBreakControl`, `WordWrap`， 和`HangingPunctuation`的属性`ParagraphFormat`，我们能够控制 Word 文档中亚洲版式的换行行为。此功能对于处理亚洲字符以及确保具有混合语言内容的文档中的正确换行和自动换行非常有用。

### 常见问题解答

#### 问：Aspose.Words for .NET 中的“亚洲版式换行组”功能是什么？

答：Aspose.Words for .NET 中的“亚洲版式换行组”功能允许您控制 Word 文档中亚洲版式的换行行为。具体来说，它会影响在处理段落中的亚洲字符时换行和换行的方式。

#### 问：如何在 Aspose.Words for .NET 中启用“亚洲版式换行组”？

答：要启用“亚洲版式换行组”，您需要配置`FarEastLineBreakControl`, `WordWrap`， 和`HangingPunctuation`的属性`ParagraphFormat`您文档中的相关段落。环境`FarEastLineBreakControl`到`false`确保在换行方面亚洲字符的处理方式与拉丁字符类似。`WordWrap`设置`true`启用亚洲版式的自动换行，以及`HangingPunctuation`设置`false`防止标点符号挂在亚洲文本中。

#### 问：我可以将“亚洲版式换行组”应用于文档中的特定段落吗？

答：是的，您可以将“亚洲版式换行组”设置应用于 Word 文档中的特定段落。在示例代码中，设置应用于文档的第一段。您可以根据需要调整代码以定位其他段落，方法是通过`Paragraphs`文件中相关部分的集合。