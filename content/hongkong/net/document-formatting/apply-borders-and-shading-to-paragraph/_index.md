---
title: 將邊框和底紋套用到 Word 文件中的段落
linktitle: 將邊框和底紋套用到 Word 文件中的段落
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將邊框和底紋套用到 Word 文件中的段落。
type: docs
weight: 10
url: /zh-hant/net/document-formatting/apply-borders-and-shading-to-paragraph/
---
在本教學中，我們將向您展示如何使用 Aspose.Words for .NET 的功能將邊框和底紋套用到 Word 文件中的段落。請按照以下步驟了解原始程式碼並套用格式變更。

## 第 1 步：建立並設定文檔

首先，建立一個新文件和關聯的 DocumentBuilder 物件。就是這樣：

```csharp
//文檔目錄的路徑。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第2步：邊框配置

現在讓我們透過指定每一邊的邊框樣式來配置段落邊框。就是這樣：

```csharp
BorderCollection borders = builder.ParagraphFormat.Borders;
borders. DistanceFromText = 20;
borders[BorderType.Left].LineStyle = LineStyle.Double;
borders[BorderType.Right].LineStyle = LineStyle.Double;
borders[BorderType.Top].LineStyle = LineStyle.Double;
borders[BorderType.Bottom].LineStyle = LineStyle.Double;
```

## 第 3 步：填充設置

我們現在將透過指定紋理和填滿顏色來配置段落填滿。就是這樣：

```csharp
Shading shading = builder.ParagraphFormat.Shading;
shading.Texture = TextureIndex.TextureDiagonalCross;
shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;
```

## 第 4 步：新增內容

我們將向該段落添加一些格式化內容。就是這樣：

```csharp
builder.Write("I'm a formatted paragraph with a double border and a nice shading.");
```

## 步驟 3：儲存文檔

插入文字輸入表單欄位後，使用以下命令將文件儲存到所需位置`Save`方法。確保提供適當的文件路徑：

```csharp
doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");
```

### 使用 Aspose.Words for .NET 將邊框和底紋套用到段落的範例原始碼

以下是 Aspose.Words for .NET 的「將邊框和陰影套用到段落」功能的完整原始碼：

```csharp

	//文檔目錄的路徑。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	BorderCollection borders = builder.ParagraphFormat.Borders;
	borders.DistanceFromText = 20;
	borders[BorderType.Left].LineStyle = LineStyle.Double;
	borders[BorderType.Right].LineStyle = LineStyle.Double;
	borders[BorderType.Top].LineStyle = LineStyle.Double;
	borders[BorderType.Bottom].LineStyle = LineStyle.Double;

	Shading shading = builder.ParagraphFormat.Shading;
	shading.Texture = TextureIndex.TextureDiagonalCross;
	shading.BackgroundPatternColor = System.Drawing.Color.LightCoral;
	shading.ForegroundPatternColor = System.Drawing.Color.LightSalmon;

	builder.Write("I'm a formatted paragraph with double border and nice shading.");
	
	doc.Save(dataDir + "DocumentFormatting.ApplyBordersAndShadingToParagraph.doc");

```

## 結論

在本教學中，我們學習如何使用 Aspose.Words for .NET 將邊框和底紋套用到 Word 文件中的段落。透過配置段落的`Borders`和`Shading`屬性中，我們能夠設定段落的邊框樣式、線條顏色和填滿顏色。 Aspose.Words for .NET 提供強大的格式化功能來自訂段落的外觀並增強文件的視覺表示。

### 常見問題解答

#### Q：如何使用 Aspose.Words for .NET 將邊框和底紋套用到 Word 文件中的段落？

答：若要使用 Aspose.Words for .NET 將邊框和底紋套用到 Word 文件中的段落，請依照下列步驟操作：
1. 建立一個新文件和`DocumentBuilder`目的。
2. 透過存取配置段落邊框`Borders`的財產`ParagraphFormat`並設定每邊的邊框樣式。
3. 透過存取配置段落填充`Shading`的財產`ParagraphFormat`並指定紋理和填滿顏色。
4. 使用以下命令將內容新增到段落中`Write`的方法`DocumentBuilder`.
5. 使用儲存文檔`Save`方法。

#### Q：如何設定段落各邊的邊框樣式？

 A：要設定段落各邊的邊框樣式，可以存取`Borders`的財產`ParagraphFormat`並設定`LineStyle`每個人的財產`BorderType`（例如，`BorderType.Left`, `BorderType.Right`, `BorderType.Top`, `BorderType.Bottom`）。您可以指定不同的線條樣式，例如`LineStyle.Single`, `LineStyle.Double`, `LineStyle.Dotted`， ETC。

#### Q：如何指定段落底紋的紋理和填滿顏色？

答：要指定段落底紋的紋理和填充顏色，您可以訪問`Shading`的財產`ParagraphFormat`並設定`Texture`屬性到所需的紋理索引（例如，`TextureIndex.TextureDiagonalCross` ）。您也可以設定`BackgroundPatternColor`和`ForegroundPatternColor`屬性到所需的顏色使用`System.Drawing.Color`班級。