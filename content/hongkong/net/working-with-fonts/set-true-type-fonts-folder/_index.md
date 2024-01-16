---
title: 設定 True Type 字型資料夾
linktitle: 設定 True Type 字型資料夾
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 渲染文件時設定 true type 字型資料夾的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/set-true-type-fonts-folder/
---

在本教學中，我們將引導您完成使用 Aspose.Words for .NET 渲染文件時設定 true type 字型資料夾的逐步過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解如何指定包含 True Type 字體的自訂資料夾，以便在使用 Aspose.Words for .NET 渲染文件時使用。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要儲存編輯後的渲染文件的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：載入要渲染的文檔
接下來，您需要使用以下命令載入要渲染的文檔`Document`班級。請務必指定正確的文件路徑。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步驟 3：設定 True Type 字型資料夾
現在，您可以透過建立一個實例來指定渲染時要使用的 true type 字體的資料夾`FontSettings`類別並使用`SetFontsFolder()`設定字體資料夾的方法。您可以指定包含 True Type 字型的自訂資料夾。第二個參數為`SetFontsFolder()`指示是否也要搜尋指定資料夾的子資料夾。

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## 步驟 4：儲存渲染的文檔
最後，您可以使用以下命令將渲染的文檔儲存到檔案中`Save()`的方法`Document`班級。請務必指定正確的路徑和檔案名稱。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### 使用 Aspose.Words for .NET 設定 True Type 字型資料夾的範例原始碼 

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
//請注意，此設定將覆蓋預設搜尋的任何預設字體來源。現在只會搜尋這些資料夾
//渲染或嵌入字體時的字體。若要在保留系統字體來源的同時新增額外的字體來源，請同時使用 FontSettings.GetFontSources 和
//相反，FontSettings.SetFontSources
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
//設定字體設定
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## 結論
在本教學中，我們學習如何在使用 Aspose.Words for .NET 渲染文件時設定 true type 字型資料夾。透過遵循此逐步指南，您可以輕鬆指定包含在渲染文件時使用的 True Type 字體的自訂資料夾。 Aspose.Words 提供了強大且靈活的 API，用於文件中字體的文字處理。有了這些知識，您就可以控制和自訂根據您的特定需求渲染文件時使用的字體。

### 常見問題解答

#### Q：如何在 Aspose.Words 中配置 TrueType 字體資料夾？

答：要在 Aspose.Words 中設定 TrueType 字體資料夾，您可以使用`SetTrueTypeFontsFolder`的方法`Fonts`指定包含 TrueType 字型的資料夾位置的類別。

#### Q：什麼類型的字體被視為 TrueType 字體？

答：TrueType 字型是一種流行的字型格式。它們通常在 Word 文件中使用，並具有 .ttf 或 .ttc 檔案副檔名。

#### Q：我可以在 Aspose.Words 中指定多個 TrueType 字體資料夾嗎？

答：是的，您可以使用 Aspose.Words 中指定多個 TrueType 字體資料夾`SetTrueTypeFontsFolder`的方法`Fonts`帶有資料夾位置清單的類別。

#### Q：如何檢查 Aspose.Words 中配置的 TrueType 字體資料夾？

答：要檢查 Aspose.Words 中配置的 TrueType Fonts 資料夾，您可以使用`GetTrueTypeFontsFolder`的方法`Fonts`類別來取得配置的 TrueType Fonts 資料夾的位置。

#### Q：為什麼在 Aspose.Words 中配置 TrueType 字體資料夾很重要？

答：在Aspose.Words中設定TrueType字體資料夾很重要，因為它可以幫助Aspose.Words找到處理Word文件時所需的字體。這確保了文件格式和外觀的一致性，即使在不同的系統中也是如此。