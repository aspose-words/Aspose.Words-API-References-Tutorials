---
title: 移至 Word 文件中的表格儲存格
linktitle: 移至 Word 文件中的表格儲存格
second_title: Aspose.Words 文件處理 API
description: 在 Aspose.Words for .NET 的 Word 文件功能中使用「移動到表格單元格」的逐步指南
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/move-to-table-cell/
---
在此範例中，我們將逐步引導您使用提供的 C# 原始程式碼來使用 Aspose.Words for .NET 的 Word 文件中的移至表格儲存格功能。此功能可讓您導覽和操作 Word 文件表格內的特定儲存格。請按照以下步驟將此功能整合到您的應用程式中。

## 第 1 步：載入包含表格的文檔

首先，我們需要載入包含要將儲存格移入其中的表格的文件。使用以下程式碼完成此步驟：

```csharp
Document doc = new Document(MyDir + "Tables.docx");
```

此程式碼載入指定文件（取代“MyDir +”Tables.docx””與包含該表的文檔的實際路徑）。

## 步驟 2：將 DocumentBuilder 移至特定的表格儲存格

接下來，我們將 DocumentBuilder 移到特定的表格單元格。使用以下程式碼來執行此步驟：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToCell(0, 2, 3, 0);
builder.Write("\nCell content added by DocumentBuilder");
```

此程式碼從現有文件建立一個 DocumentBuilder，然後將遊標從 DocumentBuilder 移至指定的表格儲存格。最後，它使用 DocumentBuilder 向該單元格添加內容`Write()`方法。

## 第 3 步：檢查結果

現在您可以驗證是否已成功移至表格儲存格。使用以下程式碼完成此步驟：

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

此程式碼驗證指定的儲存格確實是 DocumentBuilder 的目前儲存格。它還驗證 DocumentBuilder 新增的內容是否已正確保存在表格單元格中。

就這樣 ！現在您已經了解如何使用提供的原始程式碼來使用 Aspose.Words for .NET 的移至表格儲存格功能。現在您可以將此功能整合到您自己的應用程式中並操作 Word 文件中的特定表格單元。


### 使用 Aspose.Words for .NET 移動到表格單元格的範例原始程式碼


```csharp
Document doc = new Document(MyDir + "Tables.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

//將建構器移至第一個表格的第 3 行、儲存格 4。
builder.MoveToCell(0, 2, 3, 0);
builder.Write("\nCell contents added by DocumentBuilder");
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

Assert.AreEqual(table.Rows[2].Cells[3], builder.CurrentNode.ParentNode.ParentNode);
Assert.AreEqual("Cell contents added by DocumentBuilderCell 3 contents\a", table.Rows[2].Cells[3].GetText().Trim());
```

## 結論

在此範例中，我們探索了 Aspose.Words for .NET 的「移至表格儲存格」功能。我們學習如何載入包含表格的文件、將 DocumentBuilder 移至特定的表格儲存格以及向該儲存格新增內容。此功能為開發人員提供了強大的工具，可以使用 Aspose.Words for .NET 以程式設計方式導覽和操作 Word 文件表格中的特定儲存格。它可以為您的動態 Word 文件處理和表格內容管理應用程式提供有價值的補充。

### Word 文件中移至表格儲存格的常見問題解答

#### Q：Aspose.Words for .NET 中的「移至表格單元格」功能的用途是什麼？

答：Aspose.Words for .NET 中的「移動到表格單元格」功能可讓開發人員以程式設計方式導覽至並操作 Word 文件表格內的特定儲存格。它提供了在特定單元格內插入、修改或刪除內容的能力。

#### Q：如何將 DocumentBuilder 移至 Word 文件中的特定表格儲存格？

答：要將 DocumentBuilder 移至 Word 文件中的特定表格單元格，可以使用 DocumentBuilder 類別的 MoveToCell 方法。此方法將表中目標行和單元格的索引作為參數，並將遊標置於該單元格的開頭。

#### Q：使用「移至表格儲存格」功能移至特定表格儲存格後，我可以新增或修改內容嗎？

答：是的，一旦使用 MoveToCell 將 DocumentBuilder 定位到所需的表格單元格，您就可以使用 DocumentBuilder 類別的各種方法（例如 Write、Writeln 或 InsertHtml）來新增或修改該單元格的內容。

#### Q：如何驗證移動到表格儲存格是否成功？

答：您可以透過檢查 DocumentBuilder 遊標的位置來驗證是否成功移動到表格儲存格。例如，您可以將 DocumentBuilder 的目前節點與要移動到的儲存格進行比較，並驗證 DocumentBuilder 新增的內容是否正確儲存在表格儲存格中。