---
title: 檢查DrawingML文字效果
linktitle: 檢查DrawingML文字效果
second_title: Aspose.Words 文件處理 API
description: 在本教學中，了解如何使用 Aspose.Words for .NET 檢查 Word 文件中的 DrawingML 文字效果。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/check-drawingml-text-effect/
---

在本教學中，我們將引導您了解如何使用 Aspose.Words Library for .NET 檢查 Word 文件中的 DrawingML 文字效果。透過檢查 DrawingML 文字效果，您可以確定是否將特定效果套用至部分文字。我們將逐步指導您瞭解並實作 .NET 專案中的程式碼。

## 先決條件
在開始之前，請確保您擁有以下物品：
- C# 程式語言的應用知識
- 專案中安裝的 .NET 的 Aspose.Words 函式庫
- 包含 DrawingML 文字效果的 Word 文檔

## 步驟1：定義文檔目錄
首先，您需要將目錄路徑設定為 Word 文件的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有適當路徑的程式碼中。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第二步：載入文件並檢查文字效果
接下來，我們將載入 Word 文件並存取文件正文第一段中的運行（字元序列）集合。接下來，我們將檢查是否有任何特定的 DrawingML 文字效果套用於第一次執行的字體。

```csharp
//載入文檔
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

//檢查DrawingML文字效果
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### 使用 Aspose.Words for .NET 檢查 DMLText 效果的範例原始碼 

```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

//一次運行可能會套用多種 Dml 文字效果。
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## 結論
在本教學中，我們了解如何使用 Aspose.Words for .NET 檢查 Word 文件中的 DrawingML 文字效果。透過檢查 DrawingML 文字效果，您可以識別出應用了特定效果的文字部分。請隨意使用此功能來操作和分析 Word 文件中的文字效果。

### 常見問題解答

#### Q：如何使用 Aspose.Words 存取 Word 文件中的 DrawingML 文字效果？

答：透過 Aspose.Words，您可以使用提供的 API 存取 Word 文件中的 DrawingML 文字效果。您可以瀏覽文字元素並檢查文字效果的特定屬性，例如顏色、大小等。

#### Q：Word 文件中常用的 DrawingML 文字效果有哪些類型？

答：Word 文件中常用的 DrawingML 文字效果類型包括陰影、反射、發光、漸層等。這些效果可用於改善文字的外觀和格式。

#### Q：如何檢查 Word 文件中 DrawingML 文字效果的顏色？

答：要檢查Word文件中DrawingML文字效果的顏色，您可以使用Aspose.Words提供的方法來存取文字效果的顏色屬性。這樣您就可以獲得用於特定文字效果的顏色。

#### Q：是否可以檢查包含多個節的Word文件中的文字效果？

答：是的，Aspose.Words 允許檢查包含多個部分的 Word 文件中的文字效果。您可以瀏覽文件的每個部分並單獨存取每個部分的文字效果。

#### Q：如何檢查 Word 文件中 DrawingML 文字效果的不透明度？

答：要檢查Word文件中DrawingML文字效果的不透明度，您可以使用Aspose.Words提供的方法來存取文字效果的不透明度屬性。這將允許您獲取應用於特定文字效果的不透明度值。