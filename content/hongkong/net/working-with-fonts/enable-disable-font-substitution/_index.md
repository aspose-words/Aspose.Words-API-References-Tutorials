---
title: 啟用禁用字體替換
linktitle: 啟用禁用字體替換
second_title: Aspose.Words 文件處理 API
description: 在本教學中，了解如何使用 Aspose.Words for .NET 在 Word 文件中啟用或停用字體替換。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/enable-disable-font-substitution/
---
在本教學中，我們將引導您了解如何在使用 .NET 的 Aspose.Words 庫渲染 Word 文件時啟用或停用字體替換。啟用或停用字體替換可讓您控制是否將遺失的字體自動替換為預設字體。我們將逐步指導您瞭解並實作 .NET 專案中的程式碼。

## 先決條件
在開始之前，請確保您擁有以下物品：
- C# 程式語言的應用知識
- 專案中安裝的 .NET 的 Aspose.Words 函式庫
- 您想要使用或不使用字型替換來呈現的 Word 文檔

## 步驟1：定義文檔目錄
首先，您需要將目錄路徑設定為 Word 文件的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有適當路徑的程式碼中。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟2：上傳文件並配置字體設置
接下來，我們將載入要渲染的 Word 文件並建立一個實例`FontSettings`處理字體設定的類別。我們將透過在中指定字體名稱來設定預設字體覆蓋`DefaultFontName`並禁用字體資訊覆蓋`Enabled`設定`false`.

```csharp
//載入文檔
Document doc = new Document(dataDir + "Rendering.docx");

//配置字體設定
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;

//將字體設定套用到文檔
doc.FontSettings = fontSettings;
```

## 第 3 步：儲存渲染的文檔
最後，我們將保存渲染的文檔，這將遵循定義的字體覆蓋設定。

```csharp
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");
```


### 使用 Aspose.Words for .NET 啟用禁用字體替換的範例原始程式碼 

```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
fontSettings.SubstitutionSettings.FontInfoSubstitution.Enabled = false;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.EnableDisableFontSubstitution.pdf");

```

## 結論
在本教學中，我們了解了使用 Aspose.Words for .NET 渲染 Word 文件時如何啟用或停用字體替換。透過控製字體替換，您可以影響渲染文件中缺少字體的處理方式。請毫不猶豫地使用此功能來自訂 Word 文件中的字體管理。

### 常見問題解答

#### Q：如何使用 Aspose.Words 在 Word 文件中啟用字體替換？

答：要使用 Aspose.Words 在 Word 文件中啟用字體替換，您可以使用 API 指定在所需字體不可用時要使用的替換字體。即使沒有原始字體，這也將確保一致的文字視覺化。

#### Q：是否可以使用 Aspose.Words 停用 Word 文件中的字體替換？

答：是的，使用 Aspose.Words，您可以停用 Word 文件中的字體替換。透過使用 API，您可以防止 Word 以其他字體取代所需的字體，從而保持文字的原始外觀。

#### Q：如果在 Word 文件中替換時缺少所需字體，會發生什麼情況？

答：當 Word 文件中的替換過程中所需字體遺失時，Aspose.Words 可以偵測到此問題並為您提供修復此問題的選項。您可以選擇用備用字體取代遺失的字體，或在文件中包含遺失的字體，以確保正確檢視。

#### Q：使用 Aspose.Words 取代 Word 文件時如何處理缺失字體？

答：要在使用 Aspose.Words 取代 Word 文件時處理遺失的字體，您可以使用 API 來偵測遺失的字體並提供解析度選項。您可以根據需要選擇用替代字體替換缺少的字體或在文件中包含缺少的字體。

#### Q：控制 Word 文件中的字型替換很重要嗎？

答：是的，控制 Word 文件中的字型替換以保持文字的視覺完整性非常重要。透過使用 Aspose.Words 啟用或停用字體替換，您可以確保使用所需的字體並避免遺失或替換字體的問題。