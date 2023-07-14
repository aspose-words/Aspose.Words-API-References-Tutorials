---
title: 更改亚洲段落间距和缩进
linktitle: 更改亚洲段落间距和缩进
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 更改亚洲段落间距和缩进。
type: docs
weight: 10
url: /zh/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

在本教程中，我们将引导您了解如何使用 Aspose.Words for .NET 更改亚洲段落的间距和缩进。请按照以下步骤了解源代码并应用更改。

## 第 1 步：加载文档

首先，指定文档的目录并将包含亚洲版式的文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 步骤 2：更改段落间距和缩进

我们现在将修改亚洲文档第一段的间距和缩进。就是这样：

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; //更新 ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; //更新 ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //更新 ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; //更新 ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; //更新 ParagraphFormat.SpaceAfter
```

## 步骤 3：保存文档

插入文本输入表单字段后，使用以下命令将文档保存到所需位置`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### 使用 Aspose.Words for .NET 更改亚洲段落间距和缩进的示例源代码

以下是 Aspose.Words for .NET 编辑亚洲段落间距和缩进功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent 将更新
	format.CharacterUnitRightIndent = 10;      //ParagraphFormat.RightIndent 将更新
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent 将更新
	format.LineUnitBefore = 5;                 //ParagraphFormat.SpaceBefore 将更新
	format.LineUnitAfter = 10;                 //ParagraphFormat.SpaceAfter 将更新

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

通过此代码，您将能够使用 Aspose.Words for .NET 更改亚洲段落的间距和缩进。

