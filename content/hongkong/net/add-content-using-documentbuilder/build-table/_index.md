---
title: 在Word文件中建立表格
linktitle: 在Word文件中建立表格
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 在 Word 文件中建立表格。
type: docs
weight: 10
url: /zh-hant/net/add-content-using-documentbuilder/build-table/
---
在本逐步教學中，您將學習如何使用 Aspose.Words for .NET 在 Word 文件中建立表格。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠使用 DocumentBuilder 類別建立具有自訂格式和內容的表格。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：建立一個新文檔
首先，使用 Document 類別建立一個新文件：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## 第 2 步：啟動表格
接下來，使用 DocumentBuilder 類別的 StartTable 方法開始建立表格：

```csharp
Table table = builder.StartTable();
```

## 第 3 步：插入儲存格並新增內容
現在，您可以使用 DocumentBuilder 類別的 InsertCell 和 Write 方法將儲存格插入表中並在其中新增內容。根據需要自訂儲存格格式：

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## 第四步：結束行
將內容加入第一行的儲存格後，使用 DocumentBuilder 類別的 EndRow 方法結束該行：

```csharp
builder.EndRow();
```

## 第 5 步：自訂行格式
您可以透過設定 RowFormat 和 CellFormat 物件的屬性來自訂行的格式：

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## 第六步：結束桌子
要完成表格，請使用 DocumentBuilder 類別的 EndTable 方法：

```csharp
builder.EndTable();
```

### 使用 Aspose.Words for .NET 建立表格的範例原始程式碼
以下是使用 Aspose.Words for .NET 建立表格的完整原始程式碼：

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## 結論
恭喜！您已成功學習如何使用 Aspose.Words for .NET 在 Word 文件中建立表格。透過遵循逐步指南並利用提供的原始程式碼，您現在可以建立具有自訂格式的表格。

### Word文件中建表常見問題解答

#### Q：什麼是 Aspose.Words for .NET？

答：Aspose.Words for .NET 是一個功能強大的文件處理庫，可讓開發人員在 .NET 應用程式中以程式設計方式建立、讀取、編輯和轉換 Microsoft Word 文件。它提供了廣泛的處理 Word 文件的功能，例如文字操作、表格建立、文件保護、格式設定等。

#### Q：如何使用 Aspose.Words for .NET 在 Word 文件中建立表格？

答：要使用 Aspose.Words for .NET 在 Word 文件中建立表格，您可以按照以下步驟操作：
1. 建立一個新實例`Document`類別和一個`DocumentBuilder`目的。
2. 使用`StartTable`的方法`DocumentBuilder`類開始建表。
3. 將儲存格插入表格並使用`InsertCell`和`Write`的方法`DocumentBuilder`班級。
4. 使用以下命令結束該行`EndRow`的方法`DocumentBuilder`班級。
5. 透過設定行的屬性來自訂行格式`RowFormat`和`CellFormat`對象。
6. 使用結束表`EndTable`的方法`DocumentBuilder`班級。
7. 儲存文檔。

#### Q：如何自訂表格及其儲存格的格式？

答：您可以透過設定表格的各種屬性來自訂表格及其儲存格的格式。`RowFormat`和`CellFormat`對象。例如，您可以調整儲存格對齊方式、垂直和水平文字方向、儲存格高度、行高等。透過使用這些屬性，您可以獲得表格及其內容所需的外觀。

#### Q：我可以使用合併儲存格和其他進階功能建立複雜的表格嗎？

答：是的，Aspose.Words for .NET 提供了建立複雜表格的進階功能，包括對合併儲存格、巢狀表格和複雜表格佈局的支援。您可以使用`MergeCells`合併單元格的方法，`StartTable`方法建立巢狀表，以及其他方法來實作所需的表結構。

#### Q：Aspose.Words for .NET 是否與不同的 Word 文件格式相容？

答：是的，Aspose.Words for .NET 與各種 Word 文件格式相容，包括 DOC、DOCX、RTF 等。它支援傳統格式 (DOC) 和現代基於 XML 的格式 (DOCX)，並允許您毫無問題地處理不同格式的文件。

#### Q：在哪裡可以找到有關 Aspose.Words for .NET 的更多資訊和文件？

答：您可以在以下位置找到全面的文件和程式碼範例[API參考](https://reference.aspose.com/words/net/)。該文件將提供有關該程式庫的功能以及如何在 .NET 應用程式中使用它們的詳細資訊。