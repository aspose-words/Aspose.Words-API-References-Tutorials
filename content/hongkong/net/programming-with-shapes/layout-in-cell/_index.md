---
title: 單元格佈局
linktitle: 單元格佈局
second_title: Aspose.Words 文件處理 API
description: 透過這份綜合指南，了解如何使用 Aspose.Words for .NET 在儲存格中設定佈局。非常適合希望自訂 Word 文件的開發人員。
type: docs
weight: 10
url: /zh-hant/net/programming-with-shapes/layout-in-cell/
---
## 介紹

如果您曾經想要以程式設計方式微調 Word 文件中表格儲存格的佈局，那麼您來對地方了。今天，我們將深入探討如何使用 Aspose.Words for .NET 在儲存格中設定佈局。我們將逐步介紹一個實際範例，以便您可以輕鬆地理解它。

## 先決條件

在我們進入程式碼之前，讓我們確保您擁有所需的一切：

1.  Aspose.Words for .NET：請確定您已安裝 Aspose.Words for .NET 程式庫。如果你還沒有，你可以[在這裡下載](https://releases.aspose.com/words/net/).
2. 開發環境：您需要一個使用.NET 設定的開發環境。如果您正在尋找建議，Visual Studio 是一個不錯的選擇。
3. C# 的基本知識：雖然我將解釋每個步驟，但對 C# 的基本了解將幫助您更輕鬆地進行操作。
4. 文檔目錄：準備一個用於保存文檔的目錄路徑。我們稱之為`YOUR DOCUMENT DIRECTORY`.

## 導入命名空間

首先，請確保您在專案中匯入必要的命名空間：

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

讓我們將這個過程分解為可管理的步驟。

## 第 1 步：建立一個新文檔

首先，我們將建立一個新的Word文件並初始化`DocumentBuilder`物件來幫助我們建立我們的內容。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：建立表格並設定行格式

我們將開始建立一個表格並指定行的高度和高度規則。

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## 第 3 步：插入儲存格並填滿內容

接下來，我們循環將單元格插入表中。對於每 7 個單元格，我們將結束該行以建立新單元格。

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## 第四步：新增浮水印形狀

現在，讓我們為文件添加浮水印。我們將創建一個`Shape`對象並設定其屬性。

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, //如果將形狀放入儲存格中，則顯示表格儲存格外部的形狀。
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## 第 5 步：自訂浮水印外觀

我們將透過設定浮水印的顏色和文字屬性來進一步自訂浮水印的外觀。

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## 步驟 6：將浮水印插入文檔

我們將找到文件中的最後一次運行並在該位置插入浮水印。

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## 步驟 7：針對 Word 2010 最佳化文檔

為了確保相容性，我們將針對 Word 2010 最佳化文件。

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## 第 8 步：儲存文檔

最後，我們將文檔儲存到指定的目錄。

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## 結論

現在你就擁有了！您已成功建立了具有自訂表格佈局的 Word 文檔，並使用 Aspose.Words for .NET 新增了浮水印。本教學旨在提供清晰的逐步指南，以幫助您了解流程的每個部分。借助這些技能，您現在可以透過程式設計方式建立更複雜和自訂的 Word 文件。

## 常見問題解答

### 我可以為水印文字使用不同的字體嗎？
是的，您可以透過設定來更改字體`watermark.TextPath.FontFamily`屬性為您想要的字體。

### 如何調整浮水印的位置？
您可以修改`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment`， 和`VerticalAlignment`屬性來調整浮水印的位置。

### 是否可以使用圖像代替文字作為浮水印？
絕對地！您可以建立一個`Shape`與類型`ShapeType.Image`並使用設定其圖像`ImageData.SetImage`方法。

### 我可以建立具有不同行高的表格嗎？
是的，您可以透過更改`RowFormat.Height`將儲存格插入該行之前的屬性。

### 如何從文件中刪除浮水印？
您可以透過在文件的形狀集合中找到浮水印並調用`Remove`方法。