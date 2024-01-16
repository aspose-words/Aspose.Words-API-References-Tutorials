---
title: 將桌子放在一起
linktitle: 將桌子放在一起
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 將 Word 文件中的表格組合在一起。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/keep-table-together/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 將 Word 文件中的表格組合在一起。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠保持表格完整，而不會在 Word 文件中將其拆分為多個頁面。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 步驟 2：載入文件並檢索表格
要開始對表格進行文字處理，我們需要載入文件並取得我們想要保留在一起的表格。按著這些次序：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Table spanning two pages.docx");

//檢索表
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑。

## 第 3 步：啟用“KeepWithNext”選項
為了將表格保持在一起並防止其拆分為多個頁面，我們需要為表格中的每個段落啟用「KeepWithNext」選項，表格最後一行的最後幾個段落除外。使用以下程式碼：

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

在這裡，我們循環遍歷表格中的每個儲存格，並為儲存格中的每個段落啟用「KeepWithNext」選項，表格中最後一行的最後段落除外。

## 第四步：儲存修改後的文檔
最後，我們需要將修改後的文件與表格一起儲存。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 將表格保持在一起的範例原始程式碼 

```csharp
	//文檔目錄的路徑
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//我們需要為表中的每個段落啟用 KeepWithNext，以防止其跨頁，
	//除了表格最後一行的最後一段。
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 將 Word 文件中的表格組合在一起。透過遵循本逐步指南並實現提供的 C# 程式碼，您可以保持表格完整併防止其在文件中拆分為多個頁面。此功能可讓您更能控製文件中表格的外觀和佈局。