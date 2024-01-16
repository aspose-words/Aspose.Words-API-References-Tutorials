---
title: 建立表格樣式
linktitle: 建立表格樣式
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 建立自訂表格樣式的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/programming-with-table-styles-and-formatting/create-table-style/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 建立表格樣式的逐步流程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何使用 Aspose.Words for .NET 為 Word 文件中的表格建立自訂樣式。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要儲存編輯的 Word 文件的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟 2：建立新文檔和文檔產生器
接下來，您需要建立一個新的實例`Document`類別和該文檔的文檔建構子。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 3 步：建立一個新表格並新增儲存格
要開始建立表，我們使用`StartTable()`文檔生成器的方法，然後我們使用`InsertCell()`方法，我們將單元格的內容寫入使用`Write()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
builder.Write("Name");
builder. InsertCell();
builder.Write("Value");
builder. EndRow();
builder. InsertCell();
builder. InsertCell();
builder. EndTable();
```

## 第四步：建立表格樣式
現在我們可以使用以下命令來建立表格樣式`TableStyle`類和`Add()`文件中的方法`s `風格的集合。我們定義樣式的屬性，例如邊框、邊距和填滿。

```csharp
TableStyle tableStyle = (TableStyle)doc.Styles.Add(StyleType.Table, "MyTableStyle1");
tableStyle.Borders.LineStyle = LineStyle.Double;
tableStyle.Borders.LineWidth = 1;
tableStyle. LeftPadding = 18;
tableStyle. RightPadding = 18;
tableStyle.TopPadding = 12;
tableStyle.BottomPadding = 12;
```

## 步驟5：將表格樣式套用到表格
最後，我們使用已建立的表格樣式應用到表格`Style`表的屬性。

```csharp
table.Style = tableStyle;
```

## 第六步：儲存修改後的文檔
最後將修改後的文檔儲存到文件中。您可以為輸出文件選擇適當的名稱和位置。

```csharp


doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

恭喜！現在您已經使用 Aspose.Words for .NET 為表格建立了自訂樣式。

### 使用 Aspose.Words for .NET 建立表格樣式的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	builder.Write("Name");
	builder.InsertCell();
	builder.Write("Value");
	builder.EndRow();
	builder.InsertCell();
	builder.InsertCell();
	builder.EndTable();
	TableStyle tableStyle = (TableStyle) doc.Styles.Add(StyleType.Table, "MyTableStyle1");
	tableStyle.Borders.LineStyle = LineStyle.Double;
	tableStyle.Borders.LineWidth = 1;
	tableStyle.LeftPadding = 18;
	tableStyle.RightPadding = 18;
	tableStyle.TopPadding = 12;
	tableStyle.BottomPadding = 12;
	table.Style = tableStyle;
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 建立表格樣式。透過遵循此逐步指南，您可以輕鬆自訂 Word 文件中的表格樣式。 Aspose.Words 提供了強大且靈活的 API，用於操作文件中的表格並設定其格式。有了這些知識，您就可以改進 Word 文件的視覺呈現並滿足特定需求。