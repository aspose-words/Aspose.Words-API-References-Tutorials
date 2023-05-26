---
title: 更改亚洲段落间距和缩进
linktitle: 更改亚洲段落间距和缩进
second_title: Aspose.Words for .NET API 参考
description: 了解如何使用 Aspose.Words for .NET 更改亚洲段落间距和缩进。
type: docs
weight: 10
url: /zh/net/document-formatting/change-asian-paragraph-spacing-and-indents/
---

在本教程中，我们将带您了解如何使用 Aspose.Words for .NET 更改亚洲段落的间距和缩进。按照以下步骤了解源代码并应用更改。

## 第 1 步：装入文档

首先，指定文档的目录并将包含亚洲版式的文档加载到 Document 对象中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## 第 2 步：更改段落间距和缩进

我们现在将修改亚洲文档第一段的间距和缩进。就是这样：

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; //更新 ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; //更新 ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; //更新 ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; //更新 ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; //更新 ParagraphFormat.SpaceAfter
```

## 第 3 步：保存文档

插入文本输入表单域后，使用`Save`方法。确保提供适当的文件路径：

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### 使用 Aspose.Words for .NET 更改亚洲段落间距和缩进的示例源代码

以下是使用 Aspose.Words for .NET 编辑亚洲段落间距和缩进功能的完整源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent 将被更新
	format.CharacterUnitRightIndent = 10;      //ParagraphFormat.RightIndent 将被更新
	format.CharacterUnitFirstLineIndent = 20;  //ParagraphFormat.FirstLineIndent 将被更新
	format.LineUnitBefore = 5;                 //ParagraphFormat.SpaceBefore 将被更新
	format.LineUnitAfter = 10;                 //ParagraphFormat.SpaceAfter 将被更新

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

使用此代码，您将能够使用 Aspose.Words for .NET 更改亚洲段落的间距和缩进。

