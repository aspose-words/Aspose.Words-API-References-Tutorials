---
title: 寬高比鎖定
linktitle: 寬高比鎖定
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 鎖定或解鎖 Word 文件中形狀的長寬比。
type: docs
weight: 10
url: /zh-hant/net/programming-with-shapes/aspect-ratio-locked/
---

本教學介紹如何使用 Aspose.Words for .NET 鎖定或解鎖 Word 文件中形狀的長寬比。透過鎖定縱橫比，您可以在調整形狀大小時保持形狀的原始比例。

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

## 第 3 步：插入影像形狀
使用`InsertImage`的方法`DocumentBuilder`物件將圖像形狀插入到文件中。提供影像檔案的路徑作為參數。

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## 步驟 4：鎖定或解鎖寬高比
設定`AspectRatioLocked`形狀的屬性為`true`或者`false`分別鎖定或解鎖寬高比。

```csharp
shape.AspectRatioLocked = false; //解鎖寬高比
```

## 第 5 步：儲存文檔
使用以下命令將文件儲存到指定目錄`Save`方法。提供所需的檔案名稱和適當的檔案副檔名。在此範例中，我們將文件另存為「WorkingWithShapes.AspectRatioLocked.docx」。

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### 使用 Aspose.Words for .NET 鎖定寬高比的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

就是這樣！您已使用 Aspose.Words for .NET 成功鎖定或解鎖 Word 文件中形狀的長寬比。