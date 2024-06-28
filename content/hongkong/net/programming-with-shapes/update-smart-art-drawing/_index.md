---
title: 更新智慧藝術繪圖
linktitle: 更新智慧藝術繪圖
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 更新 Word 文件中的 Smart Art 繪圖。
type: docs
weight: 10
url: /zh-hant/net/programming-with-shapes/update-smart-art-drawing/
---

本教學介紹如何使用 Aspose.Words for .NET 更新 Word 文件中的 Smart Art 繪圖。透過迭代文件中的形狀並檢查它們是否具有智慧藝術，您可以更新智慧藝術繪圖以反映對其數據所做的任何更改。

## 先決條件
要學習本教程，您需要具備以下條件：

- 已安裝 Aspose.Words for .NET 程式庫。
- C# 和 Word 文件文字處理的基礎知識。

## 第 1 步：設定文檔目錄
首先設定文檔目錄的路徑。代替`"YOUR DOCUMENT DIRECTORY"`與文件所在目錄的實際路徑。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入文檔
使用以下命令載入包含 Smart Art 繪圖的 Word 文檔`Document`類別構造函數。

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## 第 3 步：更新智慧藝術繪圖
使用以下命令迭代文件中的形狀`GetChildNodes`方法與`NodeType.Shape`參數。使用以下命令檢查每個形狀是否具有智慧藝術`HasSmartArt`屬性，如果為 true，則呼叫`UpdateSmartArtDrawing`更新 Smart Art 繪圖的方法。

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### 使用 Aspose.Words for .NET 更新智慧藝術繪圖的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

就是這樣！您已使用 Aspose.Words for .NET 成功更新了 Word 文件中的 Smart Art 繪圖。