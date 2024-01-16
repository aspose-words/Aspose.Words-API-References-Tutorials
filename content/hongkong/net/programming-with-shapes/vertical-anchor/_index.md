---
title: 垂直錨
linktitle: 垂直錨
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 中的垂直錨點功能在文件中垂直定位形狀。
type: docs
weight: 10
url: /zh-hant/net/programming-with-shapes/vertical-anchor/
---

本教學介紹如何使用 Aspose.Words for .NET 中的垂直錨點功能在文件中垂直定位形狀。透過設定形狀的垂直錨點屬性，您可以控制其相對於文字或頁面的垂直對齊方式。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與要儲存文件的目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立新文件和 DocumentBuilder
建立一個新實例`Document`類別和一個`DocumentBuilder`物件使用該文件。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：插入並配置形狀
使用以下命令將形狀插入到文件中`InsertShape`的方法`DocumentBuilder`目的。設定形狀所需的尺寸。

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## 第四步：設定垂直錨點
設定形狀的垂直錨點屬性以控制其垂直對齊方式。在此範例中，我們將其設為「Bottom」以將形狀錨定在文字或頁面的底部。

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## 第 5 步：為形狀新增內容
使用`MoveTo`的方法`DocumentBuilder`物件將遊標移動到形狀的第一段。然後，使用`Write`在形狀中加入內容的方法。

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## 第 6 步：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件儲存為「WorkingWithShapes.VerticalAnchor.docx」。

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### 使用 Aspose.Words for .NET 的垂直錨點範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

就是這樣！您已成功使用 Aspose.Words for .NET 中的垂直錨點功能在文件中垂直定位形狀。