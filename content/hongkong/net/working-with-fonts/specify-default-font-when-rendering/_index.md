---
title: 渲染時指定預設字體
linktitle: 渲染時指定預設字體
second_title: Aspose.Words 文件處理 API
description: 了解如何在使用 Aspose.Words for .NET 渲染 Word 文件時指定預設字體。確保跨平台的文檔外觀一致。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/specify-default-font-when-rendering/
---
## 介紹

確保 Word 文件在不同平台上正確呈現可能是一項挑戰，尤其是在處理字體相容性時。保持外觀一致的一種方法是在將文件渲染為 PDF 或其他格式時指定預設字體。在本教學中，我們將探討如何使用 Aspose.Words for .NET 設定預設字體，以便您的文件無論在何處查看都看起來很棒。

## 先決條件

在深入研究程式碼之前，我們先介紹一下本教學需要遵循的內容：

- Aspose.Words for .NET：確保您安裝了最新版本。你可以下載它[這裡](https://releases.aspose.com/words/net/).
- 開發環境：Visual Studio 或任何其他.NET 開發環境。
- C# 基礎知識：本教學假設您熟悉 C# 程式設計。

## 導入命名空間

首先，您需要匯入必要的命名空間。這些將允許您存取使用 Aspose.Words 所需的類別和方法。

```csharp
using Aspose.Words;
using Aspose.Words.Fonts;
```

現在，讓我們將指定預設字體的過程分解為易於遵循的步驟。

## 第 1 步：設定您的文件目錄

首先，定義文檔目錄的路徑。這是您的輸入和輸出檔案將儲存的位置。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：載入您的文檔

接下來，載入要渲染的文檔。在此範例中，我們將使用名為「Rendering.docx」的檔案。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步驟 3：配置字型設定

建立一個實例`FontSettings`並指定預設字體。如果在渲染過程中找不到定義的字體，Aspose.Words 將使用電腦上最接近的可用字體。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial Unicode MS";
```

## 步驟 4：將字型設定套用到文檔

將配置的字體設定指派給您的文件。

```csharp
doc.FontSettings = fontSettings;
```

## 第 5 步：儲存文檔

最後，以所需的格式儲存文件。在本例中，我們將其另存為 PDF。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SpecifyDefaultFontWhenRendering.pdf");
```

## 結論

透過執行以下步驟，您可以確保 Word 文件以指定的預設字體呈現，從而保持不同平台之間的一致性。這對於廣泛共享或在具有不同字體可用性的系統上查看的文件特別有用。


## 常見問題解答

### 為什麼要在 Aspose.Words 中指定預設字體？
指定預設字體可確保您的文件在不同平台上顯示一致，即使原始字體不可用。

### 如果渲染期間找不到預設字體會發生什麼情況？
Aspose.Words將使用機器上最接近的可用字體來盡可能保持文件的外觀。

### 我可以指定多種預設字體嗎？
不可以，您只能指定一種預設字體。但是，您可以使用以下命令處理特定情況下的字體替換`FontSettings`班級。

### Aspose.Words for .NET 是否與所有版本的 Word 文件相容？
是的，Aspose.Words for .NET 支援多種 Word 文件格式，包括 DOC、DOCX、RTF 等。

### 如果遇到問題，我可以在哪裡獲得支援？
您可以從 Aspose 社群和開發人員那裡獲得支持[Aspose.Words 支援論壇](https://forum.aspose.com/c/words/8).