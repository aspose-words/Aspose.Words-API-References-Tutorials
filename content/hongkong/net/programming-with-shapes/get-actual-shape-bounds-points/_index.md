---
title: 取得實際形狀邊界點
linktitle: 取得實際形狀邊界點
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中擷取以點（測量單位）為單位的形狀的實際邊界。
type: docs
weight: 10
url: /zh-hant/net/programming-with-shapes/get-actual-shape-bounds-points/
---

本教學課程說明如何使用 Aspose.Words for .NET 在 Word 文件中擷取以點（測量單位）為單位的形狀的實際邊界。邊界表示文件中形狀的大小和位置。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：建立新文件和 DocumentBuilder
建立一個新實例`Document`類別和一個`DocumentBuilder`物件使用該文件。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：插入影像形狀
使用`InsertImage`的方法`DocumentBuilder`物件將圖像形狀插入到文件中。提供影像檔案的路徑作為參數。

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## 第 3 步：擷取實際形狀邊界點
訪問形狀的`ShapeRenderer`使用`GetShapeRenderer`方法。然後，使用以下命令檢索形狀的實際邊界（以點為單位）：`BoundsInPoints`財產。

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### 使用 Aspose.Words for .NET 取得實際形狀邊界點的範例原始碼 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

就是這樣！您已使用 Aspose.Words for .NET 成功擷取了 Word 文件中形狀的實際邊界（以點為單位）。