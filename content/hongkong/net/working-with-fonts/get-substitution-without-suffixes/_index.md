---
title: 取得不含後綴的替換
linktitle: 取得不含後綴的替換
second_title: Aspose.Words 文件處理 API
description: 在本教學中，了解如何使用 Aspose.Words for .NET 在 Word 文件中取得無後綴覆蓋。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/get-substitution-without-suffixes/
---

在本教學中，我們將向您展示如何使用 .NET 的 Aspose.Words 函式庫在 Word 文件中取得不帶後綴的覆寫。無後綴替換用於解決顯示或列印文件時的字型替換問題。我們將逐步指導您瞭解並實作 .NET 專案中的程式碼。

## 先決條件
在開始之前，請確保您擁有以下物品：
- C# 程式語言的應用知識
- 專案中安裝的 .NET 的 Aspose.Words 函式庫

## 步驟1：定義文檔目錄
首先，您需要將目錄路徑設定為 Word 文件的位置。代替`"YOUR DOCUMENT DIRECTORY"`在具有適當路徑的程式碼中。

```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟2：載入文件並配置不含後綴的替換
接下來，我們將使用以下命令載入文檔`Document`類別並使用以下命令配置無後綴替換`DocumentSubstitutionWarnings`班級。我們還將透過指定包含字體的資料夾來新增字體來源。

```csharp
//載入文件並配置不含後綴的替換
Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;

List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
```

## 步驟 3：儲存文檔
最後，我們將儲存套用無後綴覆蓋的文件。

```csharp
//儲存文件
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");
```

### 使用 Aspose.Words for .NET 取得無後綴的替換的範例原始碼 
```csharp

//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Get substitution without suffixes.docx");
DocumentSubstitutionWarnings substitutionWarningHandler = new DocumentSubstitutionWarnings();
doc.WarningCallback = substitutionWarningHandler;
List<FontSourceBase> fontSources = new List<FontSourceBase>(FontSettings.DefaultInstance.GetFontsSources());
FolderFontSource folderFontSource = new FolderFontSource(FontsDir, true);
fontSources.Add(folderFontSource);
FontSourceBase[] updatedFontSources = fontSources.ToArray();
FontSettings.DefaultInstance.SetFontsSources(updatedFontSources);
doc.Save(dataDir + "WorkingWithFonts.GetSubstitutionWithoutSuffixes.pdf");

```

## 結論
在本教學中，我們了解如何使用 Aspose.Words for .NET 在 Word 文件中取得不含後綴的覆寫。不帶後綴的替換對於解決字體替換問題很有用。請隨意使用此功能來改進文件的顯示和列印。

### 常見問題解答

#### Q：為什麼 Aspose.Words 在字體替換中加上字尾？

答：Aspose.Words 在字體替換中加入後綴，以避免原始字體和替換字體之間的衝突。這有助於確保轉換和操作文件時的最大相容性。

#### Q：如何在 Aspose.Words 中擷取沒有後綴的字體替換？

答：要在 Aspose.Words 中檢索不含後綴的字體替換，您可以使用`FontSubstitutionSettings`類和`RemoveSuffixes`財產。將此屬性設為`true`將獲得不添加後綴的字體替換。

#### Q：是否可以在 Aspose.Words 中停用為字體替換添加後綴？

答：不，無法在 Aspose.Words 中停用為字體替換添加後綴。預設添加後綴以確保文件相容性和一致性。

#### Q：如何在 Aspose.Words 中過濾掉字體替換中不需要的後綴？

答：要過濾掉 Aspose.Words 中字體替換中不需要的後綴，可以使用字串處理技術，例如使用`Replace`或者`Substring`刪除您不想包含的特定後綴的方法。