---
title: 設定優先權字體資料夾
linktitle: 設定優先權字體資料夾
second_title: Aspose.Words 文件處理 API
description: 使用 Aspose.Words for .NET 渲染文件時優先設定字體資料夾的逐步指南。
type: docs
weight: 10
url: /zh-hant/net/working-with-fonts/set-fonts-folders-with-priority/
---

在本教學中，我們將引導您逐步完成使用 Aspose.Words for .NET 渲染文件時設定優先字體資料夾的過程。我們將解釋捆綁的 C# 原始程式碼，並為您提供全面的指南，幫助您理解並在自己的專案中實現此功能。在本教學結束時，您將了解在使用 Aspose.Words for .NET 渲染文件時如何指定具有自訂搜尋優先順序的多個字體資料夾。

## 步驟1：定義文檔目錄
首先，您需要設定文檔目錄的路徑。這是您要儲存編輯後的渲染文件的位置。將“您的文件目錄”替換為適當的路徑。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步驟2：設定優先字體資料夾
然後您可以使用以下命令設定優先字體資料夾`FontSettings`類和`SetFontsSources()`方法。您可以使用下列實例指定多個字型來源`SystemFontSource`和`FolderFontSource`。在本例中，我們定義了兩個字體來源：預設的系統字體來源和優先順序為1的自訂字體資料夾。

```csharp
FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true, 1)
});
```

## 第 3 步：載入要渲染的文檔
現在您可以使用以下命令載入要渲染的文檔`Document`班級。請務必指定正確的文件路徑。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## 步驟 4：儲存渲染的文檔
最後，您可以使用以下命令將渲染的文檔儲存到檔案中`Save()`的方法`Document`班級。請務必指定正確的路徑和檔案名稱。

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

### 使用 Aspose.Words for .NET 設定優先權字體資料夾的範例原始碼 
```csharp
//文檔目錄的路徑
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsSources(new FontSourceBase[]
{
	new SystemFontSource(), new FolderFontSource("C:\\MyFonts\\", true,1)
});
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersWithPriority.pdf");
```

## 結論
在本教學中，我們學習如何在使用 Aspose.Words for .NET 渲染文件時優先設定字體資料夾。透過遵循此逐步指南，您可以在渲染文件時輕鬆指定具有自訂搜尋優先順序的多個字體資料夾。 Aspose.Words 提供了強大且靈活的 API，用於文件中字體的文字處理。有了這些知識，您就可以控制和自訂根據您的特定需求渲染文件時使用的字體來源。

### 常見問題解答

#### Q：如何在 Aspose.Words 中設定優先字體資料夾？

答：要在 Aspose.Words 中設定優先字體資料夾，您可以使用`SetFontsFoldersWithPriority`的方法`Fonts`透過指定字型資料夾位置及其優先順序來定義類別。

#### Q：如果一種字體存在於多個具有不同優先順序的資料夾中，會發生什麼情況？

答：如果一種字體存在於多個具有不同優先順序的資料夾中，Aspose.Words 在處理文件時將使用具有最高優先順序的資料夾中的版本。

#### Q：我可以在 Aspose.Words 中指定多個具有相同優先順序的字體資料夾嗎？

答：是的，您可以在 Aspose.Words 中指定多個具有相同優先權的字體資料夾。在文件中搜尋字體時，Aspose.Words 會同等優先考慮它們。

#### Q：如何查看Aspose.Words中定義的優先字體資料夾？

答：要檢查 Aspose.Words 中優先定義的字體資料夾，您可以使用`GetFolders`的方法`Fonts`類別來取得已配置字體資料夾的列表，包括它們的優先順序。

#### Q：在Aspose.Words中設定優先字體資料夾有什麼用？

答：在Aspose.Words中設定優先字體資料夾可以讓您控制Word文件中字體的搜尋順序。這有助於您確保使用所需的字體並避免出現不必要的字體替換問題。