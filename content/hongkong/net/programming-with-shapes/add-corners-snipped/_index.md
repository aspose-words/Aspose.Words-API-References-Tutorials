---
title: 添加剪掉的角
linktitle: 添加剪掉的角
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將帶有剪角的形狀新增至 Word 文件。
type: docs
weight: 10
url: /zh-hant/net/programming-with-shapes/add-corners-snipped/
---

本教學介紹如何使用 Aspose.Words for .NET 將帶有剪角的形狀新增至 Word 文件。可以使用以下命令自訂和插入角剪斷形狀`InsertShape`方法。

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

## 第三步：插入剪角形狀
使用`InsertShape`的方法`DocumentBuilder`物件插入一個帶有剪角的形狀。指定形狀類型（在本例中，`ShapeType.TopCornersSnipped`）並提供所需的形狀尺寸。

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## 步驟 4：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithShapes.AddCornersSnipped.docx」。

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### 使用 Aspose.Words for .NET 新增角點片段的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

就是這樣！您已使用 Aspose.Words for .NET 成功將剪角形狀新增至 Word 文件。