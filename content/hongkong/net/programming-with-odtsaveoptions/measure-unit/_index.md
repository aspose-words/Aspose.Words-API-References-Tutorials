---
title: 測量單位
linktitle: 測量單位
second_title: Aspose.Words 文件處理 API
description: 了解如何在 Aspose.Words for .NET 中配置測量單位功能，以在 ODT 轉換期間保留文件格式。
type: docs
weight: 10
url: /zh-hant/net/programming-with-odtsaveoptions/measure-unit/
---
## 介紹

您是否曾經需要將 Word 文件轉換為不同的格式，但需要為佈局指定特定的測量單位？無論您處理的是英吋、公分還是磅，確保文件在轉換過程中保持完整性至關重要。在本教學中，我們將介紹如何在 Aspose.Words for .NET 中設定測量單位功能。這項強大的功能可確保您的文件格式在轉換為 ODT（開放文件文字）格式時完全按照您的需求保留。

## 先決條件

在深入研究程式碼之前，您需要先完成一些事情：

1. Aspose.Words for .NET：請確定您已安裝了最新版本的 Aspose.Words for .NET。如果您還沒有，您可以從以下位置下載[這裡](https://releases.aspose.com/words/net/).
2. 開發環境：像 Visual Studio 這樣的 IDE，用於編寫和執行 C# 程式碼。
3. C# 基礎知識：了解 C# 基礎知識將幫助您遵循本教學。
4. Word 文件：準備好可用於轉換的範例 Word 文件。

## 導入命名空間

在開始編碼之前，讓我們確保導入了必要的命名空間。在程式碼檔案的頂部加入這些 using 指令：

```csharp
using Aspose.Words;
using Aspose.Words.Saving;
```

## 第 1 步：設定您的文件目錄

首先，您需要定義文檔目錄的路徑。這是您的 Word 文件所在的位置以及轉換後的文件將保存的位置。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

代替`"YOUR DOCUMENTS DIRECTORY"`與目錄的實際路徑。這可確保您的程式碼知道在哪裡可以找到您的 Word 文件。

## 步驟2：載入Word文檔

接下來，您需要載入要轉換的Word文件。這是使用以下方法完成的`Document`來自 Aspose.Words 的類別。

```csharp
//載入Word文檔
Document doc = new Document(dataDir + "Document.docx");
```

確保名為「Document.docx」的 Word 文件存在於指定目錄中。

## 步驟 3：配置測量單位

現在，讓我們來設定 ODT 轉換的測量單位。這就是奇蹟發生的地方。我們將設定`OdtSaveOptions`使用英吋作為測量單位。

```csharp
//使用“測量單位”功能配置備份選項
OdtSaveOptions saveOptions = new OdtSaveOptions { MeasureUnit = OdtSaveMeasureUnit.Inches };
```

在此範例中，我們將測量單位設為英吋。您也可以選擇其他單位，例如`OdtSaveMeasureUnit.Centimeters`或者`OdtSaveMeasureUnit.Points`根據您的要求。

## 步驟 4：將文件轉換為 ODT

最後，我們將使用配置的Word文檔轉換為ODT格式`OdtSaveOptions`.

```csharp
//將文件轉換為 ODT
doc.Save(dataDir + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

此行程式碼將轉換後的文件保存在指定的目錄中，並套用新的測量單位。

## 結論

現在你就擁有了！透過執行下列步驟，您可以輕鬆設定 Aspose.Words for .NET 中的測量單位功能，以確保在轉換過程中保留文件的佈局。無論您使用的是英吋、公分還是點，本教學向您展示如何輕鬆控製文件的格式。

## 常見問題解答

### 什麼是 Aspose.Words for .NET？
Aspose.Words for .NET 是一個功能強大的程式庫，用於以程式設計方式處理 Word 文件。它允許開發人員創建、修改、轉換和處理 Word 文檔，而無需使用 Microsoft Word。

### 除了英吋之外，我還可以使用其他測量單位嗎？
是的，Aspose.Words for .NET 支援其他測量單位，例如公分和點。您可以使用指定所需的單位`OdtSaveMeasureUnit`枚舉。

### Aspose.Words for .NET 有沒有免費試用版？
是的，您可以從以下位置下載 Aspose.Words for .NET 的免費試用版：[這裡](https://releases.aspose.com/).

### 在哪裡可以找到 Aspose.Words for .NET 的文檔？
您可以存取 Aspose.Words for .NET 的綜合文件：[這個連結](https://reference.aspose.com/words/net/).

### 如何獲得 Aspose.Words for .NET 支援？
如需支持，您可以造訪 Aspose.Words 論壇：[這個連結](https://forum.aspose.com/c/words/8).
