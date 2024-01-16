---
title: 設定相對水平或垂直位置
linktitle: 設定相對水平或垂直位置
second_title: Aspose.Words 文件處理 API
description: 了解如何使用 Aspose.Words for .NET 設定 Word 文件中表格的相對水平或垂直位置。
type: docs
weight: 10
url: /zh-hant/net/programming-with-tables/set-relative-horizontal-or-vertical-position/
---

在本教學中，我們將學習如何使用 Aspose.Words for .NET 設定 Word 文件中表格的相對水平或垂直位置。我們將按照逐步指南來理解程式碼並實現此功能。在本教學結束時，您將能夠在 Word 文件中設定表格的相對水平或垂直位置。

## 第 1 步：項目設置
1. 啟動 Visual Studio 並建立一個新的 C# 專案。
2. 新增對 Aspose.Words for .NET 函式庫的參考。

## 第 2 步：載入文檔
若要啟動文件的文字處理，請依照下列步驟操作：

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//載入文檔
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

請務必將「您的文件目錄」替換為文件目錄的實際路徑，並提供正確的檔案名稱。

## 第三步：設定表格的相對位置
接下來，我們將設定表格的相對水平或垂直位置。使用以下程式碼：

```csharp
//檢索表
Table table = doc.FirstSection.Body.Tables[0];

//定義工作台的相對水平位置
table.HorizontalAnchor = RelativeHorizontalPosition.Column;

//定義表格的相對垂直位置
table.VerticalAnchor = RelativeVerticalPosition.Page;
```

這裡我們使用文檔從第一部分的正文中檢索第一個表格。接下來，我們使用以下命令設定表格的相對水平位置`HorizontalAnchor`屬性使用`RelativeHorizontalPosition.Column`價值。類似地，我們設定表格的相對垂直位置`VerticalAnchor`屬性使用`RelativeVerticalPosition.Page`價值。

## 第四步：儲存修改後的文檔
最後，我們需要儲存修改後的文件並定義表格的相對位置。使用以下程式碼：

```csharp
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

請務必為輸出文件指定正確的路徑和檔案名稱。

### 使用 Aspose.Words for .NET 設定相對水平或垂直位置的範例原始程式碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table wrapped by text.docx");
Table table = doc.FirstSection.Body.Tables[0];
table.HorizontalAnchor = RelativeHorizontalPosition.Column;
table.VerticalAnchor = RelativeVerticalPosition.Page;
doc.Save(dataDir + "WorkingWithTables.SetFloatingTablePosition.docx");
```

## 結論
在本教學中，我們學習如何使用 Aspose.Words for .NET 設定 Word 文件中表格的相對水平或垂直位置。透過遵循此逐步指南並實現提供的 C# 程式碼，您可以將此相對位置套用到 Word 文件中的表格。