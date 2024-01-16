---
title: 刀片形狀
linktitle: 刀片形狀
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將形狀插入 Word 文件中。
type: docs
weight: 10
url: /zh-hant/net/programming-with-shapes/insert-shape/
---

本教學課程說明如何使用 Aspose.Words for .NET 將形狀插入 Word 文件中。形狀可用於增強文件的視覺外觀和佈局。

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

## 第 3 步：插入形狀
使用`InsertShape`的方法`DocumentBuilder`將形狀插入文檔的物件。指定形狀類型、相對水平和垂直位置、頁面尺寸、尺寸和換行類型。如果需要，您也可以設定形狀的旋轉角度。

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## 步驟 4：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件儲存為「WorkingWithShapes.InsertShape.docx」。

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### 使用 Aspose.Words for .NET 插入形狀的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

就是這樣！您已使用 Aspose.Words for .NET 成功將形狀插入到 Word 文件中。