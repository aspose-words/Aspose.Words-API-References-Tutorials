---
title: 新增群組形狀
linktitle: 新增群組形狀
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將具有多個形狀的群組形狀新增至 Word 文件。
type: docs
weight: 10
url: /zh-hant/net/programming-with-shapes/add-group-shape/
---

本教學課程介紹如何使用 Aspose.Words for .NET 將包含多個形狀的群組形狀新增至 Word 文件。群組形狀可讓您將多個形狀作為單一實體進行組合和操作。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與要儲存文件的目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：建立新文件和 GroupShape
建立一個新實例`Document`類和`GroupShape`物件使用該文件。

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## 步驟 3：建立形狀並將其新增至 GroupShape
建立單獨的形狀，例如`accentBorderShape`和`actionButtonShape`使用`Shape`班級。根據需要自訂其屬性。將這些形狀附加到`groupShape`目的。

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## 步驟 4：設定 GroupShape 的尺寸
設定寬度、高度和座標大小`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## 步驟 5：將 GroupShape 插入文件中
創建一個`DocumentBuilder`物件並插入`groupShape`使用`InsertNode`方法。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## 第 6 步：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithShapes.AddGroupShape.docx」。

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### 使用 Aspose.Words for .NET 新增群組形狀的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

就是這樣！您已使用 Aspose.W 成功將包含多個形狀的群組形狀新增至 Word 文件中