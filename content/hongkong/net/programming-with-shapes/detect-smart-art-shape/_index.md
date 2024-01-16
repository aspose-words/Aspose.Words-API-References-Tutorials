---
title: 偵測智能藝術形狀
linktitle: 偵測智能藝術形狀
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 偵測 Word 文件中的 Smart Art 形狀，辨識圖形表示。
type: docs
weight: 10
url: /zh-hant/net/programming-with-shapes/detect-smart-art-shape/
---

本教學介紹如何使用 Aspose.Words for .NET 偵測 Word 文件中的 Smart Art 形狀。智慧藝術形狀是用於直觀地呈現資訊和想法的圖形表示。

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
使用以下命令載入 Word 文檔`Document`建構函數，將文檔的路徑作為參數傳遞。

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## 第 3 步：偵測智慧藝術形狀
遍歷 type 的子節點`Shape`在文件中使用`GetChildNodes`方法。使用以下命令檢查每個形狀是否具有智慧藝術`HasSmart Art`財產。

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## 第四步：輸出結果
列印文件中偵測到的智慧藝術形狀的數量。

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### 使用 Aspose.Words for .NET 偵測智慧藝術形狀的範例原始碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

就是這樣！您已使用 Aspose.Words for .NET 成功偵測到 Word 文件中的 Smart Art 形狀。