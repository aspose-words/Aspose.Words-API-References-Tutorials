---
title: 開放式特點
linktitle: 開放式特點
second_title: Aspose.Words 文件處理 API
description: 了解如何在 Aspose.Words for .NET 中啟用和使用 Open Type 功能
type: docs
weight: 10
url: /zh-hant/net/enable-opentype-features/open-type-features/
---

在這個綜合教學中，您將學習如何啟用和利用 Aspose.Words for .NET 中的 Open Type 功能。我們將引導您完成整個過程，並為您提供必要的 C# 程式碼片段。在本指南結束時，您將能夠在 Word 文件中使用 Open Type 功能。

## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- Aspose.Words for .NET 程式庫安裝在您的系統上。

## 第 1 步：載入文檔
首先，使用 Document 類別載入文件：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## 第 2 步：啟用開放式功能
若要啟用開放類型功能，請將 LayoutOptions 類別的 TextShaperFactory 屬性設定為所需文字整形器工廠的實例。在此範例中，我們使用 HarfBuzzTextShaperFactory：

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## 第 3 步：儲存文檔
啟用 Open Type 功能後，將文件儲存為所需的輸出格式，例如 PDF：

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### 使用 Aspose.Words for .NET 的開放型別功能的範例原始碼
以下是在 Aspose.Words for .NET 中使用 Open Type 功能的完整原始碼：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## 結論
恭喜！您已成功學習如何啟用並利用 Aspose.Words for .NET 中的 Open Type 功能。透過遵循逐步指南並利用提供的原始程式碼，現在您可以在 Word 文件中使用 Open Type 功能。

Open Type 功能提供增強的版式和文字塑造功能，讓您能夠建立具有視覺吸引力和專業外觀的文件。嘗試不同的文字整形器工廠，並探索專案中 Open Type 功能的可能性。

### 常見問題解答

#### Q：如何在 Aspose.Words for .NET 中啟用 OpenType 功能？

答：要在 Aspose.Words for .NET 中啟用 OpenType 功能，您需要按照教學中提到的步驟進行操作。

#### Q：Aspose.Words for .NET 支援哪些 OpenType 功能？

答：Aspose.Words for .NET 支援多種 OpenType 功能，例如連字、字形變體、上下文替換等。

#### Q：如何檢查特定字體是否支援 OpenType 功能？

答：您可以使用以下指令檢查特定字型是否支援 OpenType 功能：`Font.OpenTypeFeatures` Aspose.Words for .NET 中的方法。

#### Q：Aspose.Words for .NET 支援哪些其他文字格式設定功能？

答：除了 OpenType 功能外，Aspose.Words for .NET 還支援其他文字格式化功能，例如格式化段落、建立表格、新增圖片等。

#### Q：我可以在所有版本的 Aspose.Words for .NET 中使用 OpenType 功能嗎？

答：較新版本的 Aspose.Words for .NET 支援 OpenType 功能。確保您使用相容版本才能受益於這些功能。