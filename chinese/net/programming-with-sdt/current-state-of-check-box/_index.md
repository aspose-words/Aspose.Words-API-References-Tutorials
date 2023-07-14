---
title: 复选框的当前状态
linktitle: 复选框的当前状态
second_title: Aspose.Words 文档处理 API
description: 了解如何使用 Aspose.Words for .NET 检索和设置 Word 文档中复选框内容控件的当前状态。
type: docs
weight: 10
url: /zh/net/programming-with-sdt/current-state-of-check-box/
---

本教程介绍如何使用 Aspose.Words for .NET 检索和设置 Word 文档中复选框内容控件的当前状态。您可以根据复选框的当前状态选中或取消选中该复选框。

## 先决条件
要学习本教程，您需要具备以下条件：

- 已安装 Aspose.Words for .NET 库。
- C# 和 Word 文档文字处理的基础知识。

## 第 1 步：设置文档目录
首先设置文档目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`与文档所在目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载文档并检索复选框内容控件
使用以下命令加载 Word 文档`Document`构造函数，将文档的路径作为参数传递。然后，从文档中检索所需的复选框内容控件。在此示例中，我们假设复选框是文档中的第一个结构化文档标签。

```csharp
Document doc = new Document(dataDir + "Structured document tags.docx");
StructuredDocumentTag sdtCheckBox =
	(StructuredDocumentTag)doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
```

## 步骤 3：根据当前状态选中或取消选中复选框
检查检索到的结构化文档标签是否为类型`SdtType.Checkbox`。如果是，则设置`Checked`内容控件的属性`true`选中该框。否则，您可以不选中它。

```csharp
if (sdtCheckBox.SdtType == SdtType.Checkbox)
	sdtCheckBox.Checked = true;
```

## 步骤 4：保存文档
使用命令将修改后的文档保存到指定目录`Save`方法。提供所需的文件名和适当的文件扩展名。在此示例中，我们将文档另存为“WorkingWithSdt.CurrentStateOfCheckBox.docx”。

```csharp
doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

### 使用 Aspose.Words for .NET 的复选框当前状态的示例源代码 

```csharp
	//文档目录的路径
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Structured document tags.docx");
	//从文档中获取第一个内容控件。
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.GetChild(NodeType.StructuredDocumentTag, 0, true);
	if (sdtCheckBox.SdtType == SdtType.Checkbox)
		sdtCheckBox.Checked = true;
	doc.Save(dataDir + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
```

就是这样！您已使用 Aspose.Words for .NET 成功检索并设置了 Word 文档中复选框内容控件的当前状态。